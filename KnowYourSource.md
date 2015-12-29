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

I originally asked a good friend. What first appeared as an external confirmation for identity, I realized later, was actually an internal sense of purpose misguided. Near the completion of engineering education at university, I felt uncertainty and the slightest doubt of indescribable dissonance. Not from good quality learning I'd been blessed with, but confusion arose from the scale of my personal place in a bigger picture, the grand scheme of the cosmos! Our light dialogue ended when he asked, "Do you know there are only nine original stories?"

Another sense of uncertainty (but hopeful this time) dawned on me, as I'm sure we just had an atypical kind of conversation. Fast forward a few months, I'd been recreationally skimming through prospective book titles and attempting to understand  narrative structures. And I see now that my good friend had inadvertently given me a fixup cure: stories possess a therapeutic effect for easing unrestful souls like mine! A metaphoric "mental defragmentation."

One last week right before completion of college, I noticed my good friend looking distressed. So I mentioned a short philosophical text I picked up in the hope of healing him, and as grateful reciprocation for his previous aid. I exposed and elucidated his anxiety by pointing out, "Do you have any plans?" At loss for words, he naturally felt worry and uncertainty for the future, like many in our cohort. Of course I can empathize.

I texted him

> ## [善行無轍跡 <i class="fa fa-volume-up"></i>][3]
>
> "A good traveler leaves no tracks<br />
> (has no fixed plans, and is not intent upon arriving)"<br />
> - [Tao Te Ching][4]

In our time as sojourners on this ephemeral world, we strive to make our mark known on the face of the earth throughout our journey. We fret and worry about the dreams, ambitions and lofty plans enforced upon ourselves that we feel an obligation to pursue. Ideals and standards we try to be, but which are not meant to be. At the cost of discovering one's true path and searching, [listening][17] within one's soul. The source of who we are.

![Who are you?](images/mirror.png)

<div class="center"><i>vintage mirror - find on <a href="http://www.etsy.com/listing/130210865/vintage-large-round-wall-mirror-30" target="_blank">Etsy</a></i></div>

I'm still searching, for now, but at least I'm no longer overly stressed out like before. I have friends and I will find it!

### Starting Up Any Project: A General Guiding Principle

What is my philosophy in creation? That something can be made out of nothing. *Ex nihilio*. Wow! Isn't that empowering and downright inspirational? Or maybe a bit too much mysticism for the skeptical folks out there. How exactly, you ask, can that be possible since it must obviously violate the very laws of physics. Well, I'll be transparent and honest with you, and say I'm no qualified physicist or doctor like some university professors are (and certainly no serious practitioner of ["Vortex-based mathematics"][6] **though Nassim Haramein did come to our school for a TEDX talk this year*). But whoever asked you to interpret it so literally? Let's describe it as a metaphor and learn something cool...

![Spiral Galaxy][16]

<div class="center"><i>spiral galaxy - pic by <a href="http://www.thegreatpeacemakers.com" target="_blank">thegreatpeacemakers</a></i></div>

Here's a refresher from one familiar narrative: "In the beginning God created the heavens and the earth."<sup id="Genesis">[\[1\]][14]</sup>
There was darkness, formlessness and emptiness - capture [this idea as the symbol][7]

$$0$$

"... and there was light." Write it down too, an idea that symbolizes singularity

$$1$$

Sum our two friends up and we can describe an infinite set of whole numbers

$$0+1=1, 1+1=\color{red}{2}, 1+2=\color{red}{3}, 1+3=\color{red}{4}, 2+3=\color{red}{5}, 1+5=\color{red}{6}, 2+5=\color{red}{7}, 3+5=\color{red}{8}, 2+7=\color{red}{9}...$$

> ### The Beginning
>
> 1 In the beginning God created the heavens and the earth. 2 Now the earth was formless and empty, darkness was over the surface of the deep, and the Spirit of God was hovering over the waters. 3 And God said, “Let there be light,” and there was light.<br /><br />
> [Genesis 1:1-3 (NIV)][10]

Together, light and darkness can create it all! In the presence of darkness, thousands of candles can be ignited from the light and source of a single candle. Two of our precious gifts also form a ubiquitous sequence found throughout nature

$$..., 0, 1, 1, 2, 3, 5, 8, 13, 21, ...$$

![Nautilus Shell][8]

<div class="center"><i>a nautilus shell - pic by <a href="http://www.earthintransition.org" target="_blank">earthintransition</a></i></div>

A sequence which can be captured by a recurrence relation, interchangeably

<div id="recurrences"></div>
$$\begin{align}
F_{n+2} &= F_{n+1} + F_{n} \\
F_{n} &= F_{n-1} + F_{n-2} \\
\end{align}$$

seeded by none other than our trusty friends as the initial conditions
$$\begin{cases} F_0 = 0 \\ F_1 = 1 \end{cases}$$

for integers $n \geq 0$ (as well as $\forall n \in \mathbb{Z}$!) And computer-codable in a familiar language (at least to me hopefully), Python

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

and extend it to negative numbers. Since given [$(2)$][9]

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
			nfib = sign*fib(posi)
			return int(nfib)

where `fib` function is defined in the previous codeblock to show code reuse. Be re-source-ful! Like nature



The third and final act of our short play will teach us to see our recurrence relationship in another interesting perspective.

We'll now solve for the k<sup>th</sup> entry of the Fibonacci sequence in a closed-form equational fashion, by giving an introduction to the generating function. 

$\bf{Definition} \textrm{ Ordinary Generating Function.}$<sup id="generatingfunction1">[\[2\]][14]</sup><sup id="generatingfunction2">[\[3\]][14]</sup>

$\textrm{Let }\{a_n\}_{n \geq 0}\textrm{ be a sequence of real numbers. Then } F(x) = \sum\limits_{n=0}^{\infty} a_n x^n \textrm{ is an ordinary generating function }\\\textrm{whose coefficients are } \{a_n\}_{n \geq 0}$

<br />
Simply, a generating function counts the number of configurations (coefficient sequences) total $a_k$ for event $k \in \mathbb{Z}_{\geq 0}$

So by converting our recurrence relation $F_{n+2} = F_{n+1} + F_{n}$ into a generating function $\Phi_F (x) = \sum\limits_{n = 0}^{\infty} F_n x^n$ we can find an arbitrary $k^{th}$ Fibonacci term, *the $k^{th}$ event in our sequence*, algebraically

$$\begin{eqnarray} 
F_{n+2} &=& F_{n+1} + F_{n} \nonumber \\
\sum\limits_{n = 0}^{\infty} F_{n+2} \textrm{ } x^{n+2} &=& \sum\limits_{n = 0}^{\infty} F_{n+1}\textrm{ }x^{n+2} + \sum\limits_{n = 0}^{\infty} F_{n}\textrm{ }x^{n+2} \nonumber \\
\sum\limits_{n = 0}^{\infty} F_{n+2} \textrm{ } x^{n+2} &=& x\textrm{ }\sum\limits_{n = 0}^{\infty} F_{n+1}\textrm{ }x^{n+1} + x^2 \textrm{ } \sum\limits_{n = 0}^{\infty} F_{n}\textrm{ }x^{n} \nonumber \\
\Phi_F(x) - F_1 \textrm{ } x^1 - F_0 \textrm{ } x^0 &=& x\textrm{ } [\Phi_F(x) - F_0\textrm{ }x^0] + x^2 \Phi_F(x) \nonumber \\
\Phi_F(x) &=& {x \over{1 - x - x^2}} \nonumber \\
&=& {x \over{1 - (\color{red}{0}x^{\color{red}{0}} + \color{red}{1}x^{\color{red}{1}} + \color{red}{1}x^{\color{red}{1}})}} \nonumber \\
\end{eqnarray}$$

Looking good so far! You can tell that the first three Fibonacci numbers $F_{\{0,1,2\}}$ are encoded in the <span style="color:red">coefficients</span> and corresponding <span style="color:red">powers</span> above. We continue with the technique of partial fraction decomposition to take advantage of the geometric formal power series $\sum\limits_{n=0}^{\infty} x^n = {1\over{1-x}}$ which will come in handy very soon. But what we do need now is to know how to factor $1 - x - x^2 = 0$ using the quadratic formula, which gives us the famous [golden ratio][20] $\phi = {{1 + \sqrt{5}}\over 2}$ as the principal root (and the other root being $\tau = {{1 - \sqrt{5}\over 2}}$) as our solution to $1 - x - x^2 = - (x + \phi) (x + \tau) = 0$

$$\begin{eqnarray}
\Phi_F(x) &=& \nonumber \\
{x \over{1 - x - x^2}} &=& {A \over{x + \phi}} - {B \over{x + \tau}} \nonumber \\
&\implies& \begin{cases}  A - B &=& 1 \\ -\tau A + \phi B &=& 0 \end{cases} \nonumber \\
&\implies& \begin{cases} A = {1\over{\sqrt{5}}} \phi \\ B = {1\over{\sqrt{5}}} \tau \end{cases} \nonumber \\
&\implies& {1\over{\sqrt{5}}} [{\phi \over{x + \phi}} - {\tau \over{x + \tau}}] \nonumber \\
&\implies& {1\over{\sqrt{5}}} [{1 \over{1 - \phi x}} - {1 \over{1 - \tau x}}] \textrm{ (using } \tau\cdot\phi = -1 \textrm{)} \nonumber \\
&\implies& {1\over{\sqrt{5}}} [\sum\limits_{n=0}^{\infty} (\phi x)^n - \sum\limits_{n=0}^{\infty} (\tau x)^n] \textrm{ (given } \sum\limits_{n=0}^{\infty} x^n = {1\over{1-x}} \textrm{)} \nonumber \\
&\implies& {1\over{\sqrt{5}}} \sum\limits_{n=0}^{\infty} [\phi^n - \tau^n] x^n = \Phi_F(x) \nonumber \\
&\implies& {1\over{\sqrt{5}}} \sum\limits_{n=0}^{\infty} [\phi^n - \tau^n] x^n =  \sum\limits_{n=0}^{\infty} F_n x^n \nonumber \\
&\implies& F_n = {1\over{\sqrt{5}}} [\phi^n - \tau^n] { } \nonumber \\
\end{eqnarray}$$

<div style="text-align:right">&#8718;</div>

Yes! What we've done is effectively summed an infinite number of copies of $F_{n+2} = F_{n+1} + F_{n}$ for $\forall n \in \mathbb{Z}_{\geq 0}$ into one generating function $\Phi_F(x) = {x \over{1 - x - x^2}}$, and our result is [Binet's Formula][19]

	#!python
	import math

	def fib_binet(n):
	    """ a closed form implementation of fibonacci
	    
	    KW args --
	    n: a natural number
	    """
	    rt5 = math.sqrt(5)
	    phi = (1+rt5)/2.0
	    tau = (1-rt5)/2.0
	    
	    return int( (1/rt5)*(phi**n-tau**n) )

Indeed, what a great idea we've encountered. Not to mention how coincidental that the Greek symbol we used for our generating function "$\Phi$" is written as the intersection between $0$ ("nothing") and $1$ ("singularity"). An equation $\Phi$ which allowed us to "comprise **data** given by infinitely many numbers into a *single* function"<sup>[\[3\]][14]</sup>. From $0$ to $1$, the starting-up and very source of our data story. Keep in touch and stay tuned!

### <span id="references"></span> References

<sup>[\[1\]][11]</sup> <i>biblegateway.com</i>. BibleGateway, n.d. Web. [<sup> <i class="fa fa-external-link"></i></sup>][10]

<sup>[\[2\]][13]</sup> Weisstein, Eric W. "Generating Function." From MathWorld--A Wolfram Web Resource. http://mathworld.wolfram.com/GeneratingFunction.html [<sup> <i class="fa fa-external-link"></i></sup>][12]

<sup>[\[3\]][18]</sup> Bóna, Miklós. <i>A Walk Through Combinatorics: an introduction to enumeration and graph theory.</i> Singapore: World Scientific Publishing Co. Pte. Ltd, 2011. Print. (Chapter 8: A Function is Worth Many Numbers. Generating Functions) [<sup> <i class="fa fa-external-link"></i></sup>][15]

[1]: http://goo.gl/6yv3dQ "'Know Yourself' - Greek"
[2]: http://en.wikiquote.org/wiki/Pythagoras "Pythagoras"
[3]: http://goo.gl/cqePXp "'Good Travel has no Tracks' - Chinese (traditional)"
[4]: http://en.wikiquote.org/wiki/Laozi "Lao Tzu"
[5]: http://www.etsy.com/listing/130210865/vintage-large-round-wall-mirror-30 "Snapshot Vintage Mirror"
[6]: http://www.quora.com/TEDx/Is-Randy-Powell-saying-anything-in-his-2010-TEDxCharlotte-talk-or-is-it-just-total-nonsense "Vortex Math"
[7]: http://www.storyofmathematics.com/indian_brahmagupta.html "Brahmagupta"
[8]: http://www.earthintransition.org/wp-content/uploads/2012/08/nautilus-golden-ratio-080212.gif "Nautilus shell"
[9]: #recurrences "negative fibonacci numbers"
[10]: http://www.biblegateway.com/passage/?search=Genesis+1
[11]: #Genesis
[12]: http://mathworld.wolfram.com/GeneratingFunction.html
[13]: #generatingfunction1
[14]: #references
[15]: http://books.google.com/books?id=TzJ2L9ZmlQUC&printsec=frontcover&dq=isbn:9814335231
[16]: http://www.thegreatpeacemakers.com/uploads/4/5/6/2/4562806/6896423_orig.jpg "Spiral Galaxy"
[17]: http://hrexach.files.wordpress.com/2014/12/fib5.jpg "Ear Fibonacci Spiral"
[18]: #generatingfunction2
[19]: http://en.wikipedia.org/wiki/Fibonacci_number#Closed-form_expression "Binet's Formula"
[20]: http://en.wikipedia.org/wiki/Kepler_triangle "Kepler Triangle"