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

$$ 		   = \frac{1}{T^2} \left\langle\ \int\_{0}^T\int\_{0}^T(f(t\_1)f(t\_2)-f(t\_1)\langle f(t\_2) \rangle - f(t\_2)\langle f(t\_1)\rangle + \langle f(t\_1) \rangle \langle f(t\_2) \rangle)dt\_1dt\_2  \right\rangle $$
$$ 		   = \frac{1}{T^2} \int\_{0}^T\int\_{0}^T(\langle f(t\_1)f(t\_2)\rangle - \langle f(t\_1) \rangle \langle f(t\_2) \rangle)dt\_1dt\_2  $$

The integrand is a function of times \\(t\_1\\) and \\(t\_2\\). But, if the system is in a stationary state, then the itegrand, which we call the _autocorrellation function_[^3], depends only on the time difference \\(\tau = t\_2 - t\_1\\).

$$ K(\tau) = \langle f(t)f(t+\tau) \rangle - \langle f(t) \rangle \langle f(t+\tau) \rangle $$
$$         = \langle f(0)f(\tau) \rangle - \langle f \rangle^2  $$

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

It is insufficient to claim that the variance of \\(\bar{f}\\) becomes insignificantly small as \\(T\to\infty\\), i.e. it is not enough to say that for long averaging times, our estimate of the time average becomes precise. For that to be true, we need the integrals \\(\int\_{0}^{\infty}K(\tau)d\tau\\) and \\(\int\_{0}^{\infty}\tau K(\tau\)d\tau\\) to converge. So if correlations persist for a long time, i.e. indefinitely, we cannot make a reliable estimate of the time average! 

What about measurable fluctuations? The root-mean-square fluctuation of a quantity \\(f\\) is given by

$$ \delta^2 f = \frac{1}{T}\int\_{0}^{T}(f(t)-\bar{f})^2dt $$ 
$$        = \bar{f^2} - (\bar{f})^2 $$

This is a measure of how much a quantity is different from its time average. It is indeed measurable and has nothing to do with the variance of the quantity or the variance of the time average of the quantity. 

But there is an unexpected relationship between the _expectation value_ of the RMS fluctuation and the variance of the time average. To derive it we first note that there is a second equivalent formula for the RMS fluctuation of f:


$$ \delta^2 f = \frac{1}{T}\int\_{0}^{T}(f(t)-\bar{f})^2dt $$
$$	  = \frac{1}{T^2}\int\_{0}^{T}\int\_{0}^{T}(f(t\_1)^2-f(t\_1)(t\_2))dt\_1dt\_2 $$

Why have we converted this single integral into a double integral? You'll soon see why. Now let us take the expectation value of both sides:

$$ \langle \delta^2 f \rangle = \frac{1}{T^2}\int\_{0}^{T}\int\_{0}^{T}(\langle f(t\_1)^2 \rangle - \langle f(t\_1)f(t\_2) \rangle)dt\_1dt\_2 $$

Since we're discussing stationary processes, we'll convert this double integral to a single integral using the same change of variables we did earlier. The expectation value of the RMS fluctuation is thus

$$ \langle \delta^2 f \rangle = \frac{2}{T^2}\int\_{0}^{T}(T-\tau)G(\tau)d\tau \ \ \ \ \ \ \ \ \color{white}{(e.2)}$$

where 
$$ G(\tau) = \langle f^2 \rangle - \langle f(0)f(\tau) \rangle $$

assuming a stationary process. Note the difference between \\(G(\tau)\\) and \\(K(\tau)\\). The latter contains the square of the expectation value while the former contains the expectation value of the square. We know that the difference between these gives us the variance! We can exploit this by rewriting \\((e.1) \\) as follows:


$$  \Delta^2\bar{f} = \frac{2}{T^2}\int\_{0}^{T}(T-\tau) (\langle f(0)f(\tau) \rangle - \langle f \rangle^2) d\tau $$

Rearrange this to get 

$$ \frac{2}{T^2}\int\_{0}^{T}(T-\tau)\langle f(0)f(\tau\) \rangle d\tau = \Delta^2\bar{f} + \langle f \rangle^2 $$


We can similarly rearrange \\((e.2)\\) to get 
$$ \frac{2}{T^2}\int\_{0}^{T}(T-\tau)\langle f(0)f(\tau\) \rangle d\tau = \langle f^2 \rangle  - \langle \delta^2 f \rangle $$

We therefore have, quite amazingly,

$$ \langle \delta^2 f \rangle = \Delta^2 f - \Delta^2 \bar{f} $$

If our time for averaging is long enough that \\(\Delta^2 \bar{f} \to 0 \\) (i.e., those integrals we talked about need to converge), then we can equate the expectation value of the fluctuation (physical) with the variance (probabilistic)! Note that \\( \Delta^2 \bar{f} \leq \Delta^2 f\\) because \\(\langle \delta^2 f \rangle\\) can never be negative.

And how good is this estimate you ask? To answer that, we need to compute the expectation value of the variance of the variance, which leads to a four-point correlation! This hierarchy is treacherous mathematical territory, but leads one to appreciate the _Ergodic problem of probability_. Equating time averages with expectation values is highly non-trivial. The above derivation sheds light on why some fluctuation based results from statistical mechanics make sense, like the Onsager reciprocal relations and the Fluctuation Dissipation Theorem. These have been shown to yield very good agreement with experiment, a reflection of propagating sufficient information via the partition function and also taking time averages over a sufficiently long duration. It is surprising, and often frustrating, that a majority of researchers (and teachers) don't pay any heed to the above line of reasoning. Part of the problem stems from the prevalent view that probabilities of occurrence are actually frequencies of occurrence. This is, in my opinion and many others, a terribly misinformed view. Nature is not inherently random. If classical and quantum mechanics has taught us anything, it is that these systems are fundamentally deterministic, and that Nature will do whatever it is doing. It is our ignorance in following the detailed motions, the various degrees of freedom, that forces us to resort to probabilistic descriptions. The probabilities we derive in equilibrium statistical mechanics do not take into account the temporal behavior of the system, yet we're shown results about physical fluctuations and symmetries of kinetic coefficients in the same breath!

#Onsager's reasoning

So we have _some_ basis for equating expectation values with time averages, and thus physical fluctuations with probabilistic variances, remembering all the while that correlations need to decay rapidly enough for "long-time" averages to make sense. Even though Onsager doesn't mention any of this, let us quickly summarize his derivation of the famous reciprocal relations (I'll use symbols from the [Landafshitz](https://en.wikipedia.org/wiki/Course_of_Theoretical_Physics) course). First, we acknowledge Boltzmann's monumental contribution:

$$ S = log(\Gamma) $$

Entropy \\((S)\\) is the logarithm of the number of microstates \\((\Gamma)\\) a system could be in for a given macrostate _at equilibrium_. Therefore the probability of the system being in a macrostate that is different from equilibrium is given by

$$ w(x\_1,x\_2,...,x\_n)dx=Ae^{S\_e - S(x\_1,x\_2,...,x\_n) }dx $$

Here, the \\(x\\)'s are parameters defining some macrostate that the entropy depends on. Since we're exploring states close to equilibrium, we can expand \\(S\\) in powers of the \\(x\\)'s about the equilibrium entropy \\(S\_e\\). Upto the second derivative, we have, in index notation (repeated indices imply sums, \\(\delta\\)'s are Kronecker):

$$ w=Ae^{-{\frac{1}{2}\beta\_{ik}x\_ix\_k}} $$

Equating the integral of the above distribution over all parameters to one gives \\(A=\sqrt{\beta}(2\pi)^{-\frac{1}{2}n}\\), where \\(\beta\\) is the determinant of \\(\beta\_{ik}\\). Note that here, we have considered the expectation value of \\(x\\)'s as 0, so you can think of them as perturbations from their equilibrium values. 

By defining what we'll call _conjugate variables_, given by

$$ X\_i = -\frac{\partial S}{\partial x\_i} = \beta\_{ik} x\_k $$

we have,

$$ \langle x\_i X\_k \rangle = \delta\_{ik} $$

$$ \langle x\_i x\_k \rangle = \beta\_{ik}^{-1} $$

$$ \langle X\_i X\_k \rangle = \beta\_{ik} \ \ \ \ \ \ \color{white}{(e.3)}$$

The covariance of the conjugate variables is symmetric with respect to the indices \\(i\\) and \\(j\\) by virtue of the definition of the covariance matrix \\(\beta\_{ik}\\); it comprises second derivatives of the entropy. So our first obvious symmetry is 

$$ \beta\_{ik} = \beta\_{ki} \ \ \ \ \ \ \color{white}{(s.1)}  $$

Having derived the probability distributions for the likelihoods of various quantities (or rather the likelihoods of their deviations from equilibrium), Onsager now asks us to mentally picture _actually_ perturbing a system from equilibrium. This "small" perturbation induces the system to drive itself back to equilibrium. _The rate of change of the deviations of the macroscopic quantities from their equilibrium values, is postulated to have the phenomenological form_,

$$ \dot{x\_i} = -\lambda\_{ik}x\_k $$

or, since we've defined those conjugate variables,

$$ \dot{x\_i} = -\gamma\_{ik}X\_k \ \ \ \ \ \ \color{white}{(e.4)}$$

This \\(\gamma\\) matrix comprises Onsager's phenomenological _kinetic coefficients_. It turns out this matrix is symmetric (that's the reciprocity!). The implication is that processes approaching equilibrium exhibit a symmetric coupling; for example, if the diffusion of mass transfers heat, the diffusion of heat transfers mass. 

The perturbation from equilibrium causes correlations, \\(\langle x\_i(t)x\_k(t+\tau)\rangle\\) to be finite over some relaxation time (recall the discussion about \\(K(\tau)\\)).

Onsager then invokes the assumption of _microscopic reversibility_. In the time integral \\(\langle x\_i(t)x\_k(t+\tau) \rangle\\) (remember that expectation values have been equated with time averages), \\(x\_i\\) is positioned to take place first followed by \\(x\_k\\) at a later time \\(\tau\\). If all the microscopic trajectories contributing to this integral are symmetric in time (as the laws of classical and quantum mechanics would have it), the relative times at which \\(x\_i\\) and \\(x\_k\\) are positioned in the integral wouldn't matter. Therefore, our second symmetry is 

$$ \langle x\_i(t)x\_k(t+\tau) \rangle = \langle x\_i(t+\tau)x\_k(t)\rangle \ \ \ \ \ \ \color{white}{(s.2)}$$

(Be apprised that this does not hold if magnetic fields or centripetal forces are present; they don't reverse direction when time reverses.) Taking derivatives on both sides with respect to \\(\tau\\) and taking \\(\tau\to 0\\) gives

$$ \langle x\_i\dot{x\_k} \rangle = \langle \dot{x\_i}x\_k\rangle $$

We can substitute \\((e.4)\\) in the above:

$$ \langle x\_i\gamma\_{kl}X\_l \rangle = \langle \gamma\_{il}X\_lx\_k\rangle $$

The relationships \\((e.3)\\) now come in handy since,

$$ \langle \gamma\_{kl}x\_iX\_l \rangle = \langle \gamma\_{il}X\_lx\_k\rangle $$
$$ \gamma\_{kl}\delta\_{il} = \gamma\_{il}\delta\_{lk} $$
$$ \gamma\_{ki} = \gamma\_{ik} \ \ \ \ \ \ \color{white}{(s.3)}$$

That last equality is Onsager's famous reciprocity relation.

This derivation, as reasonable looking as it is, doesn't indicate the range of applicability, let alone masking a great deal of non-trivial dynamics by equating expectation values with time averages. The need for introducing phenomenological relations while in the midst of propagating information via probability distributions further embitters any taste. To me, what is most unsettling about it is that entropy, a quantity that is very well defined at equilibrium (by ennumerating all the microstates subject to the experimental constraints), is now seen to _evolve_ in time _outside of equilibrium_! It is possible for a system to take multiple microscopic paths to equilibrium, which the standard definition of entropy says nothing about. Shouldn't such motions be accounted for in any non-equilibrium description? Herein lies the greatest conceptual controversy/confusion in all of statistical mechanics: Irreversibility and the Second Law of Thermodynamics. Jaynes spent a lifetime demystifying much of this and has left us with a great deal of wisdom on how to articulate and resolve such problems. I will share my notes from studying his works in a future article. 

#Footnotes

[^1]: Reading Jaynes' [_Probability Theory: Logic of Science_](https://books.google.se/books/about/Probability_Theory.html?id=tTN4HuUNXjgC&redir_esc=y) is an intellectual adventure deserved to be experienced by everyone. Not just people in Science. Everyone.

[^2]: Jaynes, E. T., 1979, [_Where do we Stand on Maximum Entropy?_](http://bayes.wustl.edu/etj/node1.html).

[^3]: The covariance function \\(K(\tau)\\), the way we've derived it, is a combination of expectation values. It is common practice to replace these expectation values with time averages and call \\(K(\tau)\\) the _correlation function_. The replacement of expectation values with time averages and vice versa is an assumption called the _Ergodic Hypothesis_. Once this is done, one can relate the correlation function to spectral densities using the [Wiener-Khinchin theorem](https://en.wikipedia.org/wiki/Wiener%E2%80%93Khinchin_theorem) and then proceed to derive dynamical things relating to relaxation phenomena, like the famous [_Fluctuation-Dissipation theorem_](https://en.wikipedia.org/wiki/Fluctuation_dissipation_theorem) for instance. The FD Theorem, first articulated by Einstein, is a statement about how the very "random" forces that cause the fluctuation of a quantity, also results in damping that quantity. For a simple introduction, read the first chapter of _Zwanzig, R., 2001. Nonequilibrium statistical mechanics. Oxford University Press, USA._ As tempting as it is to equate time averages with expectation values, it must be kept in mind that in doing so, we are - inadvertently at least - imposing upon Nature non-trivial dynamical behavior that simply stems from our ignorance of the underlying complexities. Many Physicists seem completely ok with Ergodicity. To quote the great Kip Thorne from his lecture notes on random processes, where he confines all discussions to ergodic phenomena, _"This (ergodic hypothesis), in principle, is a severe restriction. In practice, for a physicist, it is not severe at all. In physics one's objective, when defining random variables that last forever and when introducing ensembles, is usually to acquire computational techniques for dealing with a single, or a small number of random variables \\(y(t)\\), studied over finite lengths of time; and one acquires those techniques by defining one's conceptual infinite-duration random variables and ensembles in such a way that they satisfy the ergodic hypothesis."_ This to me is a bit too convenient and requires better justification. The current discussion aims at quantifying the degree of correctness of such an assumption.

