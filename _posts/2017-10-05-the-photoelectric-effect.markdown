---
layout: post
comments: true
title:  "The Photoelectric Effect"
date:   2017-10-05 14:10:51 +0800
categories: Tutorials
tags: ['physics', 'lab', 'education', 'photoelectric effect', 'khan academy', 'history']
excerpt_separator: <!--more-->
---
A while back, I created [a small demo][1] on Khan Academy. Since I've decided to use this blog to post educational material (and other things that I have yet to decide on), I figured that I may as well take the time to share and flesh out a mini lesson plan. Of course, after I found a way to embed Processing.js, I realized that the default angle mode is in radians while Khan Academy defaults to degrees. As a result, the CodePen snippet below has some hacky-looking modifications from the original, but it's mostly identical. Either way, this is a good reminder to 1.) use radians from now on, and 2.) work on factoring out more constant variables so that I don't have to go on a programmer's version of hide-and-go seek. With that mental note out of the way, onto the lab!
<!--more-->
## Background 

There are already lots of great resources explaining the [history][2] behind the photoelectric effect and the phenomenon itself. Consequently, in an attempt to provide something with a twist, I've decided to opt for an exploratory approach. With that said, I'll still provide a brief recap so that we can "stand on the shoulders of giants". 

Once upon a time, there was a great light debate. On one side was the wave theory of light, and on the other side was the particle theory. Christiaan Huygens, a Dutch physicist, argued that light behaved as a wave and that each point of a wavefront was itself a source of radiation that propagated outwards with the same frequency and phase. He published this result in 1678, now known as Huygens' Principle, in his *[Traité de la Lumière][3]* (*Treatise on Light*). 

<table class="image" align="center">
<caption align="bottom" style="font-size: 10pt">Huygens' Principle by Arne Nordmann - Own illustration, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=1944668</caption><tr><td><img style="width: 400px" src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/60/Refraction_on_an_aperture_-_Huygens-Fresnel_principle.svg/500px-Refraction_on_an_aperture_-_Huygens-Fresnel_principle.svg.png" alt="Refraction on a aperture"/></td></tr>
</table>

Huygens also attacked Issac Newton's particle theory of light, rightfully claiming that his theory could not explain diffraction (bending of waves around obstacles), interference, and other phenomena. Newton countered in his 1704 publication *[Opticks][4]* by claiming that particles created waves in the "aether", a magical medium that was believed to exist throughout space. Both theories would be proven wrong. 

<table align="center" style="margin-bottom: 10px">
	<tr align="center">
		<td>Diffraction</td>
		<td>Interference</td>
	</tr>
	<tr align="center" style="font-size: 10pt">
		<td style="padding-right: 10px">
			<figure>
				<img style="width: 280px" src="http://ircamera.as.arizona.edu/NatSci102/NatSci102/images/water_diffraction2.jpg"/>
			</figure>
			<figcaption>
				Wave diffraction photo from Exploratorium. <br>CC BY 3.0 US.
			</figcaption>
		</td>
		<td style="padding-left: 10px">
			<figure>
				<img style="width: 260px" src="http://static.nautil.us/2895_6b8b8e3bd6ad94b985c1b1f1b7a94cb2.jpg"/>
			</figure>
			<figcaption>
				An illustration of wave interference <br>by Sybille Yates via Shutterstock
			</figcaption>
		</td>
	</tr>
</table>

With that said, Newton's fame did popularize the particle theory initially, but wave theory gained traction by the 19th century. In 1887, Heinrich Hertz set up a spark gap transmitter as part of an experiment to detect electromagnetic waves. However, he noticed that sparks were more vigorous when the device was exposed to ultraviolet light. This was bizarre considering that classical wave theory states that the intensity of the light determines the amplitude of the wave, which would in turn vibrate the electrons on a piece of metal more rapidly and eject [photoelectrons][5] with greater kinetic energy. What did frequency have to do with anything?

<div style="text-align: center; margin-bottom: 10px"><iframe width="560" height="315" src="https://www.youtube.com/embed/YSf93g0heUA?rel=0" frameborder="0" allowfullscreen></iframe></div>

Hertz concluded that "...I confine myself at present to communicating the results obtained, without attempting any theory respecting the manner in which the observed phenomena are brought about." Fortunately, JJ Thompson and Philipp Lenard set out to explore this behavior in the following decade, which we'll be replicating below.

## The Setup

1. We've set up a lamp to shine over the negatively-charged metal plate. There's a [really neat adjustable lightbulb][6] where you can change the color of the light. In addition, it comes with a dimmer so you can crank the intensity up or down to your liking. 

2. On the other end is an electron collector. Notice that it's positively charged so that electrons will be attracted to it. This can be accomplished by hooking up a variable power supply in series with the circuit shown below. Let's just pretend it's already hidden behind the ammeter.

3. If you need to reset everything to the initial setup, don't worry, we've hired a lab assistant. Simply click the "rerun" button in the lower right corner. 

---

<p data-height="490" data-theme-id="dark" data-slug-hash="eGMNyj" data-default-tab="result" data-user="Liwmo" data-embed-version="2" data-pen-title="eGMNyj" class="codepen">See the Pen <a href="https://codepen.io/Liwmo/pen/eGMNyj/">eGMNyj</a> by Warren (<a href="https://codepen.io/Liwmo">@Liwmo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

---

## Questions (Part 1)

1. Let's start off with red light ($$\lambda=750$$ nm) and the sodium plate. Go ahead and play with the light intensity. What do you notice?

2. Next, we'll fix the light intensity at some mid-range value. Now, slowly adjust the color. At what *frequency* are electrons finally ejected? What is the current through the wire?

3. What happens to the electrons as you decrease the wavelength further? Construct a plot of current versus wavelength using quantitative data, and sketch a qualitative plot of photoelectron kinetic energy vs frequency.

4. Double the light intensity (you can assume that slider values scale linearly from 0% to 100% brightness). What is the new current? Feel free to repeat this procedure with various starting points. With this knowledge, what does the relationship between current and intensity look like?

## Break Time
Prior to the 20th century, Max Planck had already hinted at the fact that electromagnetic energy was *quantized*. That is, energy took on *discrete* values given by $$E=hf$$, where $$f$$ represents frequency and $$h \approx 4.136 \cdot 10^{-15} \text{ eV} \cdot \text{s}$$ is a number we now call Planck's constant. Planck only applied this "mathematical trick" in an attempt to get sensible results, but Albert Einstein saw this as the key to understanding the photoelectric effect. 

Before we move on to the explanation, let's take some time to acknowledge how counter-intuitive it was (and still is) for nature to be discretized. Sure, one can count number of items, say 5 apples, and note that counting numbers are discrete. However, in our physical world, you're still able to cut an apple in half and get 1/2 an apple, 0.3692 apples, or any other continuous value. The food we eat is not quantized and we think of heights as continuous numbers; we don't grow in exact 0.5 inch increments. 

With that aside, we're well on our way to the quirkiness of modern physics. Let's think of our experiment as a collision. Then, according to the law of conservation of energy:

$$ hf = KE_{max} + \Phi $$

where $$ hf $$ represents our *photon* (a quanta of EM energy) before the collision, $$ KE_{max} $$ is the kinetic energy of an electron after the collision, and $$ \Phi $$, which we'll call the *work function*, is the energy required to eject the electron in the first place. Fun fact: Einstein won the Nobel prize for his [insight into the photoelectric effect][7], not relativity. 

## Questions (Part 2)

1. If we shine blue light ($$\lambda = 450 $$ nm) onto a cesium plate, what is the maximum kinetic energy of an emitted electron in electron volts?

2. Answer question 5 again if we replace cesium with calcium (this is a bit of a trick question). 

3. For question 5, what is the velocity of the photoelectron in km/s?

4. A photon with a momentum of [$$0.005 \frac{\text{keV}}{\text{c}}$$][8] has just enough energy to eject an electron from some material. Indicate the [transition metal][9] with which this material is most likely composed.

5. Let's say we try to apply a potential difference between the plate and collector so that it's just enough to stop an electron from reaching the collector. This *stopping voltage* $$ V_0 $$ is found to be $$0.72 \text{ mV}$$. In our setup, we're using photons with an angular frequency of $$\omega = 5.4 \cdot 10^{-15} \text{ s}^{-1}$$ and a silver sample, which has a work function that depends on the face of the crystal (see resource below). Determine the corresponding face.

<iframe frameborder="0" width="100%" height="500px" src="https://repl.it/@Liwmo/Photoelectric-Effect-Quiz?lite=true"></iframe>

That's it! The photoelectric effect demonstrated the particle-like properties of light and eventually gave way to the [wave-particle duality of photons][10]. To conclude, here's a short video of a physical experiment:

<div style="text-align: center"><iframe width="560" height="315" src="https://www.youtube.com/embed/kcSYV8bJox8?rel=0&amp;start=3" frameborder="0" allowfullscreen></iframe></div>

[1]: https://www.khanacademy.org/computer-programming/photoelectric-effect/4809986404909056
[2]: http://galileo.phys.virginia.edu/classes/252/photoelectric_effect.html
[3]: https://books.google.com/books/about/Trait%C3%A9_de_la_lumi%C3%A8re.html?id=No8PAAAAQAAJ
[4]: http://www.relativitycalculator.com/pdfs/Opticks_by_Sir_Isaac_Newton.pdf
[5]: http://www.dictionary.com/browse/photoelectron
[6]: https://www.amazon.com/Cxy-APP-Smartphone-controlled-Multicolor-Equivalent/dp/B0721L1FPK/ 
[7]: http://astro1.panet.utoledo.edu/~ljc/PE_eng.pdf
[8]: http://quarknet.fnal.gov/toolkits/new/whatgevs.html
[9]: http://chemed.chem.purdue.edu/genchem/topicreview/bp/ch12/trans.php
[10]: https://ed.ted.com/lessons/is-light-a-particle-or-a-wave-colm-kelleher