# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

$$T(n) = T(n/13) + 5$$
$$     = T(n/13^2) + 5 + 5$$
$$     = T(n/13^3) + 5 + 5 + 5$$
$$     ...$$

After $k$ substitutions:
$$T(n) = T(n/13^k) + 5k$$

The recursion stops when $n/13^k \leq 1$
This means: $n/13^k = 1$
Therefore: $k = \log_{13}(n)$

Substituting this $k$:
$$T(n) = 1 + 5\log_{13}(n)$$

So, $T(n) ∈ \Theta(\log n)$

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

$$T(n) = 13T(n/13) + 5$$
$$     = 13[13T(n/13^2) + 5] + 5$$
$$     = 13^2T(n/13^2) + 13\cdot5 + 5$$
$$     = 13^2[13T(n/13^3) + 5] + 13\cdot5 + 5$$
$$     = 13^3T(n/13^3) + 13^2\cdot5 + 13\cdot5 + 5$$
$$     ...$$

After $k$ substitutions:
$$T(n) = 13^kT(n/13^k) + 5(13^{k-1} + 13^{k-2} + ... + 13 + 1)$$

When $n/13^k = 1$, $k = \log_{13}(n)$

Therefore:
$T(n) = n\cdot T(1) + 5(n - 1)/(13-1)
     = n + \frac{5(n-1)}{12}
     = 2n$

So, $T(n) ∈ \Theta(n)$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$
$$T(n) = 13T(n/13) + 2n$$
$$     = 13[13T(n/13^2) + 2(n/13)] + 2n$$
$$     = 13^2T(n/13^2) + 2n + 2n$$
$$     = 13^2[13T(n/13^3) + 2(n/13^2)] + 4n$$
$$     = 13^3T(n/13^3) + 6n$$
$$     ...$$

After $k$ substitutions:
$$T(n) = 13^kT(n/13^k) + 2kn$$

When $n/13^k = 1$, $k = \log_{13}(n)$

Therefore:
$$T(n) = n + 2n\cdot\log_{13}(n)$$

So, $T(n) ∈ \Theta(n \log n)$

## Sources 

Mergesort video where we solved a similar recurrence relation.
