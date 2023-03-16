# Test page

## Test page

https://squidfunk.github.io/mkdocs-material/reference/

## Test for formula

$$
a = \frac{1}{2} \sum_{\sigma}\mathbb{I}
$$

The homomorphism $f$ is injective if and only if its kernel is only the 
singleton set $e_G$, because otherwise $\exists a,b\in G$ with $a\neq b$ such 
that $f(a)=f(b)$.


## Test for codes

```python
def f(n):
    return n * f(n-1) if n > 1 else 1

print(f(3))
```

```rkt
(define (f x)
    (if (x > 1)
        (* x (f (- x 1)))
        1))
```

## Test for Admonitions

!!! note
    123
    
    123
    
## Test for 
