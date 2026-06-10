### Mother Matrix

![Sylvester](/images/puncte/james_sylvester.jpg)

In 1850, mathematician **James Joseph Sylvester** (pictured below)
wrote a treatise on determinants and their properties. Among those,
the general method for computing determinants using expansions by
elements along a line or column. Like, for instance:

$$
\begin{vmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{vmatrix} =
1 \cdot \begin{vmatrix} 5 & 6 \\ 8 & 9 \end{vmatrix} -
2 \cdot \begin{vmatrix} 4 & 6 \\ 7 & 9 \end{vmatrix} +
3 \cdot \begin{vmatrix} 4 & 5 \\ 7 & 7 \end{vmatrix}
$$

This is the point where Sylvester names determinants *Matrix* (plural *Matrices*),
a word he took from Latin, where it means *birthing mother*. The mathematician
doesn't explain how he came up with that word, but a possible interpretation is
that determinants have an interesting property: they product self-similar objects
when computed (expanded as above). These objects were later called *minors*,
to keep with Sylvester's naming scheme.

Currently, mathematics draws a clear distinction between matrices and
determinants, but in Sylvester's treatise, the main use of matrices was
to compute their determinants, hence the inclination to see the latter as
a substitute for the former.
