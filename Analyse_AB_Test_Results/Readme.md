# Analyze A/B Test Results
![Hypotheses Rules](http://www.plantuml.com/plantuml/png/PP6zZkem48LxdkBS3X3tXnO1egI_k_LgI2R4mdYyzfWeRxyJWrYXBQ94n_g-cHCVibBIuPHdI_ndnNl4SOoYFMUsR0bg6acj2sUeeCP8nNFUsE4IRptZ-F4Fyr2yNy1bQ2gC4tUI6ACKDE8zDmeA8rfI-lF2bLp8-n5PIJbFViFC4WJSTHCdoL9Iw20u9oanWnA3FmryTL5exRsknurS8wjjlJ9L-2qtJfvYj03zirx5Ap8dhvm2gRjnRJ5C8mV68CMtyEx2KB5QjTwTsrv9-xqDtlwjNpOpABcGGU6-7h8x1qY7B5V6nOLsyw3cknMszkntYmVzwbp_SDh6a1WbEtLIfLCo_VMd4xzsC2rC-ssT7JYqThrV)

![Hypotheses and Errors](http://www.plantuml.com/plantuml/png/VP31IWD138Rl-nGvQX2rLwdIWqgzUB7U2f9jOsTWp0oJhCk-lMlMoYheBVcJoVSnApMgrhVQ83onmNE1zL2o1LRMhMW62sGmzj3dgWpv5RZMiOIe7YFQK1WUfXZnga64n_orDJO8czenbApHuZlF8k437ID0t4ntxlmXekyjtyZ23QKIQ7dXjSUtl8lxA0Ste6HSnI_1oVfbSUfg8-1iAtrW0TfPHoaDdzFBx-cvNxg-fwG_xM0IEPhCF5gslpMaIya9__8Nl_YEd_r4isBPzwr-0000)

**Example**:

We set up the null and alternative hypotheses in the following way:

![H_0: mu_n - mu_0 <= 0](http://www.plantuml.com/plantuml/png/SoWkIImgoKqioU3oY3UmKiWjZSzJq0LH1WesjWe6N0wfUIaWQG00)

and

![H_1: mu_n - mu_0 > 0](http://www.plantuml.com/plantuml/png/SoWkIImgoKqioU3oY3UqKiWjZSzJq0LH1Wfs2WPS3gbvAI1P0000)

where ![mu_0](http://www.plantuml.com/plantuml/png/SoWkIImgoKqioU3ABOqtu798pKi1yG00) is the mean revenue of the old campaign, and ![mu_1](http://www.plantuml.com/plantuml/png/SoWkIImgoKqioU3ABOtFut98pKi1yG00) is the mean revenue of the new campaign.
- The null is that the mean revenue of the new campaign is less than or equal to the mean of the old campaing.
- The alternative is that the mean revenue of the new campaign is larger than the mean revenue of the old campaign.
- **Type I Error**: Deciding the new page is better, but really the old page is better.
- Type II Error: Deciding the old page is better, but really the new page is better.

![Test hypotheses](http://www.plantuml.com/plantuml/png/VLF1Sjem4BthAxRf0Pa23LS7c4mxq-cvpPrPp8BLaIMFLYQXau_lIWP3KYOwQRHlttkxVdxaY25sZLNb4t64-jZwM1CJlwfonDYqbaPG8uC3ls4A1up6EmQ_Wv7qHiFHL3nQg7BHOAnNFzVt9JGTBE7ETTQk6q9t1uklkQZEc7d6V7e3Ec54DyiQjrzlXJqNMVXSEmlejhwPLRKt5UdUtGJO_AMbdj_BcRYYcAK6ZI-6b_FYuJqRnstF9HTzGoXrP4y7j6zLdGyDMZqOdi1_p1F8BXA7B2kZXABtERjigtUOKB-xjlLCC1uF-1KC2kEnaZg5zSPtBja-WvJrprVFGmDCGGz4qyjx8P_dEzgginYJM3kLwJeI_bOkmg0l8w_WIhCuMOKlrv05YFvxY9hAKLhsXI7WKNYuGekXWBqv40F2D-zjCjRNdqsi-tL1DiCtUi_S0qKRVEj3Ic0Au5FewDJyeCmET1-lFDCAqBOrda9LGAp9WJuI5whyWSP2z13e3rKnbVAgXl0RNYcoJA2T5_YlZs1kQtRgyzxRRNcrLp2SyU9tWnjZJJmcm_qV98d9nHo8b0UbVG3l21eV2EWb1ce8Z8CT7b9bb-5e8mKdBGSgPDfRVhAiB6NsgXx5MTVOVm00)

# References
