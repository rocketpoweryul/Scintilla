# Scintilla
A top-down approach to finding a trading strategy that meets my investment objectives, using Amibroker

I decided to review what I want out of trading and determine quantitatively what that means, and what strategies I can employ to do this.

I won't paste my beliefs here, because they are personal, but the output of this of what I want from my trading strategy is here, pasted from my OneNote, with some redactions for privacy:

So, I need to trade where:
	1) I make on avg 25 trades a month, or 300/yr
	2) I make at least 3 times my risk
	3) That risk is at least ~1% of my main acct) per trade, so I need to make 3% per trade (of portfolio equity)
	4) I generally don't like to lose more than 5% per trade on avg (due to Minervini conditioning, so maybe I could be convinced otherwise by validated data to allow more)
	5) This means I need to make at least 15% per winning trade, which is on par with what any reasonable position/IBD or swing trading gain could hope for on avg
	6) I like stocks that bounce of the 20-day SMA, and base on top of the 50-day
	7) I like to buy low risk entry breakouts or pullbacks, usually with VCP and/or pocket pivot characteristics

So trade entry characteristics are:
	1) Logical stop is < 5%, such as the last contraction width, or the pullback distance to the KMA
	2) Average profit from such an entry meets the above requirements
		a. If multiple entries exist that meet this criteria, its contribution to the aggregate is what counts
		b. This implies I need to be right 1/3 of the time, and make 3 times my avg loss on avg when I do
	3) I could pull in the stop if it is low-risk to my avg profit to do so, to further reduce the avg loss, and give some margin to the avg win and win pct performance vectors

Trade Management Characteristics:
	1) I like the comfort of the free-roll concept, sell half at 2x your risk, and set the stop to breakeven. 
		a. Actually this is better than free-roll because you are guaranteeing 1R profit after 2R is reached. A true free-roll is leaving your original stop after selling at 2R and follow a KMA
		b. Thus to make 15% avg profit on the trade, the backhalf needs to double the performance of the first half:
			i. First half is sold at 2R or 10% profit from the trade, netting 1R right off the bat, and leaving open an additional 1% in equity in profit
			ii. Second half is sold at the 4R level or greater, or 20%, but this time since the additional 2R was only with half the position size, we net an additional 1% + the 1% profit we kept open from before for an additional 2% equity profit
			iii. This gives a grand total of 3% equity profit over a 20% span of the stock's performance, for an average gain on each half of (10+20)/2 = 15 %, which is 3 times our risk and verifies the trade executed successfully
	2) So this begs the question, should we not sell half until our avg win profit is secured? i.e,:
		a. Buy at the breakout or pullback
		b. Sell half at 3R, trail the rest to a KMA?
		c. This allows us to make everything we need with less performance required from the stock (15% vs 20%), however we keep our open profits at risk for another 5%
		
Approach to finding stocks that meet the above characteristics:
	1) Find stocks that trend in the manner that meets the above needs:
		a. Find events in a stock time series where ALL of the following is true:
			i. Stock is in a stage 2 uptrend
			ii. The stock's 20-day SMA has increased by at least 20%
			iii. The low of the stock is never below the 20-day SMA during that time period
			iv. Time series consists of HLOCV data
		b. Use an Amibroker exploration to sort this out, although you will have survivorship bias
	2) Determine specific entry points that meet the following criteria
		a. They precede the stocks run per (1)
		b. They give a low-risk entry point, where the logical stop fits a 5% logical stop will represent about ~1% of my acct equity
		c. The low-risk entry point is generally a VCP or pullback that can also show pocket pivot characteristics, usually within a cup with handle or high handle (cap base), double bottom with (high) handle, flat or square base, HTF/PP. Cheats can be used given correct characteristics
	3) Backtest the specific entry points to see if they provide the expectancy desired
	4) Repeat if necessary or consider using machine learning to converge on entry points with an edge

Constraints:
	- Don't use current library, coding is terrible
	- All math must be matrix oriented to avoid inability to backtest. All code must be backtestable!
	- Simplify everything wrt trade mgmt, maximize portfolio mgmt

OKR:
Double my liquid net worth

KPIs:
	- Profit so far
	- Expectancy
	- Number of trades
	- Average loss
	- Average win
CAGR![image](https://github.com/rocketpoweryul/Scintilla/assets/5898307/8ae2a444-1e02-4b61-be8d-f27ada4ae7fb)
