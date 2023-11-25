# A novel proof of Pythagorus' Theorem using Involutes and Binomial Coefficients.

We will calculate $cos^2x+sin^2x$ from first principles for any value of x.  

Consider the right-angled triangle with sides a, b and c with angle x between a and c.  
![abc triangle](./abc%20triangle.png)  
We need to demonstrate that 
$$a^2+b^2 = c^2$$
which is equivalent to demonstrating that
$$\tag1{({a\over c})}^2+{({b\over c})}^2=1.$$
The definition of $cos x$  and $sin x$ are
$$cos x = {adjacent \over hypotenuse}={a\over c}$$
$$sin x = {opposite \over hypotenuse}= {b\over c}.$$   
We will calculate from first principles  
$$cos^2x+sin^2x=?$$  

Geometrically we can calculate $cos x$ by unrolling [involutes](https://en.wikipedia.org/wiki/Involute) on the unit circle. The simple calculation uses only geometry and limits - it does not rely on the Pythagorean Identity.
This leads us to the following equations for $cosx$ and $sinx$ valid for any real x.  
$$cosx=\big({x^0\over0!}-{x^2\over2!}+{x^4\over4!}-{x^6\over6!}+...\big)=∑_{n=0}^\infty {(-1)^nx^{2n} \over (2n)!}$$
$$sinx=\big({x^1\over1!}-{x^3\over3!}+{x^54\over5!}-{x^7\over7!}+...\big)= ∑_{n=0}^\infty {(-1)^nx^{2n+1} \over (2n+1)!}$$

We will now brute force calculate $cos^2x+sin^2x$.

We can expand the terms of $cos^2x$ into this infinite table and then collect the terms diagonally. This is called the [Cauchy Product](https://en.wikipedia.org/wiki/Cauchy_product).  
$$cos^2x=\big({x^0\over0!}-{x^2\over2!}+{x^4\over4!}-{x^6\over6!}+...\big)*\big({x^0\over0!}-{x^2\over2!}+{x^4\over4!}-{x^6\over6!}+...\big)$$
| |$x^0$|$x^2$|$x^4$|$x^6$|...|
|-|-|---|---|---|---|
|$x^0$|$1\over0!0!$|$-1\over0!2!$|$1\over0!4!$|$-1\over0!6!$|...|
|$x^2$|$-1\over2!0!$|$1\over2!2!$|$-1\over2!4!$|$1\over2!6!$|...|  
|$x^4$|$1\over4!0!$|$-1\over4!2!$|$1\over4!4!$|$-1\over4!6!$|...|  
|$x^6$|$-1\over6!0!$|$1\over6!2!$|$-1\over6!4!$|$1\over6!6!$|...|
|...|...|...|...|...|...|  

$=x^0 ({ 1 \over 0!0! })-x^2 ({1\over0!2!}+{1\over2!0!})+x^4 ({1\over0!4!}+{1\over2!2!}+{1\over4!0!}) -x^6({1\over0!6!}+{1\over2!4!}+{1\over4!2!}+{1\over6!0!})+x^8(...)+... $  
Each term from the table is included once in the infinite sum above.  
Each double factorial term in the brackets looks like the denominator of a [binomial coefficent](https://en.wikipedia.org/wiki/Binomial_coefficient).  
$$\big(_k^n\big)={n!\over{k!(n-k)!}} $$  
We are only missing the $n!$ term in the numerator.  
If we multiply and divide each term by the factorial of the exponents we can make each term in the brackets a binomial coefficient.  
$$={x^0\over0!}({ 0! \over 0!0! })-{x^2\over2!}({2!\over0!2!}+{2!\over2!0!})+{x^4\over4!}({4!\over0!4!}+{4!\over2!2!}+{4!\over4!0!})\\-{x^6\over6}!({6!\over0!6!}+{6!\over2!4!}+{6!\over4!2!}+{6!\over6!0!})+{x^8\over8!}(...)+... $$  

$$={x^0\over0!} (_0^0)-{x^2\over2!}\big((_0^2)+(_2^2)\big)+{x^4\over4!}\big((_0^4)+(_2^4)+(_4^4)\big)-{x^6\over6}!\big((_0^6)+(_2^6)+(_4^6)+(_6^6)\big)+{x^8\over8!}(...)+... $$

Similarly $sin^2x=$ will provide us with the missing odd terms, all with the sign inverted.
| |$x^1$|$x^3$|$x^5$|$x^7$|...|
|-|-|---|---|---|---|
|$x^1$|$1\over1!1!$|$-1\over1!3!$|$1\over1!5!$|$-1\over1!7!$|...|
|$x^3$|$-1\over3!1!$|$1\over3!3!$|$-1\over3!5!$|$1\over3!7!$|...|  
|$x^5$|$1\over5!1!$|$-1\over5!3!$|$1\over5!5!$|$-1\over5!7!$|...|  
|$x^7$|$-1\over7!1!$|$1\over7!3!$|$-1\over7!5!$|$1\over7!7!$|...|
|...|...|...|...|...|...|  

$={x^2\over2!}({1\over1!1!})-{x^4\over4!} ({1\over1!3!}+{1\over3!1!})+{x^6\over6!} ({1\over1!5!}+{1\over3!3!}+{1\over5!1!}) -{x^8\over8!}(...)+... $  
$={x^2\over2!}({2!\over1!1! })-{x^4\over4!}({4!\over1!3!}+{4!\over3!1!})+{x^6\over6!}({6!\over1!5!}+{6!\over3!3!}+{6!\over5!1!}) -{x^8\over8!}(...)+... $  
$={x^2\over2!}(_1^2)-{x^4\over4!}[(_1^4)+(_3^4)]+{x^6\over6!}[(_1^6)+(_3^6)+(_5^6)] -{x^8\over8!}[...]+... $  

Combining, we get $cos^2x+sin^2x$  
$$\tag2={x^0\over0!}(_0^0)-{x^2\over2!}[(_0^2)-(_1^2)+(_2^2)]+{x^4\over4!}[(_0^4)-(_1^4)+(_2^4)-(_3^4)+(_4^4)]\\-{x^6\over6!}[(_0^6)-(_1^6)+(_2^6)-(_3^6)+(_4^6)-(_5^6)+(_6^6)]+{{x^8}\over8!}[...]-...$$

We see that for each term $x^n$ we have the alternating sum of all of its binomial coefficients. The proof that this sum is zero is easy. The [Binomial Formula](https://en.wikipedia.org/wiki/Binomial_theorem) is   
$${(1+x)^n}=∑_{k=0}^n {(_k^n)x^k}, x\in R, n\in N.$$  
Setting $x=-1$ gives  
$${(1-1)^n}=∑_{k=0}^n {(_k^n)(-1)^k}=(_0^n)-(_1^n)+(_2^n)+(_3^n)-...(_n^n)=0, n \in N.$$  
This means that equation (2) collapses to
$$cos^2x+sin^2x={x^0\over0!}-{x^2\over2!}[0]+{x^4\over4!}[0]-{x^6\over6!}[0]+{x^8}[0]+...=1$$  

$${\tag3}cos^2x+sin^2x=1$$

Equating (1) and (3)
results in
$${{({a\over c})}^2}+{{({b\over c})}^2}=cos^2x+sin^2x=1.$$ 

Multiplying by $c^2$ gives us the famous formula and our proof of the Pythagorean Identity  
$$ a^2 + b^2 = c^2.$$

