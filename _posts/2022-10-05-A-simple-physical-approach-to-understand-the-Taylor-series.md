---
layout: post
title: A simple physical approach to understand the Taylor series
tags: Maths Physics Tutorial
description: Do you know that the displacement formula with acceleration in one dimension which you had learned in Physics class actually reveals the existence of Taylor series implicitly?
---

I still remember the first time that I meet the concept of **Taylor series** was in one AP calculus textbook. It's kind of a pity that the AP calculus textbook I was reading at that time didn't give any further explanation about why and how this formula came up, etc. So I just questioned myself about its formation and finally I did figured it out at that time by using the knowledge I've learned in Physics. I guess you may wonder why wouldn't I just search on the Internet and see the proof of **Taylor series**, in fact, I did do that, but didn't work for me at that point, since I lack too much Maths knowledge to understand that proof. Therefore I found a new way to help myself understand the **Taylor series** at that time.

Firstly, let us derive the displacement formula with acceleration in one dimension:

$$
\begin{aligned}
\frac{\mathrm{d} x}{\mathrm{d} t} &=v_t \\
\\
\mathrm{d} x&=v_t \times \mathrm{d} t \\
\int_{t_0}^{t} \mathrm{d} x&= \int_{t_0}^{t}\left(v_t \right) \ \mathrm{d} t \\
x_t&=\int_{t_0}^{t}\left(v_t \right) \ \mathrm{d} t + x_0
\end{aligned}
$$

Similarly, we can use the same deriving method of:

$$
\frac{\mathrm{d} x}{\mathrm{d} t} = v_t \quad \Rightarrow \quad x_t=\int_{t_0}^{t}\left(v_t \right) \ \mathrm{d} t + x_0
$$

To get:

$$
\frac{\mathrm{d} v}{\mathrm{d} t} = a_t  \quad \Rightarrow \quad v_t=\int_{t_0}^{t}\left(a_t \right) \ \mathrm{d} t + v_0
$$

Then we substitute $v_t$ into $x_t$, we would have:

$$
x_t=\int_{t_0}^{t}\left(\int_{t_0}^{t}\left(a_t \right) \ \mathrm{d} t \right)\ \mathrm{d} t + v_0(t-t_0)    + x_0 \tag{1}
$$

Note that since $a_t$ is a constant (In fact, this is related to the **Principle of least action** in Physics: We assume that the accleration of any system must be a constant,
in other words: $\dfrac{\mathrm{d}^3 (x)}{(\mathrm{d} t)^3} = 0$), therefore we could get our displacement formula with acceleration:

$$
x_t=\dfrac{a_t(t-t_0)^2}{2}+v_0(t-t_0)+x_0
$$

But the problem is: What if $a_t$ is not a constant anymore (And that situations do happen a lot in real life), for example, have you heard about presence of *jerk* ($j_t =\dfrac{\mathrm{d} a}{\mathrm{d} t}$) before?

Then we need to deal with the equation $(1)$ again, through using the same deriving method stated above, we could get:

$$
\frac{\mathrm{d} a}{\mathrm{d} t} = j_t  \quad \Rightarrow \quad a_t=\int_{t_0}^{t}\left(j_t \right) \ \mathrm{d} t + a_0
$$

Next we substitute $a_t$ into $x_t$, we can have:

$$
x_t=\int_{t_0}^{t}\left(\int_{t_0}^{t}\left(\int_{t_0}^{t}\left( j_t\right) \ \mathrm{d} t  \right) \ \mathrm{d} t  \right)  \ \mathrm{d} t + \dfrac{a_0(t-t_0)^2}{2}+ v_0(t-t_0)+ x_0
$$

And using some derivatives form to substitute in that equation:

$$
x_t=\int_{t_0}^{t}\left(\int_{t_0}^{t}\left(\int_{t_0}^{t}\left( j_t\right) \ \mathrm{d} t  \right) \ \mathrm{d} t  \right)  \ \mathrm{d} t + \dfrac{\ddot{x}_{t=t_0}(t-t_0)^2}{2!}+\dfrac{\dot{x}_{t=t_0}(t-t_0)}{1!}+ \dfrac{x_{t=t_0}}{0!}
$$

$$
\text{Where } \dot{x}_{t} = \dfrac{\mathrm{d} x}{\mathrm{d} t}, \dot{x}_{t} =\dfrac{\mathrm{d}^2 x}{(\mathrm{d} t)^2} \text{ and so on.}
$$

Now I believe that you could clearly see the presence of the **Taylor series** in this equation right?

Therefore if we keep iterating using the same method and let $x_{t}=f(t)$, we would be able to get the real **Taylor series** formula:

$$
f(t)=\sum_{n=0}^{\infty }\left( \frac{f^{(n)}{'}({t=t_0})}{n!} \left(t-t_0\right)^{n}\right)
$$

This also indicate us the essence of **Taylor series**: Knowing all of its $n$th ($n$ is natural numbers) derivatives value at one point is equivalent to Knowing the primitive formula of a function.
