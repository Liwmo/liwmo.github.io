---
layout: post
comments: true
title:  "Finding the perfect cup of coffee with gradient descent (part 1)"
date:   2017-10-16 14:10:51 +0800
categories: Education Programming
tags: algorithms    
excerpt_separator: <!--more-->
---
In middle school, there was a rather popular website kids went to called [Cool Math Games][1] (don't worry, it's not terribly sketchy). Anyway, I forget the specific details, but I do recall having a bit of "independent time" to work on educational-related things, and one student assured our teacher that the site was indeed, *educational*. When she found out that learning consisted of [Bloons Tower Defense][2] and other nonsense, well...let's just say that was the end of that. Yet, despite this incident, my 6th grade teacher remains one of the most influential and amazing educators that I've had. Also, Cool Math Games did have some information on mathematics such as an article on counting I tried skimming over at the time. I gave up upon encountering $$ n \choose k $$, kind of like how I recently struggled through an entire day trying to understand [tensors][3].
<!--more-->

So, to make up for the lack of math and to revisit the joys of childhood, I present to you one of my personal favorites: [Coffee Shop][4]. Go ahead and give it a whirl down below. It's important that you play through at least a few in-game days to make sense of the analysis below (and I apologize in advance for the lack of volume controls; mute the tab if desired). 

<div style="text-align: center"><object type="application/x-shockwave-flash" data="//www.coolmath-games.com/sites/cmatgame/files/games/coffeeshop-coolmath-1.swf" id="swfObjID" width="640" height="480" align="middle"><param name="allowScriptAccess" value="always"><param name="movie" value="coffeeshop-coolmath-1.swf"><param name="menu" value="false"><param name="quality" value="high"><param name="wmode" value="direct"></object></div><br>

### Our Motivating Question

All right, so what does this have to do with the title? Well, after playing a few rounds last week I thought, "Hmm...__what's the best strategy for maximizing profit?__" Since I've been spending so much time trying to move into AI and machine learning, I figured this might make for a fun mini data-analysis tutorial that would be different (in an positive way) from other articles out there. In the following sections, I'm going to introduce the experiment and lay out the necessary tools, namely gradient descent. The fine details and substantive analyses will come in part 2.

### Some Necessary Simplifications

In order to answer the question above, we'll need to collect some data. I decided to generate 50 different sets, one for each simulated day. Each set contains 4 random values, chosen over a uniform distribution with appropriate ranges listed below: 

<table align="center" style="border: 1px solid black; margin-bottom: 10px">
	<tr align="center">
		<td style="padding-right: 20px; padding-left: 20px">Coffee</td>
		<td style="padding-right: 20px; padding-left: 20px">Milk</td>
		<td style="padding-right: 20px; padding-left: 20px">Sugar</td>
		<td style="padding-right: 20px; padding-left: 20px">Price per cup</td>
	</tr>
	<tr align="center">
		<td style="padding-right: 20px; padding-left: 20px"> 0-4 tsps (0.1)</td>
		<td style="padding-right: 20px; padding-left: 20px"> 0-2 cups (0.1)</td>
		<td style="padding-right: 20px; padding-left: 20px"> 0-4 tsps (0.1)</td>
		<td style="padding-right: 20px; padding-left: 20px"> $0.1-$10 (in 0.1 increments)</td>
	</tr>
</table>

Unfortunately, this still leaves plenty of open questions. For instance, temperature has a huge influence on sales. Furthermore, your starting budget will vary depending on how many supplies you purchase. Buy too little and you'll sell out of product, but buy too much and you'll risk spoiling ingredients. I could record daily profits, though that varies with the business reputation and price, which can change midday. To further complicate matters, purchasing in bulk is cheaper. Yet, anyone who has been to a Costco can attest to the dangers of wholesale shopping. As a result, what do we record, how should we buy supplies, and how do we ensure that measurements can be reasonably benchmarked from day to day? 

> A time-consuming exercise: if you're not convinced that we couldn't have just recorded everything and then trained some complex model (requiring more data), try running 100 days worth of simulations with manually-set random values, record every hour-by-hour detail yourself, and then imagine doing that again when you're done.

Solution: narrow the scope of our problem, make reasonable assumptions, do a dry run, and then refine and repeat. Specifically, instead of asking our broad question above, __let's only consider day 1__. We'll then transfer that opening-day strategy throughout the remaining two weeks. This provides us with several benefits. First of all, the temperature is always $$51^{\circ}\text{F}$$ on the first day and lies between the coldest and warmest days. Secondly, the starting budget is constant at $30.00 and our reputation starts at 0%. Lastly, we'll spend our entire budget in order to maximize the cups of coffee we can produce. Even if we don't sell it all, we will need an initial stockpile and most of the supplies will last at least another day.

Admittedly, even this isn't perfect and I'll leave you to come up with more reasons why. However, we've got to start somewhere, and this seems like a reasonable place. Below, I've recorded the reputation and profit for each recipe-price tuple in "data.txt". 

### Exploring the Data
<a name="code"></a>
<iframe frameborder="0" width="100%" height="500px" src="https://repl.it/@Liwmo/Gradient-Descent-Single-Variable?lite=true"></iframe>

Feel free to explore the dataset. The `soldout` column is indicated with a `1` if we ran out of coffee, which only happens once and appears to be an outlier (in terms of reputation). Consequently, we're rarely leaving out potential profits, and even then one might argue that this is an acceptable "penalty" in our model since it means we could be charging more. 

The "main.py" file is broken into 4 parts: the self-explanatory `read_file()` function that you can ignore, `gradient_descent()`, which we'll get to in a bit, a training block, and a plotting block. In the training block you can find all the data split and stored into appropriate column vectors such as `coffee` or `price`. Go ahead and plot some of these variables by modifying the plotting block line `ax1.plot(x_variable, y_variable, 'o')`, then answer following questions:

1. Which two variables seem to be the *most strongly* correlated? That is, find the two with the closest "straight-line" relationship (ex. height and weight).
> <p class="spoiler">Price and Reputation</p>

2. Out of the three ingredients, which one appears to be most correlated with reputation? 
> <p class="spoiler">Milk</p>

3. Most of the remaining pairs seem to be either random, or weakly correlated. However, there is one interesting exception...can you identify it?
> <p class="spoiler">Price and Revenue. This has a very fascinating relationship, and we'll definitely take a closer look at it in part 2. In the meantime, see if you can come up with an explanation for the scatter plot's distinctive shape.</p>

### Linear Regression

Based on the activity, it makes sense to model the relationship between price and reputation with the equation of a line,

$$\hat{y} = \theta_0 + x\theta_1 $$

where $$\theta_0$$ is the y-intercept (bias) and $$\theta_1$$ is the slope (weight). However, how do we determine these parameters? If you had a high school experience similar to me, then you may have been taught to plug points into a calculator and magically compute the regression line. This time however, we'll be doing things from scratch, and trust me, the payoff will be well worth the cost (function). 

Suppose we have a model and some points. We can then compute how far off our model's predicted $$\hat{y}$$ is from the real $$y$$ by taking a difference. Here's an example:

<img style="display: block; margin: 0 auto; height: 280px"  src="/assets/images/grad_descent_1.png"/>

We can then square each of these differences (to get distances) and then take an average of all these "errors". The resulting quantity is the mean squared error (MSE):

$$ MSE = \frac{1}{m} \sum_{i=1}^m (\hat{y_i} - y_i)^2,$$

where $$m$$ represents the number of training examples. Let's rewrite this as the following:

$$ J(\theta) = \frac{1}{2m} \sum_{i=1}^m (h_\theta(x_i) - y_i)^2.$$

Even though this looks a bit strange, it's the same equation. We're just going to rename $$J$$ to be our *cost function*, which takes in $$\theta_0$$ and $$\theta_1$$ as parameters. Similarly, $$\hat{y}$$ is going to be a function of $$x$$ given some theta parameters. As for that extra 2...you'll see in moment. All we have to do now is to find the values of theta that minimize our cost function. In other words, take steps in the steepest downhill direction until we reach the bottom. This direction is determined by the gradient, $$\nabla J$$ (which involves taking derivatives, or finding slopes along both axes). I thought about $$\LaTeX$$ing the derivation, but opted for an "old(er)-school" way instead:

<img style="display: block; margin: 0 auto; height: 480px" src="/assets/images/grad_descent_2.png">

To conclude, here's the psuedocode for the gradient descent algorithm: 
<a name="algorithm"></a>
>for $$i$$ iterations: 
>
>$$\frac{\partial J}{\partial\theta_0} \leftarrow \frac{1}{m} \sum_{i=1}^m (h_\theta(x_i) - y_i)$$
>
>$$\frac{\partial J}{\partial \theta_1} \leftarrow \frac{1}{m} \sum_{i=1}^m (h_\theta(x_i) - y_i)x_i$$
>
>$$\theta_0 \leftarrow \theta_0 - \alpha \frac{\partial J}{\partial\theta_0}$$
>
>$$\theta_1 \leftarrow \theta_1 - \alpha \frac{\partial J}{\partial \theta_1}$$

Note that we've included a factor $$\alpha$$ called the *learning rate*, which controls how "big" our steps are.

### Intuition 
To test your understanding, let's take a short field trip to the French Alps. 
<div style="text-align: center"><iframe src="https://www.google.com/maps/embed?pb=!1m0!4v1507448209620!6m8!1m7!1sxveCv-9TE4YXuYVd7q3AEg!2m2!1d44.34113458961325!2d6.857884756335238!3f135.90640697364665!4f-46.35339039307856!5f0.7820865974627469" width="760" height="500" frameborder="0" style="border:0" allowfullscreen></iframe></div>
<div style="text-align: center"><iframe src="https://docs.google.com/forms/d/e/1FAIpQLScKG5EJ7nHT4l0XBgXKg23RGm7yb8ugO3eLkIivLJsxHNN5kg/viewform?embedded=true" width="760" height="500" frameborder="0" marginheight="0" marginwidth="0">Loading...</iframe></div>

Once you're satisfied with your score, try implementing gradient descent in "main.py" [above](#code). Don't forget to set a few learning rates, plot the cost versus number of iterations (already done for you), and compare the results! 

Fortunately, in the time it took to wade through that explanation, our coffee has cooled enough to analyze and I've covered all the technical tools needed to do so. Next time, we'll go into the interesting details and finally reveal a winning strategy (edit: [it's posted][5]!). Along the way, we'll walk through multivariable regression, stochastic gradient descent, and data standardization. Until then, enjoy this visualization I made encapsulating the main ideas.

<script src="https://www.khanacademy.org/computer-programming/gradient-descent-visualization/5485161012199424/embed.js?editor=yes&buttons=no&author=no&embed=yes"></script>

[1]: http://www.coolmath-games.com/
[2]: https://www.coolmath-games.com/0-bloons-tower-defense-1
[3]: https://en.wikipedia.org/wiki/Tensor
[4]: http://www.coolmath-games.com/0-coffee-shop
[5]: {% post_url 2017-11-07-gradient-descent-part-2 %}