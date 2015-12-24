Title: Seeking the Source - Why I Started Up a Data Blog
Date: 2015-12-21
Category: Personal
Tags: Philosophy, Math, Fibonacci
Author: Kevin
Email: kevhung11@gmail.com
about_author: Data Evangelist who synthesizes science &amp; spirit to tell his data stories!

### A Quest to Know

So.. why did I start blogging? How did my background lead me to a venturesome pursuit? Simply, I desire to know. I aim to understand "science", to expand my intellectual horizon and challenge cognitive limits. Just as more, a chance to question myself - who am I?

> ## [γνῶθι σεαυτόν <i class="fa fa-volume-up"></i>][1]
>
> "Know Yourself"<br />
> [gnōthi seauton - Pythagoras][2]

I originally asked a good friend. What first appeared as an external confirmation for identity, I realized later, was actually a constructed veil for an internal sense of purpose. Near the completion of engineering education at university, I felt uncertainty and the slightest doubt of indescribable dissonance. Not from the good quality of learning I've been blessed with, but my personal place in a bigger picture, the grand scheme of the cosmos! Our light dialogue ended when he asked, "Do you know there are only nine original stories?"

Another sense of uncertainty (but hopeful this time) dawned on me, as I'm sure we just had an atypical kind of conversation. Fast forward a few months, I'd been recreationally skimming through prospective book titles and attempting to understand  narrative structures. And now I see that my good friend had inadvertently given me a fixup cure: stories possess a therapeutic effect for easing unrestful souls like mine! A metaphoric "mental defragmentation."

One last week right before completion of college, I noticed my good friend looking distressed. So I mentioned a short philosophical text I picked up in the hope of healing him, and as grateful reciprocation for his previous aid. I exposed and elucidated his anxiety by pointing out, "Do you have any plans?" At loss for words, he naturally felt worry and uncertainty for the future, like many in our cohort. Of course I can empathize.

I texted him

> ## [善行無轍跡 <i class="fa fa-volume-up"></i>][3]
>
> "A good traveler leaves no tracks<br />
> (has no fixed plans, and is not intent upon arriving)" - [Tao Te Ching][4]

In our time as sojourners on this ephemeral world, we strive to make our mark known on the face of the earth throughout our journey. We fret and worry about the dreams, ambitions and lofty plans enforced upon ourselves that we feel an obligation to pursue. Ideals and standards we try to be, but which are not meant to be. At the cost of discovering one's true path and searching, listening within one's soul. The source of who we are. Who I am.

![Who are you?](images/mirror.png)

<div class="center"><i>vintage mirror - find on <a href="http://www.etsy.com/listing/130210865/vintage-large-round-wall-mirror-30" target="_blank">Etsy</a></i></div>

I'm still searching, for now, but at least I'm no longer overly stressed out like before. I have friends and I will find it!

### Starting Up Any Project: A General Guiding Principle

What is my philosophy in creation? That something can be made out of nothing. *Ex nihilio*. Wow! Isn't that empowering and downright inspirational? Or maybe a bit too much mysticism for the skeptical folks out there. How exactly, you ask, can that be possible since it must obviously violate the very laws of physics. Well, I'll be transparent and honest with you, and say I'm no qualified physicist or doctor like university professors are (and certainly no serious practitioner of ["Vortex-based mathematics"][6] *though Nassim Haramein did come to our school for a TEDX talk this year). But whoever asked you to interpret it so literally? Let's describe it as a metaphor and learn something cool.

Here's a refresher if the narrative sounds unfamiliar: "In the beginning God created the heavens and the earth."
There was darkness, formlessness and emptiness - capture [this idea as the symbol][7]

$$0$$

"... and there was light." Write down this idea that can symbolize singularity

$$1$$

Sum our two friends up and we can describe an infinite set of whole numbers

$$0+1=1, 1+1=2, 1+2=3, 1+3=4, 2+3=5, 2+4=6,...$$

Together, light and darkness can create it all! In the presence of darkness, thousands of candles can be ignited from the light of a single candle. Two of our precious gifts also form a ubiquitous sequence found throughout nature

$$..., 0, 1, 1, 2, 3, 5, 8, 13, 21, ...$$

![Nautilus Shell][8]

<div class="center"><i>a nautilus shell - pic by <a href="http://www.earthintransition.org" target="_blank">earthintransition</a></i></div>

A sequence which can be captured by a recurrence relation, interchangeably

<div id="recurrences"></div>
$$\begin{align}
F_{n+2} &= F_{n+1} + F_{n} \\
F_{n} &= F_{n-1} + F_{n-2} \\
F_{n+2} &= F_{n+1} + F_{n} \text{ (for negative integers!)}
\end{align}$$

seeded by none other than our trusty friends
$$\begin{cases} F_0 = 0 \\ F_1 = 1 \end{cases}$$

and computer-codable in a familiar language (at least to me hopefully), Python!

	#!python
	def fib(n):
		""" calculate the nth fibonacci number
		
		Keyword arguments:
	    n -- a whole number
		"""

		if n==0 or n==1:
			return n
		else:
			return fib(n-1) + fib(n-2)

We can also write it, in addition to the recursive style above, iteratively as well

	#!python
	def fib(n):
		""" calculate the nth fibonacci number
		
		Keyword arguments:
	    n -- a whole number
		"""

		if n==0 or n==1:
			return n
		else:
			f0 = 0
			f1 = 1

			for _ in range(n-1):
				fnext = f1 + f0
				f0 = f1
				f1 = fnext

			return fnext

and extend it to negative numbers. Since given [$(3)$][9]

$$\begin{align} F_{n-2} &= F_{n} - F_{n-1} \\
F_{-n} &= (-1)^{n-1}\cdot F_{n}\\
\end{align}$$

e.g.: $... 5, -3, 2, -1, 1, 0, 1, 1, 2, 3, 5, ...$

	#!python
	def fibonacci(i):
		""" calculate the nth fibonacci number
		
		Keyword arguments:
	    i -- an integer
		"""

		if i >= 0:
			return fib(i)
		else:
			posi = abs(i)
			sign = (-1)**(posi-1)
			return sign*fib(posi)

where `fib` is defined in the previous codeblock to demonstrate code reuse (be re-source-ful!)

[1]: http://goo.gl/6yv3dQ "'Know Yourself' - Greek"
[2]: http://en.wikiquote.org/wiki/Pythagoras "Pythagoras"
[3]: http://goo.gl/cqePXp "'Good Travel has no Tracks' - Chinese (traditional)"
[4]: http://en.wikiquote.org/wiki/Laozi "Lao Tzu"
[5]: http://www.etsy.com/listing/130210865/vintage-large-round-wall-mirror-30 "Snapshot Vintage Mirror"
[6]: http://www.quora.com/TEDx/Is-Randy-Powell-saying-anything-in-his-2010-TEDxCharlotte-talk-or-is-it-just-total-nonsense "Vortex Math"
[7]: http://www.storyofmathematics.com/indian_brahmagupta.html "Brahmagupta"
[8]: http://www.earthintransition.org/wp-content/uploads/2012/08/nautilus-golden-ratio-080212.gif "Nautilus shell"
[9]: #recurrences "negative fibonacci numbers"