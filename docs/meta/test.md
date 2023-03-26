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

```rkt title="Racket code"
(define (f x)
    (if (x > 1)
        (* x (f (- x 1)))
        1))
```

## Test for Admonitions

!!! note
    123
    
    123

???+ note "collapsible"
    here
    
??? info inline end "Lorem ipsum"

    Lorem ipsum dolor sit amet, consectetur
    adipiscing elit. Nulla et euismod nulla.
    Curabitur feugiat, tortor non consequat
    finibus, justo purus auctor massa, nec
    semper lorem quam in massa.
!!! info inline end "Lorem ipsum"

    Lorem ipsum dolor sit amet, consectetur
    adipiscing elit. Nulla et euismod nulla.
    Curabitur feugiat, tortor non consequat
    finibus, justo purus auctor massa, nec
    semper lorem quam in massa.
1

## Test for links

[home page](../index.md)

[Yaml](../blog/lang/yaml.md)
