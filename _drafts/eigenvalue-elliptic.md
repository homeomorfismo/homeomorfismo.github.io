---
layout: post
title: "Adaptative procedural for computing eigenvalues"
description: "Discussion of the implementation of different approaches of error adaptivity methods for solving elliptic eigenvalue problems."
comments: false
keywords: "eigenvaluse, finite, elements, adaptivity"
---

# Defining a goal

The goal of this incipient research is to be able to compute the eigenvalues (specifically, the imaginary part) of the Helmholtz equation
\\[ \Delta u +k^2 n^2 u = \beta^2 u. \\]
for \\( k \\) a given wavenumber.
Notice that, for the *exact solution* and *any domain* \\(\omega \subset \Omega \\), the following holds
\\[ \Im(\beta^2) = \frac{1}{2\imath \lVert u\rVert_\omega^2} \int_{\partial \omega} (\partial_n \overline{u})u - (\partial_n u)\overline{u} \, \mathrm{d}s, \\]
where this expression is obtained by means of testing the previous equation against the conjugate of \\( u \\), conjugating the equation and testing it against the solution, and taking diferences.

Thus, we define the functional
\\[ j_\omega(u) := \frac{1}{2\imath  \lVert u\rVert_\omega^2} \int_{\partial \omega} (\partial_n \overline{u})u - (\partial_n u)\overline{u} \, \mathrm{d}s, \\]
for all subdomains \\( \omega \subset \Omega \\).
In particular, we set \\( J(u) := j_\Omega(u) \\).

## Local estimators?

Consider \\( \Omega_h \\) a triangulation of \\( \Omega \\).
Notice we could rewrite \\( J(u) \\) as
\\[ J(u) = \sum_{ T\in \Omega_h } \kappa_T j_T(u), \\]
for appropiated weights \\(\kappa_T \approx \frac{\lVert u \rVert_T^2}{\lVert u \rVert_\Omega^2} \\).

## Potential problems 

Despite the theory, seems hard to believe these functionals could work as their derivation holds for the *exact solution*.
Might be worth to analize the weak formulation and the functional setting.
A restriction operator \\(r_\omega: H^1(\Omega) \to H^1(\omega) \\) could play a role in this context.
On the other hand, a global phenomenon seems unlikely to be described by a local behavior.
We might want to experiment and analize the behaviour of the computed values.

## Error control for elliptic problems

There is a general framework for [optimal control to *a posteriori* error estimations in FEM](https://doi.org/10.1017/S0962492901000010a) by Rannacher and Becker, and further work in [elliptic eigenvalue problems](https://doi.org/10.1023/A:1014291224961) by Rannacher and Heuveline that suggesting how to proceed.

## Setting of the problem 

Let \\(\mathcal{a}(\cdot,\cdot\cdot)\\) the bilinear form associated to the weak formulation of the Helmholtz operator.
We want to find a pair \\((v,\lambda) \in H \times \mathbb{C} \\)  such that
\\[ a(v,\phi) = \lambda (v,\phi), \text{ for all } \phi \in H, \\]
where \\( (\cdot, \cdot\cdot) \\) is the standard \\(L^2\\) inner product, and \\( H \\) is an appropiate Hilbert space.
There is a natural counterpart of previous equation, that is given by the Galerkin finite element approximation of the previous equation (i.e., replace \\(H\\) with \\(H_h \subset H\\) ).
We can add a normalization constrain \\( \lVert v \rVert = 1 \\) to the above problem.

Define \\( V:= H\times \mathbb{C} \\) and \\( A: V \times V \to \mathbb{C} \\) given by 
\\[ A( (v,\lambda); (\psi,\chi) ) := -a(v,\psi) + \lambda(v,\psi)  + \overline{\chi} \left( \lVert v \rVert^2 -1 \right). \\]
Provided a functional \\( J: V \to \mathbb{R} \\), we want to compute a target \\(J(v,\lambda)\\) subject to  \\(A((v,\lambda);(\psi, \chi))=0\\).

## Lagrangian!

We seek to characterize the stationary points of \( L: V\times V \to \mathcal{C} \) given by
\\[ L((v,\lambda);(\psi, \chi)) := J((v,\lambda)) - A((v,\lambda);(\psi, \chi)). \\]

This induces a second problem \\( A' = J'\\), that requires to be analized for this context.

#TODO
## Main result estimators
## Refinement stratergies 
## Error-balancing stratergy
