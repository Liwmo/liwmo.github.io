---
layout: post
comments: true
title:  "On the merits and follies of hand-written code"
date:   2017-11-15 14:10:51 +0800
categories: Teaching
tags: ['teaching', 'experience', 'pedagogy', 'coding', 'programming', 'logo', 'launchcode']
excerpt_separator: <!--more-->
---

If you've been in a computer science class, you're bound to hear someone complain about hand-written code during tests or quizzes at some point or another. Oftentimes, the debate goes something like this:

*Oblivious Student: "This is so stupid and unrealistic. When will I ever have to hand-write code?"*

*Old-Fashioned Professor: "This is an important and fundamental skill--think about the job interviews!"*

Fair enough. For instance, there are plenty of books and articles about technical interviews and this video to guide applicants towards that coveted position at Google:

<div style="text-align: center">
<iframe width="100%" height="315" src="https://www.youtube.com/embed/XKu_SEDAykw?rel=0" frameborder="0" allowfullscreen></iframe></div>
<!--more-->

On the contrary, you also occasionally come across this,

<img src="/assets/images/handcode_1.jpg"/>

might feel a bit more trivial. 

Admittedly, while there will always be some level of subjectivity when grading, the [AP Computer Science grading guidelines][2] seems to agree with this interpretation (see the "No Penalty" section on page 2). The purpose of an assessment is to *assess*, provide insight into student learning and guide teaching. 

----------------------------------------------

As a student, I too was skeptical when it came to hand writing code. Yet, my stance shifted when I taught my first course for LaunchCode. I met biweekly with a group of roughly 20 students from various backgrounds who had little to no coding experience. The first unit of the program covered essentials such as variables, operators, control structures, etc.

Loosely mimicking a flipped-classroom model, students would go though a majority of the prep work and instruction at home, come in for an auditorium-style lecture, and then split up into respective classroom-sized groups. At that point, we (the teaching fellows) would handle things on our own accord. We were provided in-class materials for each session. Consequently, I would read it over, maybe make a few comments or adjustments, and then encourage everyone to form groups. After allowing everyone some time to figure things out, I would start making my way around the classroom, trying my best to speak with each and every student.

<img src="/assets/images/handcode_3.png"/>

The first few projects were fairly smooth, but it didn't take long before I noticed issues. Specifically, when students were finished, I tried gently probing them with a few questions such as why did you use `elif` instead of `else`? What does this function do? Can you walk me through your code? Some were able to discuss their process, but I also had many blank stares, and some refreshingly honest answers like, "I have no clue what I did. I just kept typing stuff until the errors went away." 

In all fairness, experimenting around is a great way to learn. My earliest exposure to programming involved playing around with KTurtle years ago, which is an educational programming environment that uses a language based on [Logo][3]. During this phase, I attempted an Oregon Trail knockoff as well as a half-finished calculator for computing "taxes" that I wanted to collect from my cousin's account on my Animal Crossing game. The spaghetti code resembled something like this:

```php
if $a == 'apple' {
	if $b == 'stalks' {
		if $x == 1 {
		   ...
		}
		if $y == 2 {
		   ...
		}
		...
	}
	if $c == 'sea bass' {
	   ...
	}
	if $d == 'dung beetle' {
	   ...
	}
	...
}
if $a == 'orange' {
	...
}
...
```

Somewhat functional, but ugly and hard to modify. Perhaps, I would have eventually developed more descriptive variable names and organizational skills, but sometimes, gentle guidance in an open sandbox can help accelerate the learning process tremendously.

With that in mind, I decided to have the class split into four groups. To provide diagnostics, I passed out a no-computers-allowed "quiz" to one group (which made some people uneasy, even without formal grades), and then helped out other students with the in-class project. Afterwards, I would return to the quiz takers and discuss questions, misconceptions, and so forth before repeating this procedure with the remaining groups. Of course, it took some gesture-reading and words of encouragement to ensure everyone was on the same page, but generally, the small circle seemed to alleviate students' reservations about sharing wrong answers, and the lack of a compiler meant everyone had to think about what was occuring.

Here's a sample:

<img src='/assets/images/handcode_2.jpg' width='80%'/>

The key concept is that `return` will immediately exit out of the function, and so the `print` statement below is effectively *invisible* (mediocre joke, fair enough). Anyway, when I asked for feedback, many students expressed that these exercises were very helpful and surprisingly requested more, thus I had a rather [fun time writing them][6]. 

<iframe src="https://docs.google.com/document/d/e/2PACX-1vRGqgtVUQF5Erze-UU_I1IH34KYuRblxZXkoISz8REHYZOhPtqGtTI9uZClAwt-FVhJTTx0oFJhd76K/pub?embedded=true" width="100%" height="500px"></iframe>

I also have a link to the [Thanksgiving edition][4], and the [Polar Express Christmas edition][5], which ramps up in difficulty just a tad and involves writing a few lines. The objective of the final quiz of the semester was to provide some practice with classes and inheritance, especially since we were feeling rushed. As a result, I also made my first teaching video. It's not my best work, but I thought I'd share:

<div style="text-align: center">
<iframe src="https://drive.google.com/file/d/0Bxka66Mq1AW0bzR5QjlyNWd2T0E/preview" width="560" height="315"></iframe></div>

The exhilarating sequel can be found [here][7]. All in all, students really seemed to appreciate these additional resources, and I suppose what I'm about to say won't be all that surprising: writing code can be a good exercise that forces one to pause and ponder about what's going on behind-the-scenes. However, like most educational tools, your mileage may vary. If the questions are crafted and evaluated with particular goals in mind, you're likely to see better results, and if you use a meter stick to measure weight, then the only result will be nonsense.

[1]: https://en.wikipedia.org/wiki/Object-oriented_programming
[2]: https://secure-media.collegeboard.org/digitalServices/pdf/ap/ap16_computer_science_a_sg.pdf
[3]: https://en.wikipedia.org/wiki/Logo_(programming_language)
[4]: https://drive.google.com/open?id=0Bxka66Mq1AW0ZTF1ZkRfc3l6ZGc
[5]: https://drive.google.com/open?id=0Bxka66Mq1AW0QnV4N05yblhGeFU
[6]: https://drive.google.com/open?id=0Bxka66Mq1AW0TmhCUll5MFZ5OTA
[7]: https://drive.google.com/open?id=0Bxka66Mq1AW0MlYzSWJlTXM4aVE