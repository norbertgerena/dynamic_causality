# causal_ccm
Package implementing Convergent Cross Mapping for causality inference in dynamical systems as defined by [Sugihara et al (2012)](https://science.sciencemag.org/content/338/6106/496)

See `usage_sample.ipynb` for an example usage.

## To install
`pip install causal-ccm`

## To use
Say we want to check if X drives Y. We first define `ccm` using:
* `X` and `Y` - time series data
* `tau` - time lag (if `tau=1` we get `[t, t-1, t-2...]` as our shadow manifold embedding
* `E` - embedding dimension (default=2) for the shadow manifold
* `L` - time horizon to consider, defaults at length of time series X

We define `ccm`:
<br>`ccm1 = ccm(X, Y, tau, E, L) # define ccm with X, Y time series `

We check the strength of causality measured as correlation in prediction vs true (see Sugihara (2012))
<br>`ccm1.causality()`

We can visualize cross mapping between manifolds of X and Y
<br>`ccm1.visualize_cross_mapping()`

We visualize correlation of X->Y
<br>We stronger correlation = stronger causal relationship
<br>`ccm1.plot_ccm_correls()`



