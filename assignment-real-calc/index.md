{{def=solutions}}

# Assignment: Real Calculus

## Author
Your Math Professor

Read the description on each single exercise, and provide a solution.

#### Computations {{if=solutions}}
Introducing the necessary quantities.

```{{hidden}}
from sympy import *
```

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

The limit exists.
Nonetheless, the function is not continuous since we cannot compute $f(0)$ given that $x = 0$ is not in the domain of $f$.

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

Which can be computed symbolically:

$$
\lim_{x \to 1} \frac{\sin{x}}{x - 1} =
\lim_{x \to 1} \sin{x} \cdot \frac{1}{x - 1} =
\lim_{x \to 1} \sin{x} \cdot \lim_{x \to 1} \frac{1}{x - 1} =
\sin{1} \cdot \lim_{x \to 1} \frac{1}{x - 1} = \infty
$$

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

Applying the chain rule:

$$
f^\prime(x) = \frac{1}{\frac{1}{\sin{x}}} \cdot \left( \frac{1}{\sin{x}} \right)^\prime
$$

Deriving further and simplfying:

$$
f^\prime(x) = \sin{x} \cdot \left[ \left( \sin{x} \right)^{-1} \right]^\prime =
\sin{x} \cdot (-1) (\sin{x})^{-2} \cos{x} =
-\frac{\cos{x}}{\sin{x}}
$$

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
