# Callable Asian Option Valuation

We present a new model named callable Asian options.  Such options allow their underwriters to call the options back from investors at a specified time and with a specified amount prior to option maturities.  A hybrid of Monte Carlo simulation and the closed form Michael Curran’s solution is employed in pricing.

Let   be a price process of a given underlying asset,   be a set of reset dates and   be a payoff settlement date.  The callable Asian option with the underlying S is a European type derivative security whose matured payoff at the settlement date is given by

	 	(1)

where N is the notional principal,   is the call-put index, K is the strike, and A is the arithmetic average of    , with equal weight.  At time , typically  , if the underlying stock price   is above a barrier  , the deal will be cancelled automatically and the owner of the option will be paid a fixed amount C.  Users can also specify that it is up to the underwriter to decide whether the option is cancelled.

The deal can be forward starting.  In this case, the strike K is not pre-determined in the contract, but rather a stock price   at a future start date  .

Equation (1) indicates that the principal is protected.  A payoff type without notional is also allowed, which removes the first part of equation (1) at maturity; but the owner of the option can still receive the call amount if the option is called on the call date (of course this call amount will be greatly reduced in the contract).

Pricing of callable Asian options involve two stages.  The first stage is for the cases when the current value date is prior to the call date.  This is our focus.  The second is for the cases when the current value date is beyond the call date; in these cases, either the option was called and therefore deceased, or the remaining is just a regular Asian option, which is not in our scope.

Let t be the current value date, assume  .  At the call date  , the value of the option if the cancellation is automatic, is given by

	 	(2)

where   is the indicator function,   is the discount factor.  If the cancellation is not automatic, then from the underwriter’s point of view, the above expression should be changed to

	 	(3)

The current value at time t is then

	 .	(4)

When the current value is computed using equation (4),   in equations (2) and (3) should be the forward discount factor.

A hybrid of Monte Carlo simulation and the Michael Curran’s closed-form solution can be employed to price callable Asian options.  The former is used to propagate the stock price from the value date to the forward start date to determine the strike if the deal is forward starting, and to the call date to obtain a price to be compared with the call amount.  The latter is used to price the Asian option value.

Formulae (2) to (4) are in a world that is forward risk-neutral with respect to a specific currency  .  As a result, the notional principal N is measured in the currency  , and the discounting factor should be calculated by a   zero curve given at the value date.  If the underlying asset is measured in another currency  , the governing price dynamics of this underlying asset in the risk-neutral world of   should be written as

			 

where   is the short rate of  ,   is the dividend yield of the asset,   is the correlation coefficient between the asset price and the cross-currency exchange rate,   is the volatility of the asset price,   is the volatility of the exchange price, and   is the Wiener process.  All these parameters are assumed deterministic.

It should be noted that we allow a separate volatility of stock,  , for pricing the Asian option, other than the volatility of stock,  , for propagating the stock price in Monte Carlo simulation.  This separate volatility is actually the forward volatility of stock from the call date to the option maturity date.

