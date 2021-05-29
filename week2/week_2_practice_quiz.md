week\_2\_practice\_quiz
================
Haixu Leng
5/29/2021

## 1. Consider a random variable X that has a normal distribution with a mean of 5 and a variance of 9.

Calculate *P*\[*X* &gt; 4\].

``` r
pnorm(4, mean = 5, sd =3, lower.tail = FALSE)
```

    ## [1] 0.6305587

## 2. What is the expected value of Y give that x = 5.

*Y* =  − 3 + 2.5*x*, *ϵ* ∼ *N*(0, *σ*<sup>2</sup> = 4)

``` r
y = -3 + 2.5 * 5
y
```

    ## [1] 9.5

## 3. Given the SLR model in Question 2, what is the standard deviation of Y when x is 10?

The standard deviation should be determined by *σ* of *ϵ*, which is 2.

## 4. For this question, use the built-in trees dataset in R. Fit a simple linear regression model with Girth as the response and Height as the predictor.

What is the slope of the fitted regression line?

``` r
result = lm(trees$Girth ~ trees$Height)
```

The slope is 0.2557471

## 5. What is the value of *R*<sup>2</sup> for this fitted SLR model?

``` r
x = trees$Height
y = trees$Girth
y_hat = coefficients(result)[[1]] + x * coefficients(result)[[2]]
SST = sum((y - mean(y))^2)
SSReg = sum((y_hat - mean(y))^2)
SSE = sum((y_hat - y)^2)
R_2 = SSReg / SST
```

Result: *R*<sup>2</sup>= 0.2696518.
