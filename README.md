# A/B Testing: Ad vs PSA Conversion

A project I built to practice A/B testing on real data — using the Marketing A/B Testing dataset from Kaggle, where one group of users was shown an ad and a control group was shown a PSA instead.

Question: Did the ad actually lead to more conversions, or could the difference just be random noise?

### What I did
* Explored the data and checked group sizes (~564K in the ad group, ~23K in the PSA group)
* Ran a power analysis to check if the sample size was actually big enough to trust a result
* Used a two-proportion z-test (not a t-test, since conversion is a proportion, not a mean) to test significance
* Calculated the effect size and a 95% confidence interval, not just the p-value
* Checked whether the ad group beat PSA consistently across every day of the week, or if the result was being driven by one outlier day
### What I found
* The ad group converted at ~2.55% vs ~1.79% for PSA — a statistically significant difference (p < 0.05)
* That's a 43% relative lift, and it held up on every single day of the week
* I couldn't say whether this is worth it for the business, since I don't have cost-per-ad or revenue-per-conversion data — so I stopped at "statistically   significant," not "definitely worth the spend"
### Tools

Python, Pandas, Statsmodels, Matplotlib

### A note on limitations

The PSA group was slightly under the sample size a power analysis said would be needed for the assumed effect — doesn't invalidate the test, but worth being upfront about. This is also Kaggle data, not something I ran myself, so I can't fully verify random assignment the way a real experiment would guarantee
