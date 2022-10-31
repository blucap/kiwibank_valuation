## Valuation of Kiwibank using multiples ##

The code shows the valuation of Kiwibank on 22 August 2022, when the New Zealand government [announced its aquisition](https://www.beehive.govt.nz/release/kiwibank-remain-fully-kiwi-owned). 

I use a valuation method based on multiples, because traditional valuation approaches, based on discounting cashflows, do not always work well. The discount factor is low and volatile, which will result in large valuation swings.

The approach I take is well-documented and empirically tested. See, for example, this academic paper: [Equity Valuation Using Multiples Jing Liu, Doron Nissim, Jacob Thomas](https://onlinelibrary.wiley.com/doi/10.1111/1475-679X.00042).

The approach relies on a group of comparable firms. These firms are very similar to the firm one wants to value. The difference is that the comparable firms are all listed, so they all have a market value. For these firms, it is straightforward to find a representative P/E ratio (Price to Earnings) or Price to Book ratio. To determine the value of an unlisted firm, you multiply these ratios by the earnings or book value of the firm you are interested in.

To illustrate: suppose the average Price to Earnings ratio of the group of comparable firms is 15 and your (unlisted) firm reports a profit of 1 million dollars. In this case, investors in the group of comparable firms are willing to pay 15 dollars for a dollar of profit. With a 1 million dollar profit, the value of your firm is 15 million dollars. Likewise, using the Market to Book ratio: if the average M/B ratio is 1.25, and the value of book equity of your unlisted firm is 800 million dollars, its market value is 1 billion dollars. 

The challenging part of this approach is finding the right group of comparable banks. For Kiwibank, I chose banks from OECD countries plus banks from European countries that are not OECD members. I excluded banks from the US and Japan (because the accounting is different in the US, and because there are too many Japanese banks ending up in my sample). I also selected banks that are about the same size as Kiwibank and I filtered out banks with extreme values of critical variables, as  such profitability and capitalization. 

After determining the proper group of comparable banks, I determined the P/E ratio and the P/B (Price to Book) ratio and multiplied these ratios with Kiwibank's income number and book value.

<br>

I use Python to show you my workings. The data is from Datastream and the variables I use are shown below. You should be able to replicate my work.