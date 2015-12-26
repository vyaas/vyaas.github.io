---
layout: page
title:  "Frustration with Fluctuations"
---

The following is a simple, yet radically important point made by [E.T. Jaynes](http://bayes.wustl.edu/). 

When a physical occurrence appears too complicated to understand, we assign to it a probability of happening, based on all the available information we have. These probability distributions are, as Jaynes has put it, carriers of information. They are epistemological things, i.e. they are founded on what we know. For instance, the _expectation value_ of a quantity \\(f\\) relevant to some phenonmenon is given by

$$ \langle f \rangle = \sum\_{i}^np\_if\_i $$

Here, \\(n\\) is the number of microscopic configurations the system can be in (i.e. subject to the constraints), \\(p\_i\\) is the probability that the system exhibits the \\(i\\)th occurrence, and \\(f\_i\\) is the value f takes in such an occurrence. We call \\(\langle f \rangle\\) the expectation value of \\(f\\). It is a prediction based on all the information we have of the system.

How much an \\(f\_i\\) deviates from \\(\langle f \rangle\\) is given by the difference \\( f\_i - \langle f \rangle \\). The expectation value of such a deviation is an indicator of how reliable our expectation value is.

$$ \Delta^{2}f = \langle (\Delta f)^2 \rangle $$
$$             = \langle (f - \langle f \rangle)^2 \rangle $$
$$             = \langle f^2 - 2f \langle f\rangle + (\langle f \rangle)^2 \rangle $$
$$             = \langle f^2 \rangle - 2\langle f \rangle \langle f\rangle + \langle f \rangle^2 $$
$$             = \langle f^2 \rangle - \langle f \rangle^2 $$

We take the expectation value of the squares of the deviations because that gives us a positive number; the expectation value of just the deviation can turn out to be zero and thus hide how much each possibility varies from the mean. The quantity \\(\Delta^{2}f\\) is called the _variance_ of \\(f\\). A large variance indicates that out expectation value is not very reliable. More precisely, the ratio of the expectation values to the square root of the variance tells us how good our expectation value is. This number ought to be much less than one if are to make sharp predictions. 

The expectation values and variances are epistemological things as opposed to ontological things, i.e. they are not physical properties of the system, they are simply estimates based on available information. 

Here is however, an ontological thing:

$$ \bar{f} = \frac{1}{T}\int\_{0}^T f(t)dt $$

\\(\bar{f}\\) is the time average of the physical quantity \\(f\\). It can be experimentally measured. This has nothing to do with probabilities. But we can however make a prediction about \\(\bar{f}\\) by computing its expectation value:


$$ \langle\bar{f}\rangle = \left\langle \frac{1}{T}\int\_{0}^T f(t)dt \right\rangle $$
$$                       = \frac{1}{T}\int\_{0}^T \langle f \rangle dt $$

Now _this_ is a statement of probabilities. We always hope to match these expectation values with the measured quantities. The way we do this is to systematically accumulate all information relevant to the phenomenon in question and assign probability distributions. We must dutifully update these probabilities with newly available information if we wish to make reliable predictions. This is the essence of the scientific method, what Jaynes has rightly called the _Logic of Science_[^1]. 

At equilibrium, \\(\langle\bar{f}\rangle = \langle f\rangle\\), but in general, equating time averages with expectation values needs to be founded on more assumptions. To drive home the point, Jaynes asks us to calculate the variance of the time average[^2], i.e the reliability of our estimate of the time average.

$$ \Delta^2\bar{f} = \langle\  (\bar{f} - \langle\bar{f}\rangle)^2\  \rangle $$
$$ 		   = \langle\  (\bar{f} - \langle\bar{f}\rangle) (\bar{f} - \langle\bar{f}\rangle)\rangle $$
$$ 		   = \frac{1}{T^2} \left\langle\ \int\_{0}^T(f(t\_1)-\langle f(t\_1) \rangle)dt\_1 \int\_{0}^T(f(t\_2)-\langle f(t\_2) \rangle)dt\_2\right \rangle $$

$$ 		   = \frac{1}{T^2} \left\langle\ \int\_{0}^T\int\_{0}^T(f(t\_1)f(t\_2)-f(t\_1)\langle f(t\_2) \rangle - f(t\_2)\langle f(t\_1) + \langle f(t\_1) \rangle \langle f(t\_2) \rangle)dt\_1dt\_2  \right\rangle $$
$$ 		   = \frac{1}{T^2} \int\_{0}^T\int\_{0}^T(\langle f(t\_1)f(t\_2)\rangle - \langle f(t\_1) \rangle \langle f(t\_2) \rangle)dt\_1dt\_2  $$

The integrand is a function of times \\(t\_1\\) and \\(t\_2\\). But, if the system is in a stationary state, then the itegrand, which we call the covariance function, is a function only of the time difference \\(\tau = t\_2 - t\_1\\).

$$ K(\tau) = \langle f(t)f(t+\tau) \rangle + \langle f(t) \rangle \langle f(t+\tau) \rangle $$
$$         = \langle f(0)f(\tau) \rangle + \langle f \rangle^2  $$

We should therefore be able to reduce the double integral to a single integral. We do this by changing the variables of integration. Let us define two new variables

$$ \tau = t\_1 - t\_2 $$
$$ \eta = t\_1 + t\_2 $$

The relationship between the infinitesimal areas in the two domains is given by:

$$ ||J|| dt\_1dt\_2 = d\tau d\eta $$

where \\(||J||\\) is the absolute value of the Jacobian (determinant) of the transformation which is given by

$$ \begin{vmatrix}
\frac{\partial \tau}{\partial t\_1}  & \frac{\partial \eta}{\partial t\_2}  \\\ 
\frac{\partial \tau}{\partial t\_1}  & \frac{\partial \eta}{\partial t\_2}  \\\
\end{vmatrix} $$

According to our adopted transformation, \\(||J|| = 2\\).
 

<center><img src = "{{ site.url }}/public/images/integral_change_of_variables.png"\></center>

To integrate in the new domain, we need to change the limits of integration. We would like to integrate out over \\(\eta\\) so that we're left with an integral over \\(\tau\\). As can be seen from the figure below, when \\(\tau>0\\), \\(\eta\\) varies between \\(\tau\\) and \\(2T-\tau\\). When \\(\tau<0\\), \\(\eta\\) varies between \\(\tau\\) and \\(2T+\tau\\). So on the whole, we see that \\(\eta\\) varies between \\(|\tau|\\) and \\(2T-|\tau|\\). \\(\tau\\) ofcourse varies between \\(-T\\) and \\(T\\). Therefore, 

$$ \Delta^2\bar{f} = \frac{1}{2T^2}\int\_{-T}^{T}d\tau\int\_{|\tau|}^{2T-|\tau|}K(\tau)d\eta $$
$$                 = \frac{1}{T^2}\int\_{-T}^{T}(T-\tau)K(\tau)d\tau $$

Since \\(K(\tau)\\) is symmetric in \\(\tau\\),
$$  \Delta^2\bar{f} = \frac{2}{T^2}\int\_{0}^{T}(T-\tau)K(\tau)d\tau \ \ \ \ \ \ \ \ \color{white}{(e.1)}$$

It is insufficient to claim that the variance of \\(\bar{f}\\) gets better as \\(T\to\infty\\). For that to be true, we need the integrals \\(\int\_{0}^{\infty}K(\tau)d\tau\\) and \\(\int\_{0}^{\infty}\tau K(\tau\)d\tau\\) to converge. Therefore, if correlations persist for a long time, we cannot make a reliable estimate of the time average! That simply means we need to supplement our probabilities with more information. 

What about measurable fluctuations? The root-mean-square fluctuation of a quantity \\(f\\) is given by

$$ \delta^2 f = \frac{1}{T}\int\_{0}^{T}(f(t)-\bar{f})^2dt $$ 
$$        = \bar{f^2} - (\bar{f})^2 $$

This is a measure of how much a quantity is different from its time average. It is indeed measurable and has nothing to do with the variance of the quantity or the variance of the time average of the quantity. 

But there is an unexpected relationship between the _expectation value_ of the RMS fluctuation and the variance of the time average. To derive it we first note that there is a second equivalent formula for the RMS fluctuation of f:


$$ \delta^2 f = \frac{1}{T}\int\_{0}^{T}(f(t)-\bar{f})^2dt $$
$$	  = \frac{1}{T^2}\int\_{0}^{T}\int\_{0}^{T}(f(t\_1)^2-f(t\_1)(t\_2))dt\_1dt\_2 $$

Why have we converted this single integral into a double integral? You'll soon see why. Now let us take the expectation value of both sides:

$$ \langle \delta^2 f \rangle = \frac{1}{T^2}\int\_{0}^{T}\int\_{0}^{T}(\langle f(t\_1)^2 \rangle - \langle f(t\_1)f(t\_2) \rangle)dt\_1dt\_2 $$

Since we're discussing stationary processes, We'll convert this double integral to a single integral using the same change of variables we did earlier. The expectation value of the RMS fluctuation is thus

$$ \langle \delta^2 f \rangle = \frac{2}{T^2}\int\_{0}^{T}(T-\tau)G(\tau)d\tau \ \ \ \ \ \ \ \ \color{white}{(e.2)}$$

where 
$$ G(\tau) = \langle f^2 \rangle - \langle f(0)f(\tau) \rangle $$

assuming a stationary process. Note the difference between \\(G(\tau)\\) and \\(K(\tau)\\). The latter contains the square of the expectation value while the former contains the expectation value of the square. We know that the difference between these gives us the variance! We can exploit this by rewriting \\((e.1) \\) as follows:


$$  \Delta^2\bar{f} = \frac{2}{T^2}\int\_{0}^{T}(T-\tau) (\langle f(0)f(\tau) \rangle + \langle f \rangle^2) d\tau $$

Rearrange this to get 

$$ \frac{2}{T^2}\int\_{0}^{T}(T-\tau)\langle f(0)f(\tau\) \rangle d\tau = \Delta^2\bar{f} + \langle f \rangle^2 $$


We can similarly rearrange \\((e.2)\\) to get 
$$ \frac{2}{T^2}\int\_{0}^{T}(T-\tau)\langle f(0)f(\tau\) \rangle d\tau = \langle f \rangle^2  - \langle \delta^2 f \rangle $$

We therefore have, quite amazingly,

$$ \langle \delta^2 f \rangle = \Delta^2 f - \Delta^2 \bar{f} $$

If our time for averaging is long enough that \\(\Delta^2 \bar{f} \to 0 \\), then we can equate the expectation value of the fluctuation with the variance! Note that \\( \Delta^2 \bar{f} \leq \Delta^2 f\\) because \\(\langle \delta^2 f \rangle\\) can never be negative.

And how good is this estimate you ask? We need to compute the expectation value of the variance of the variance, which leads to a four-point correlation. This hierarchy is treacherous mathematical territory, but leads one to appreciate the _Ergodic problem of probability_. Equating time averages with expectation values is highly non-trivial. The above derivation sheds light on why some fluctuation based results from statistical mechanics make sense, like the Onsager reciprocal relations and the fluctuation dissipation theorem. These have been shown to yield very good agreement with experiment, a reflection of propagating sufficient information via the partition function and also taking time averages over a sufficiently long duration. It is surprising, and often frustrating, that a majority of researchers (and teachers) don't pay any heed to the above line of reasoning. Part of the problem stems from the prevalent view that probabilities of occurrence are actually frequencies of occurrence. This is, in my opinion and many others, a terribly misinformed view. Nature is not inherently random. If classical and quantum mechanics has taught us anything, it is that these systems are fundamentally deterministic, and that Nature will do whatever it is doing. It is our ignorance in following the detailed motions, the various degrees of freedom, that forces us to resort to probabilistic descriptions. The probabilities we derive in equilibrium statistical mechanics do not take into account the temporal behavior of the system, yet we derive results about physical fluctuations and symmetries of kinetic coefficients! These must come from additional non-trivial assumptions.

References:

[^1] Reading Jaynes' [_Probability Theory: Logic of Science_](https://books.google.se/books/about/Probability_Theory.html?id=tTN4HuUNXjgC&redir_esc=y) is an intellectual adventure deserved to be experienced by everyone. Not just people in Science. Everyone.

[^2]Jaynes, E. T., [_Where do we Stand on Maximum Entropy?_](http://bayes.wustl.edu/etj/node1.html), 1979
