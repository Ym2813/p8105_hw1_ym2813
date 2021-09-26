p8105\_hw1\_ym2183
================
Anna Ma
9/26/2021

## Problem 1

### 1.1 Creating the Data frame

``` r
problem1_df <- tibble(
  vec_random = rnorm(10, mean = 0, sd = 1),
  vec_logical = vec_random > 0, 
  vec_char = c("a","b","c","d","e","f","g","h","i","j"),
  vec_factor = factor(c("low","medium","high","medium","high","low","low","medium","high","high"))
)
```

### 1.2 Take mean of each variable

``` r
#1.Random sample of standard normal distribution 
mean(pull(problem1_df,vec_random))
```

    ## [1] 0.03975712

``` r
#2.Logical vector
mean(pull(problem1_df,vec_logical))
```

    ## [1] 0.5

``` r
#3. Character vector
mean(pull(problem1_df,vec_char))
```

    ## Warning in mean.default(pull(problem1_df, vec_char)): argument is not numeric or
    ## logical: returning NA

    ## [1] NA

``` r
#4. Factor Vector 
mean(pull(problem1_df,vec_factor))
```

    ## Warning in mean.default(pull(problem1_df, vec_factor)): argument is not numeric
    ## or logical: returning NA

    ## [1] NA

We can take the mean for the random sample of standard normal
distribution and the logical vector. However, the mean of the character
vector and factor vector cannot be taken.

### 1.3

``` r
#1.Logical vector
as.numeric(pull(problem1_df,vec_logical))
#2. Character vector
as.numeric(pull(problem1_df,vec_char))
#3. Factor Vector 
as.numeric(pull(problem1_df,vec_factor))
```

The logical vector and the factor vector was converted. In the logical
vector, TURE values are converted to 1, and the FALSE values are
converted to zero. In the factor vector, the levels were converted to
numeric value 1 to 3 indicating 3 different levels. The character vector
was not converted to numbers. This explain why the logical vector has a
mean whereas the other vectors does not. The mean of the the logical
vector shows the average of the sample and how likely the sample is
true; the character values do not have intrinsic numeric value and
therefore does not have a mean; finally, the factor vector does not have
a mean even though the levels are numeric because levels are similar to
ranks, whose mean has no numerical meaning.

## Problem 2
