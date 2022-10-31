## Valuation of Kiwibank using multiples ##

The code below shows the valuation of Kiwibank at the moment of the announcement of the acquisition by the New Zealand government on 22 August 2022. I use a valuation method based on so-called "multiples", because traditional valuation approaches, based on discounting cashflows, do not work well. The discount factor is low and volatile, which will result in large valuation swings.

The approach I take is well-documented and empirically tested. See, for example, this academic paper: [Equity Valuation Using Multiples Jing Liu, Doron Nissim, Jacob Thomas](https://onlinelibrary.wiley.com/doi/10.1111/1475-679X.00042).

The approach relies on a group of comparable firms. These firms are very similar to the firm one wants to value. The difference is that the comparable firms are all listed, so they all have a market value. For these firms, it is straightforward to find a representative P/E ratio (Price to Earnings) or Price to Book ratio. To determine the value of an unlisted firm, you multiply these ratios by the earnings or book value of the firm you are interested in.

To illustrate: suppose the average P/E ratio of the group of comparable firms is 15 and your firm reports a profit of $\$1 million. Its value would then be $\$15 million.

The challenging part of this approach is finding the right group of comparable firms. For Kiwibank, I chose banks from OECD countries and European banks. I excluded banks from the US and Japan (because the accounting is different in the US, and because there are too many Japanese banks ending up in my sample). I also selected banks that are about the same size as Kiwibank and I filtered out banks with extreme values of critical variables.

After determining the proper group of comparable banks, I determined the P/E ratio and the P/B (Price to Book) ratio and multiplied these ratios with Kiwibank's income number and book value.

<br>

I use Python to show you my workings. The data is from Datastream and the variables I use are shown below. You should be able to replicate my work.