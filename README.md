# trading-sim
A common trading rule says: buy when the 30-day moving average goes above the 180-day moving average (the BUY rule), and sell when it goes below (the SELL rule).

Let's assume we buy 1 share at the closing price the very day the BUY rule triggers, and sell that 1 share the SELL triggers. (Now this is a bit tricky as we need that day's closing price to compute the average, but let's gloss over that). At the end, we want the overall return.

To achieve the above:

    Step 01: Compute the daily return ratio i.e., the ratio of today's closing price to yesterday's closing price.
    Step 02: Create a mask of the days when we hold the share, i.e., the BUY has triggered, but the SELL rule has not.
    Step 03: Compute the cumulative return ratio over the days of the mask. This is the product of the return ratios on the days I hold the share.

