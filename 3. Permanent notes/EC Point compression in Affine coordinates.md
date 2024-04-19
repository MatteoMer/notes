2209202322:37
tags: 
# EC Point compression in [[Affine Space|affine coordinates]]

Sometimes, we want to compress a point and make it possible to know the point using less storage. 

For example in SRS or CRS.

To do so we use an interesting property, that $y$ can be computed from $x$ because  $\forall x\in\mathbb{F}$, there are max two possible $ys\in\mathbb{F}$ st $(x,y)\in E(\mathbb{F})$. 

Because of that, we can store only $x$ along with a _sign bit_ to say which root of $y^2$ we want as $y$.

### Note
If you have 3 spare bits: first is telling you if it's compressed or not, second if it's the point of infinity and the 3rd if you take the largest root or not

If you have 3 spare bits: first is telling you if it's compressed or not, second if it's the point of infinity and the 3rd if you take the largest root or not

---
## References
1. [[EC SW Projective Representation]]