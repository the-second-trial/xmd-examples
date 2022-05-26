{{def=solutions}}

# Assignment: Real Calculus

## Author
Your Math Professor

```{{hidden}}
from sympy import *
```

Read the description on each single exercise, and provide a solution.

#### Computations {{if=solutions}}
Introducing the necessary quantities.

```{{output=none}}
x = symbols('x')
```

## Continuity
Evaluate whether function $f$ is continuous in $x = 0$:

$$
f(x) = \frac{\sin{x}}{x}
$$

If deemed non-continuous, expand on the nature of the discontinuity.

### Solution {{if=solutions}}
The definition of continuity for $f$ in $0$ is:

$$
\lim_{x \to 1} \frac{\sin{x}}{x} = \left. \frac{\sin{x}}{x} \right|_{x = 0}
$$

We have a canonical limit.

```{{output=latex}}
f_lim_val = limit(sin(x)/x, x, 0)
latex(f_lim_val)
```

But the function is not continuous because we cannot compute $f(0)$ since $0$ is not in the domain of $f$.

## Limits
Compute the value of the following limit:

$$
\lim_{x \to 1} \frac{\sin{x}}{x - 1}
$$

### Solution {{if=solutions}}
The limit's value is:

```{{output=latex}}
lim_val = limit(sin(x)/(x-1), x, 1)
latex(lim_val)
```

## Differentiation
Compute the first order derivative of $f$:

$$
f(x) = \log{\left(\frac{1}{\sin{x}}\right)}
$$

### Solution {{if=solutions}}
The first order derivative is:

```{{output=latex}}
latex(diff(log(1/(sin(x))), x))
```

## Integration
Compute the following integral:

$$
\int_{\frac{\pi}{4}}^{\frac{\pi}{2}} \frac{1}{\sin{x}+1} dx
$$

### Solution {{if=solutions}}

```{{hidden}}
f = 1/(sin(x)+1)
x1 = pi/4
x2 = pi/2
```

The primitive of the function is:

```{{output=latex}}
F = integrate(f, x)
latex(F)
```

We can apply the foundamental theorem of Calculus:

```{{output=latex}}
v2 = F.subs(x, x2)
v1 = F.subs(x, x1)
diff = v2 - v1
latex(v2 - v1)
```

Which gives the final value. Also validated by direct integration:

```{{output=latex}}
latex(integrate(f, (x, x1, x2)))
```
