# phys512-assignment-4-solved
**TO GET THIS SOLUTION VISIT:** [Phys512 Assignment 4 Solved](https://www.ankitcodinghub.com/product/phys512-assignment-4-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;101385&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;Phys512 Assignment 4 Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
<pre>planck_likelihood.py
</pre>
in the mcmc directory. You will need to install CAMB (pip3 install camb may work for you, but it also may not), and your life will be easier next week if you already have the dependencies sorted out.

1) We will do a non-linear least-squares problem. Look at the file side- bands.npz in the mcmc directory. This file contains data from one of your TA’s who is trying to measure the width of a resonance in an optical cavity. To do this, they send in a laser with sidebands (so, most of the laser power is at a central frequency ν plus a bit of power at ν + dν and ν − dν). They use a piezo to mechanically push on the cavity, which in turn alters the resonant frequency of the cavity. You can assume that over the stretch of data we use, the piezo shifts the cavity resonant frequency linearly in time. You can load the data with e.g.:

<pre>stuff=np.load(’sidebands.npz’)
t=stuff[’time’]
d=stuff[’signal’]
</pre>
a) To start, model the data as a single Lorentzian and use analytic derivatives. Please use Newton’s method (or Levenberg-Marquardt if you prefer) to carry out the fit. What are your best-fit parameters for the amplitude, width, and center? Please parameterize the Lorentzian as

d=a 1+(t−t0)2/w2

b) Estimate the noise in the data, and use that to estimate the errors in your parameters.

c) Repeat part a), but use numerical derivatives. I suggest you use a helper function that accepts an input function (and any ancillary data/arguments you want to pass it) and returns the derivatives of that function with respect to the model parameters. Are your answers statistically significantly different from your answers in a)?

d) Repeat part c), but now model the data as the sum of three Lorentzians. The width of all three Lorentzians should be the same, and the separation of the side peaks from the main peak should be equal, i.e.:

d=a+b+c 1+(t−t0)2/w2 1+(t−t0 +dt)2/w2 1+(t−t0 −dt)2/w2

1

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
You should have sensible guesses for a,t0,w from earlier, so you should try to estimate reasonable initial guesses for b,c,dt. What are your errors on these parameters?

e) Look at the residuals from subtracting your best-fit model from the data. Do you believe the error bars you got by assuming the data are independent with uniform variance, and that the model is a complete description of the data?

f) Generate some some realizations for the parameter errors using the full covariance matrix AT N−1A from part d). Plot the models you get from adding these parameters to the parameter errors. What is the typical difference in χ2 for the perturbed parameters compared to the best-fit χ2? Is this reasonable?

g) Redo the fit from part d), using an MCMC. IMPORTANT – please use your parameter covariance estimate from d) to generate your trial MCMC sam- ples, though you can introduce an overall scaling (the overall scaling should be order unity, but you may find faster convergence if it isn’t exactly 1). Show at least one plot that explains why you think your chain is converged. Did your error bars change?

h) The laser sidebands are separated from the main peak by 9 GHz (so dx maps to 9 GHz). What is the actual width of the cavity resonance, in GHz?

</div>
</div>
<div class="layoutArea">
<div class="column">
2

</div>
</div>
</div>
