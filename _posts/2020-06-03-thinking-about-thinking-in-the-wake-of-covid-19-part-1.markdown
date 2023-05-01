---
layout: post
comments: true
title:  "Thinking About Thinking in the Wake of COVID-19"
date:   2020-06-03 14:10:51 +0800
categories: Research
tags: ['covid', 'pandemic', 'metacognition', 'knowledge tracing', 'deep learning', 'SRL']
excerpt_separator: <!--more-->
---

It's been quite a while since I've updated this website (and blog), but I suppose there's
no better excuse than a pandemic to find new hobbies and restart old projects. Since I first shared the educational materials on this site, I've (apparently) been grad school for over 2 years and, as part of my candidacy requirements, have the great ~~burden~~ opportunity to dig into an area of interest. I hope that the act of writing a blog post will help me organize my thoughts and inch closer to what it precisely is that I am interested in researching, and serve dual purpose as a time capsule of my personal and professional thoughts.

Now with that complete, I'll move on to our main motivation: synthesizing knowledge regarding metacognition, in which the current pandemic will serve as a backdrop for this discussion about how people think and how we teach people to think. But, cognition and metacognition can (obviously) relate to many more things beyond what is discussed here. Roughly 3 months ago, when much of the lockdowns were first imposed, a friend and I were discussing the diagram below:

<img src="/assets/images/coronavirus_flattening_curve.jpg"/>
<!--more-->

While there are many non-Michigan-branded varieties of this plot, the general phrase "flattening the curve" should be familiar to most. I recall my colleague mentioning how elegant and simple this picture was and how it was difficult to fathom how people couldn't understand the urgency of the situation. Yet, if we dissect this piece-by-piece, it's actually a lot of knowledge packed into an "accessible-looking" figure, and a fun exercise in avoiding the ["expert blind spot"][1]<a href="#one"> \[1\]</a>, otherwise known as that feeling when you're in class and the instructors' explanation goes over everyone's head, or when a textbook says "the proof is left to the reader (or is evident)" and the reader has no idea how to connect the dots.

For starters, comprehending this figure requires one to have basic mastery of knowledge components regarding reading graphs. This means looking at the x-axis and understanding that it is temporal, that the y-axis is the number of people sick at any given time, while also realizing that the exact dates are not relevant for the main idea this diagram is trying to convey. Then, we must know that the 2 overlaid curves involve 2 different scenarios: one with preventative measures and one without. Finally, the horizontal line represents the capacity a hospital can treat at any given time and that this is fixed, at least in this representation (more on that later).

We must utilize knowledge, which I'll loosely define as "information about things or processes," and [cognition][2]<a href="#two"> \[2\]</a>, which is an umbrella term that includes thinking and all the mental processes that help us collect, maintain, create, and make sense or use of knowledge . You might be familiar with [Bloom's taxonomy][3]<a href="#three"> \[3\]</a> for instance, which is a rough hierarchy (the upper two tiers are perhaps more or less on the same level) of educational objectives. The updated version published in [2001][4]<a href="#four"> \[4\]</a> incorporates knowledge and cognition as its own dimensions and is shown in the picture below:

<img src="/assets/images/blooms_taxonomy_revised.png" width='800'/>

So, in the example above, we have mainly focused on "remembering" and "understanding", and even then there are quite a few moving gears, before accounting for analysis and evaluation. To dive deeper into what I mean, the "number of sick people" is actually rather difficult to understand as this is represented by the area under the curve, or a sum of the number of people sick captured across a series of time slices (yay calculus!). Assuming all that registers, we might then ask questions such as whether or not the total number of infected people will decrease as a result of preventative measures, or remain stable with cases simply spread over time to avoid overloading hospital capacity. 

One might even begin to "evaluate" the model and ask if the capacity is truly fixed. More health care workers might become sick as there are more patients, or more temporary facilities may be constructed which might yield a slight boost and morph the horizontal threshold. All of this only scratches the surface regarding societal consequences (e.g. how overloaded hospitals affects treatment of other ailments, weighing who gets treatment, anticipating public response, etc.). Even then, one can argue about which of these nuances are significant enough to warrant the added complexity in our model. 

As I've shown, even if we can identify individual components (not moving past the second level of the taxonomy), it can still be hard to really understand the full picture. This is especially difficult if someone already has a preconceived hypothesis or conclusion in mind. Thus, having an informed opinion requires us to judge our own understanding, identify this gap in knowledge (and it's sometimes hard to know what you don't know!), figure out when and where to fill this gap, have the strategies to learn from other sources, and actually muster up the motivation to set these plans in motion. In other words, knowing and thinking alone are often not enough; we need "thinking about thinking," or in other words, metacognition. To end, feel free to explore some of the ideas here with a cellular automata epidemic simulation and an exploratory analysis video as well.

<style>
#iframe-wrapper {
    position:relative;
}
#iframe-overlay {
    height:370px;
    width:350px;
    background-color:#fff;
    position:relative;
    top:-375px;
    left:450px;
}
</style>
<div id="iframe-wrapper">
<iframe width="100%" height="468" id="automata" src="https://ncase.me/sim/?lz=N4IgtgpgLghiBcoAmEDOBjATgSwA5WwHsA7BEQXg3AMPYAIB1CAG3UMmqkOoFExCArbagGVsYAK4MY7TAEJqVADrFFACQiYIAclTVULCNQgAPGGFwM0bDqlwxMAa2oBPQqMzURMAObZikosXhqAApmXEcAWhtUKH0GHzttACNGQgB3AEpFRXJAUl3qADFCdWiC7GLgqAALbG0SfWdRDXUdCAgfT2lM4iDABMJqAGEAGQBJfoBpahI2Sv1PHCRLaiwISX0YagAzMogu7MAAna5cbBQwbHRURUqoKFxUeAB6e+J0GFQIADpIe9QRe4B+VAAXh+6DsWWIgB4NwAc+wMSKkYI4tNQAOImfSEDbUQbYDYQS7XW4PJ4vN6fCDfX4AwHMYjwxzg8iAFl3qAAhcIALQGM1OLwYQiOmBgDAuxCuNzuj2erw+Xx+YH+QMSAC8GYBOHaE6BmDDixE8SMEEDmhr8UwAsoQUAx8eKiVLSbLKUCMFqdZ5wYA+DcAUbvUAAK6iQkiK4T9EEc1HNluthMlJJl5LlCsBuHU9KUkMAa-u+zCEdAQJCuIUMMPIiDENSrBYslaatBRiXE6VkinyqnJGCahmABD3qABtFkSYgOYRgAC6FQ4YBgdnqLjcaWIXTF0Yb9vjjsBiQHYLTAE0XEsYMQDEhsFBpvoYoYzz5qABBAByO8mmKqaAvRigiUIhjQABp3M8DCiCeurTDUkxlu8XKHp4F4zNQmDiBYABkBg8Pw1DJAwaSLJO07UGWqQ6CIqBQfkPiFo4-4NAeR6CLeABqnDUIeCyCMot4AErMQ0bhyu84LKDAABu+gbKIxCyBCgCR+yAv4gEggqpAgACM8kbLcCAAKzyWYCIIFAiEQAAvvJ0SrKgCA9qAxwIAADPJZwkGQckgL4kBkBAphQI4rntgQJCWfAPYjvJKAYDg+D+J53lhtYhBQCApk2UgqmOTSZDuoARLuue5EBkD4uLoDEqXyf5-hBdZIA+bg+XwCAOIAPqCsQSAsK5yaEIkMCJNgcQ+fZ7x2QAzGVxUVVZoA1XVICeIQjXsI15kxK5y0QMMAAiZDDX542BVZI7GYdv6gJ13W9f1vnwHZQ0AExjQFxCVaAa2bWQWmudNZBzQt81rUloXVY4tUFRszWse1yUgGdPV9aeV03SND0TcFL2wDEb31QAbJ9wMzT9i3-Ud8lffVTUtW1YBJSdIDWO2dUObTuAJYI6PrVt13yeYIkQKzqyY4zpPgIQom-QDYVoFgeCPWQVSEG81CpJUHC2PohUQMVebBG1FjEAl1CTtcajuJitWYLoR7gagjjeSwfjoOk1MpQg90NRl9XkIAQnu5WiZCoKIGAQFFm75cj+2o7T2CeKQ9UAHyArlohU-Aam02zmMgCpu2Pc90PZudcMDdd7yp+V4dVa9HOZ7jIP1QTf1s+LQO1w1YMU5DgNC01ZZR5UX6YE7kfR2Q8eJ8nruV2QAAs2co1VMMXfDg2l3tT2TWn-NVzPJN49982E43xPNzN5MQ1TR9d2DPeeH3RSDz8w9xwn8nEEnLtmenVc7WHa8RwvhcIyGjpEAZdf4V0-tPGu+N94N1WE3S+4NWodx3i3bubQb793vjYXM9kzLMygHzDGHNGbc1EoQ9muDj5kB4KLdgTdwpSyis5eqh5JivkwKkGo+gZhCiqGGM2Fs2BTnaARDgH5BTUGTBrGAogc6D1svAUabtmEgHdIAVF2fYeXquoZgol-SuQYZFGW2ig7FFLFAbQcsFZKw4JUHmCENYizUFrDY2YwDnmoCeN40pZ7lxetghmeCWYQM5iAUhvMQmC13vVGhEAxZHShgoqe6UVHkEAOx7miZpSNEsQdG2BRIGMlkY6K9UBFTFgHYER2TzF+FEgbFY-tyj+01CxSxgpRJ8hIEWTYRQDCoDeLk7AQohGoASP+DY9MDavDsP+XQ6Ahl8i8bAZ47R-zQHQO8XxYCXpRxjiAUeL834pw-pvMgWcf653-pdQadlgGgNzpPeq5yqF1xgUtQ+ndomt0QZTeBXy0G90wVDB+eyDluSOanR5IBbpbMufnWG1zi4rzkRHKFMKUHQN+u8uBF9-ltzPn81BV90G3wHsCgJlD4oEMiVzFYZCaUvOFrQwgANEmpXgMApyeyISAFP9zJZBlbWFPEKbASo8yFIitLEpIAACOohbCHgIGWBYrwWIOP9gwM8GIWJHiKCgTA9waSGX8mwQU8zQKdVzPmYo-5emCqOLAOIYqFhBFeP7U4oEPUeD5OJTA7DTWHlQKcfp-hHYXPXlcpeSLw2opCSAb+jL67YpWriolPzIY00jUXRGdzV4PLjQAdigXvLFRNPlpvbufY6zt4BYxSXs8ggB2vf5fVOVCrBnKolYw4xtNGAbHCCIZmbwFi9MnK1QMmAwxtpakq-QQRhJDKWCQWAxUA3ms8JMOc-rIByyQKgMNIC80RvhYvbNJcY3gNOfVBNQsk1loxaDdNVa2UIALfWsg5A9gtoUhrBp4qJaSqYXs9QUiBkWOmPLOCkhqB2LqSeFxbiPFeL-bCg6R9UhFAYOy0AohcABhWvVOU4hlkQBcJZF+JL+7KwtNQwgRRQ550IMzP1c80ZXsZjYP1QUsbDWBSE1OnGLH2T41e12gmgrDQLSJohCAlHieEzTR5yToa2CE9daTFCOW6VU0FOyGnMZ1pU1xhTbGZPwDfUZtTenAY-DFQgUAnCkBVAQFPRmMxe6JUUbx4yxkgA" frameborder="0"></iframe>
<!--<div id="iframe-overlay"></div>-->
</div>

<div style="text-align: center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/gxAaO2rsdIs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

[1]: http://pact.cs.cmu.edu/pubs/2001_NathanEtAl_ICCS_EBS.pdf
[2]: https://opentext.wsu.edu/psych105/chapter/7-2-what-is-cognition/
[3]: https://cmapspublic2.ihmc.us/rid=1Q2PTM7HL-26LTFBX-9YN8/Krathwohl%202002.pdf
[4]: https://www.celt.iastate.edu/teaching/effective-teaching-practices/revised-blooms-taxonomy/
