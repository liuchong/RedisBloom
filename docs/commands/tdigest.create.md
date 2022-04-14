Allocate the memory and initialize the t-digest.

#### Parameters:

* **key**: The name of the sketch.
* **compression**: The compression parameter. 100 is a common value for normal uses. 1000 is extremely large. See the further notes bellow. 


**Further notes on compression vs accuracy:**
Constructing a T-Digest requires a compression parameter which determines the size of the digest and accuracy of quantile estimation. 
The scaling of accuracy versus the compression parameter is illustrated in the following figure retrieved from ["Ted Dunning, The t-digest: Efficient estimates of distributions, Software Impacts,Volume 7,2021"](https://www.sciencedirect.com/science/article/pii/S2665963820300403).

<img src="images/tdigest-accuracy-vs-compression.jpg" alt="The scaling of accuracy versus the compression parameter"/>

@return

@simple-string-reply - `OK` if executed correctly, or @error-reply otherwise.

@examples

```
redis> TDIGEST.CREATE t-digest 100
OK
```