# A novel proof of Pythagorus' Theorem.

Calculate $cos^2x+sin^2x$from first principles.  

  $cos^2x+sin^2x$ 
  $= (\sum_{n=0}^{\infty} {(-1)^nx^{2n} \over (2n)!})^2 + (\sum_{n=0}^{\infty} {(-1)^nx^{2n+1} \over (2n+1)!})^2$

We can expand $cos^2x$in this infinite table and then collection the terms diagonally (Cauchy Summing??).  
$cos^2x=$
| |$x^0$|$x^2$|$x^4$|$x^6$|...|
|-|-|---|---|---|---|
|$x^0$|$1\over0!0!$|$-1\over0!2!$|$1\over0!4!$|$-1\over0!6!$|...|
|$x^2$|$-1\over2!0!$|$1\over2!2!$|$-1\over2!4!$|$1\over2!6!$|...|  
|$x^4$|$1\over4!0!$|$-1\over4!2!$|$1\over4!4!$|$-1\over4!6!$|...|  
|$x^6$|$-1\over6!0!$|$1\over6!2!$|$-1\over6!4!$|$1\over6!6!$|...|
|...|...|...|...|...|...|  

$=x^0 ({ 1 \over 0!0! })-x^2 ({1\over0!2!}+{1\over2!0!})+x^4 ({1\over0!4!}+{1\over2!2!}+{1\over4!0!}) -x^6({1\over0!6!}+{1\over2!4!}+{1\over4!2!}+{1\over6!0!})+x^8(...)+... $ 

Similarly $sin^2x=$
| |$x^1$|$x^3$|$x^5$|$x^7$|...|
|-|-|---|---|---|---|
|$x^1$|$1\over1!1!$|$-1\over1!3!$|$1\over1!5!$|$-1\over1!7!$|...|
|$x^3$|$-1\over3!1!$|$1\over3!3!$|$-1\over3!5!$|$1\over3!7!$|...|  
|$x^5$|$1\over5!1!$|$-1\over5!3!$|$1\over5!5!$|$-1\over5!7!$|...|  
|$x^7$|$-1\over7!1!$|$1\over7!3!$|$-1\over7!5!$|$1\over7!7!$|...|
|...|...|...|...|...|...|  

$=x^2 ({ 1 \over 1!1! })-x^4 ({1\over1!3!}+{1\over3!1!})+x^6 ({1\over1!5!}+{1\over3!3!}+{1\over5!1!}) -x^8({1\over1!7!}+{1\over3!5!}+{1\over5!3!}+{1\over7!1!})+... $ 


Combining we get $cos^2x+sin^2x$ 
$=x^0-x^2({1\over0!2!}-{1\over1!1!}+{1\over2!0!})+x^4({1\over0!4!}-{1\over1!3!}+{1\over2!2!}-{1\over3!1!}+{1\over4!0!})-x^6(...)+... $  
If we pull out the $1\over n!$ from each term we have.
$=x^0\over{0!}-x^2\over2!(2!\over0!2!}-{2!\over1!1!}+{2!\over2!0!})+x^4\over4!({4!\over0!4!}-{4!\over1!3!}+{4!\over2!2!}-{4!\over3!1!}+{4!\over4!0!})-x^6\over6!(...)+... $  

The remainder of the proof is to show that every coefficient of $x^{2n}$is just zero for $n>2$.   

$cos^2x+sin^2x$ 
$=1+ \sum_{n=1}^{\infty}(-1)^nx^{2n}(\sum_{k=0}^{n}{1\over {(2k)!(2n-2k)!}}-{1\over {(2k+1)!(2n+2-(2k+1))!}}) $
## Pascal's Triangle
|  |  |  | 1|  |  |  |
|--|--|--|--|--|--|--|
|  |  | 1|  | 1|  |  |
|  |1 |  | 2|  |1 |  |
| 1|  | 3|  | 3|  | 1|

Each element of Pascal's Triangle can be calculated as "n choose k" =  
$$\begin{pmatrix}n\\k\end{pmatrix} = { n! \over {(n-k)! k!}} $$ 

We can change the sum above to convert to Choose by.  
$$=1+ \sum_{n=3}^{\infty}(-1)^nx^{2n}(\sum_{k=0}^{n}{(2n)!\over {(2k)!(2n-2k)!(2n)!}}-{(2n+2)!\over {(2k+1)!(2n+2-(2k+1))!(2n+2)!}}) $$ 
$$=1+ \sum_{n=3}^{\infty}(-1)^nx^{2n}(\sum_{k=0}^{n}\begin{pmatrix}2n\\2k\end{pmatrix}{1\over {(2n)!}}-\begin{pmatrix}2n+2\\2k+2\end{pmatrix}{1\over{(2n+2)!}}) $$ 
We can pull out $1\over(2n+2)!$as a common factor.  
$$=1+ \sum_{n=3}^{\infty}{(-1)^nx^{2n}\over(2n+2)!}(\sum_{k=0}^{n}\begin{pmatrix}2n\\2k\end{pmatrix}(2n+1)(2n+2)-\begin{pmatrix}2n+2\\2k+2\end{pmatrix}) $$ 
Let's define 
$$A_n = \sum_{k=0}^{n}\begin{pmatrix}2n\\2k\end{pmatrix}(2n+1)(2n+2)-\begin{pmatrix}2n+2\\2k+2\end{pmatrix} $$ 
and we only need to prove that $A_n=0, n>2$.  
Splitting out first and last term we have
$$A_n =\begin{pmatrix}2n\\0\end{pmatrix}(2n+1)(2n+2)+[\sum_{k=1}^{n-1}\begin{pmatrix}2n\\2k\end{pmatrix}(2n+1)(2n+2)-\begin{pmatrix}2n+2\\2k+2\end{pmatrix}]+ $$
$$\begin{pmatrix}2n\\2n\end{pmatrix}(2n+1)(2n+2)-\begin{pmatrix}2n+2\\2n+2\end{pmatrix}$$ 
$$A_n =2(2n+1)(2n+2)-1+[\sum_{k=1}^{n-1}\begin{pmatrix}2n\\2k\end{pmatrix}(2n+1)(2n+2)-\begin{pmatrix}2n+2\\2k+2\end{pmatrix}] $$
Let us set 
$$B_n =\sum_{k=1}^{n-1}\begin{pmatrix}2n\\2k\end{pmatrix}(2n+1)(2n+2)-\begin{pmatrix}2n+2\\2k+2\end{pmatrix}, n>2$$
$$A_n=2(2n+1)(2n+2)-1 + B_n, n>2$$
Now using Pascal's Triangle we have
$$\begin{pmatrix}2n+2\\2k+2\end{pmatrix}=\begin{pmatrix}2n+1\\2k+1\end{pmatrix}+\begin{pmatrix}2n+1\\2k+2\end{pmatrix}$$

$$B_n =\sum_{k=1}^{n-1}\begin{pmatrix}2n\\2k\end{pmatrix}(2n+1)(2n+2)-\begin{pmatrix}2n+1\\2k+1\end{pmatrix}-\begin{pmatrix}2n+1\\2k+2\end{pmatrix}, n>2$$
Splitting out first term we have
$$B_n =(2n+1)(2n+2)-\begin{pmatrix}2n+1\\3\end{pmatrix}-\begin{pmatrix}2n+1\\4\end{pmatrix}+\sum_{k=2}^{n-1}\begin{pmatrix}2n\\2k\end{pmatrix}(2n+1)(2n+2)-\begin{pmatrix}2n+1\\2k+1\end{pmatrix}+\begin{pmatrix}2n+1\\2k+2\end{pmatrix}, n>2$$




