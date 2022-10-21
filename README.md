# Quant Finance 

In this repository we will try to go through different portfolio construction techniques, performance analysis and backtesting. 

- FILE: Portfolio Construction

The notebook file consists of two main ideas: 1) Projection of Expected Returns(and Covariances) and 2) Constructing portfolios using ER and COV.
Key concept of the file is based on stochastic modeling. Stochastic modeling is a form of financial model that is used to help make investment decisions.  
This type of modeling forecasts the probability of various outcomes under different conditions, using random variables.
Stochastic modeling is inherently random, and the uncertain factors are built into the model.

The Monte Carlo simulation is one example of a stochastic model; it can simulate how prices may perform based on the probability distributions.
Base case assumptions for performing M-C simulation are following: a) using some historical inputs (e.g., daily prices of last two years), b) normal (Gaussian) distribution.

Brownian motion will be the main driver for estimating the return. It is a stochastic process used for modeling random behavior over time. 
A geometric Brownian motion (exponential Brownian motion) is a continuous-time stochastic process in which the logarithm of the randomly varying quantity follows a Brownian motion with drift.

A stochastic process St is said to follow a GBM if it satisfies the following stochastic differential equation (SDE):

dS(t) = muS(t)dt + sigmaS(t)dW(t),
where W(t) is a Wiener process or Brownian motion, mu ('drift') and sigma ('volatility') are constants.

Drift — is its constant directional movement.
Volatility — represents market volatility that is multiplied with a random input, which in this case is standard normal variable.

In this notebook we try to intervene into assumption /a)/, and not to allow historic prices to be the inputs for the model i.e. drift and volatility will not be based on historical prices.

Knowing that we need to replace inputs for drift (expected return) and volatility. We will done that by usig two different models.
For calculating expected returns it will be useed Black-Litterman model and for volatility it will be done by GARCH(1,1) model.
To reiterate; exected return as an input for M-C simulatio will be done by Black Litterman and for expected volatility it will be used GARCH(1,1)

Black-Litterman
Key information on the Black-Litterman model is provided in the notebook, but it needs to be explained here what is the logic behind it. 
The award-winning model on portfolio construction (Markowitz MPT) starts with the idea of expected returns and covariances - first calculated and then optimize for weights. The logic of B-L is the opposite, it tries to reverse engineer the process since expected returns (ERs) are impossible to know and what usually happens is that calculated weights are not the most optimal. So, two GSs practitioners decided to go another way around, assuming that we already know what are the weights. Since we use publicly traded instruments for calculation they assumed that the market cap of stocks/ETFs are the optimal weights. For example, if we want to pair AAPL and GOOG for optimization then optimal weights are their market caps. From this ground, they build implied expected returns, which we did in the notebook with SPY and TLT. However, markets are not usually correct (in equilibrium) and prices can deviate from fundamentals. That is why they decided to incorporate personal (subjective) views into the calculation. Finalyl     



