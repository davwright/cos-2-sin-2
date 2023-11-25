# A novel proof of Pythagorus' Theorem.

We will calculate $cos^2x+sin^2x$ from first principles for any value of x.  

We will consider the right angled triangle with sides a, b and c.  
![abc triangle](abc%20triangle.png)  
The definition of $cos x$  and $sin x$ are
$$cos x = {adjacent \over hypotenuse}={a\over c} $$
$$sin x = {opposite \over hypotenuse}= {b\over c} $$

  $cos^2x+sin^2x$ 
  $= (∑_{n=0}^\infty {(-1)^nx^{2n} \over (2n)!})^2 + (∑_{n=0}^\infty {(-1)^nx^{2n+1} \over (2n+1)!})^2$

We can expand $cos^2x$ in this infinite table and then collection the terms diagonally (Cauchy Summing??).  
$cos^2x=$
| |$x^0$|$x^2$|$x^4$|$x^6$|...|
|-|-|---|---|---|---|
|$x^0$|$1\over0!0!$|$-1\over0!2!$|$1\over0!4!$|$-1\over0!6!$|...|
|$x^2$|$-1\over2!0!$|$1\over2!2!$|$-1\over2!4!$|$1\over2!6!$|...|  
|$x^4$|$1\over4!0!$|$-1\over4!2!$|$1\over4!4!$|$-1\over4!6!$|...|  
|$x^6$|$-1\over6!0!$|$1\over6!2!$|$-1\over6!4!$|$1\over6!6!$|...|
|...|...|...|...|...|...|  

$=x^0 ({ 1 \over 0!0! })-x^2 ({1\over0!2!}+{1\over2!0!})+x^4 ({1\over0!4!}+{1\over2!2!}+{1\over4!0!}) -x^6({1\over0!6!}+{1\over2!4!}+{1\over4!2!}+{1\over6!0!})+x^8(...)+... $  
If we multiply and divide each term by the factorial of the exponents we can make each term in the brackets a binomial coefficient.  
$={x^0\over0!}({ 0! \over 0!0! })-{x^2\over2!}({2!\over0!2!}+{2!\over2!0!})+{x^4\over4!}({4!\over0!4!}+{4!\over2!2!}+{4!\over4!0!})\\-{x^6\over6}!({6!\over0!6!}+{6!\over2!4!}+{6!\over4!2!}+{6!\over6!0!})+{x^8\over8!}(...)+... $  

$={x^0\over0!} (_0^0)-{x^2\over2!}\big((_0^2)+(_2^2)\big)+{x^4\over4!}\big((_0^4)+(_2^4)+(_4^4)\big)-{x^6\over6}!\big((_0^6)+(_2^6)+(_4^6)+(_6^6)\big)+{x^8\over8!}(...)+... $

Similarly $sin^2x=$ will provide us with the missing odd terms, all with the sign inverted.
| |$x^1$|$x^3$|$x^5$|$x^7$|...|
|-|-|---|---|---|---|
|$x^1$|$1\over1!1!$|$-1\over1!3!$|$1\over1!5!$|$-1\over1!7!$|...|
|$x^3$|$-1\over3!1!$|$1\over3!3!$|$-1\over3!5!$|$1\over3!7!$|...|  
|$x^5$|$1\over5!1!$|$-1\over5!3!$|$1\over5!5!$|$-1\over5!7!$|...|  
|$x^7$|$-1\over7!1!$|$1\over7!3!$|$-1\over7!5!$|$1\over7!7!$|...|
|...|...|...|...|...|...|  

$={x^2\over2!}({1\over1!1!})-{x^4\over4!} ({1\over1!3!}+{1\over3!1!})+x^6 ({1\over1!5!}+{1\over3!3!}+{1\over5!1!}) -x^8(...)+... $  
$={x^2\over2!}({2!\over1!1! })-{x^4\over4!}({4!\over1!3!}+{4!\over3!1!})+{x^6\over6!}({6!\over1!5!}+{6!\over3!3!}+{6!\over5!1!}) -{x^8}(...)+... $  
$={x^2\over2!}(_1^2)-{x^4\over4!}[(_1^4)+(_3^4)]+{x^6\over6!}[(_1^6)+(_3^6)+(_5^6)] -{x^8}[...]+... $  

Combining we get $cos^2x+sin^2x$  
$$\tag2={x^0\over0!}-{x^2\over2!}[(_0^2)-(_1^2)+(_2^2)]+{x^4\over4!}[(_0^4)-(_1^4)+(_2^4)-(_3^4)+(_4^4)]\\-{x^6\over6!}[(_0^6)-(_1^6)+(_2^6)-(_3^6)+(_4^6)-(_5^6)+(_6^6)]+{x^8}[...]+...$$

The sum of alternating binomial coefficients is zero.
Proof:  
$$ (1+x)^n=∑_{k=0}^n {(_k^n)x^k}$$  
Setting $x=-1$ gives
$$ (1-1)^n=∑_{k=0}^n {(_k^n)(-1)^k}=0$$
This means that equation (2) collapses to
$$cos^2x+sin^2x={x^0\over0!}-{x^2\over2!}[0]+{x^4\over4!}[0]-{x^6\over6!}[0]+{x^8}[0]+...\\=1$$  

$${\tag2}cos^2x+sin^2x=1$$

Combining (1) and (2)
results in the famous formula and our proof of the Pythagorean Identity
$$ a^2 + b^2 = c^2.

