2209202316:12
tags: #archive 
# EC SW Projective Representation

The ***general*** Weirstrass equation is $E: y^2+a_1y+a_3y=x^3+a_2x^2+a_4x+a_6$.
The ***short*** Weirstrass equation is: $E: y^2 = x^3+ax+b$.

## Projective space
The points are usually described as in the affine space $(x,y) \in \mathbb{A}^2$.$$E(\mathbb{F})=\{(x,y)\in\mathbb{A}^2:y^2=x^3+ax+b\}\cup\mathcal{O}$$
A more precise way to describe the point of infinity (since it's included in the space) is the projective space.
In the projective space we work with lines that goes through the origin the (n+1)-space (compared to the n-space of affine space).$$(x,y)\in\mathbb{A}^2 = (\lambda x,\lambda y,\lambda)\in \mathbb{P}^2(\mathbb{F})\text{ where }\lambda\in\mathbb{F} $$
$\mathbb{P}^2=\mathbb{A}^3\setminus \{0,0,0\}$ modulo the fact that points will be in the space only "once" if they're equivalent to some $\lambda$: if $(x_1,y_1,z_1)=(\lambda x_2, \lambda y_2, \lambda z_2)$ then only the first will be in $\mathbb{P}^2$. (this is a congruence)

The congruence is noted $(X,Y,Z)$ and it represents all the point on the line in $\mathbb{P}^2$ that corresponds to $(x,y) \in \mathbb{A}^2$.

## From affine to projective coordinates
$(x,y)\rightarrow(x,y,1)$ and $(X,Y,Z)\rightarrow(\frac{X}{Z},\frac{Y}{Z})$.
$\mathcal{O}$ is represented by $(0,1,0)$ which is not possible to convert back to affine, which make sense because it's not in the space.

$E_{\mathbb{P}}$ is called the projective closure of E.
### Note
There's other way of doing the substitution $x=\frac{X}{Z},y=\frac{Y}Z$. For example the Jacobian Coordinates uses: $x=\frac{X}{Z^2},y=\frac{X}{Z^3}$ 

## Speeding up EC computation
Computations in EC groups are more complex than in normal groups.
Which can be pretty good in some cases, because it's more difficult for attackers to compute as well!
For example some algorithm that are aiming to solve the DLP in subexponential time are not working in EC computations.
Because of that we can take way smaller fields to do ECC. 

## Optimizing operations in ECC
The explicit formula would not be used in practice and SW form is not an optimal curve model.

To optimize operations in SW we can use the projective space because it avoids an inversion (the most expensive operation by far)

There are other forms of EC that are being used depending on the curve. All forms are isomorphism to the SW form.
## Affine Form of SW 
**non singular** when $det\neq0$, making the group law non ambiguous.
## Affine point compression
- $\forall x\in\mathbb{F}$, there are max two possible $ys\in\mathbb{F}$ st $(x,y)\in E(\mathbb{F})$
- $y$ can be computed from $x$.
- We can store only $x$ along with a _sign bit_ to say which root of $y^2$ we want as $y$.

If you have 3 spare bits: first is telling you if it's compressed or not, second if it's the point of infinity and the 3rd if you take the largest root or not

If $P\in E(\mathbb{F})$ and $P=(x,0)$, $P$ is called _self inverse_.
## Projective form of SW
Points in SW form over $\mathbb{F}$ satisfy: $E:Y^2\cdot Z=X^3+a\cdot X\cdot Z^2+b\cdot Z^3$
## Additive inverse in projective form
Additive inverse: $(X,Y,Z)\cdot(X,-Y,Z)=e$ 

---
## References
1. [[Projective Space for ECC SW]]
2. [[EC point compression]]