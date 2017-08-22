---
layout: post
title: Sigma Algebra
---

A collection of subsets of $$S$$ is called a **Sigma Algebra** denoted by $$\mathcal{B}$$, if it satisfies:

1. \\(\emptyset \in \mathcal{B}\\)
2. \\(A \in \mathcal{B} \implies A^\complement \in \mathcal{B}\\) 
3. \\(A_1,A_2,A_3,... \in \mathcal{B} \implies \bigcup_{i} A_{i}\\) 

Which can be interpreted as:

1. The empty set is an element of $$\mathcal{B}$$
2. If $$A$$ is in $$\mathcal{B}$$ then the complement of $$A$$ (i.e. $$A^\complement$$) is also in $$\mathcal{B}$$
3. For any set of $$A$$s in $$\mathcal{B}$$, the union of all those $$A$$s is also in $$\mathcal{B}$$

If $$S$$ is empty, then we don't have much to speak of. If $$S$$ is not empty, there is always the trivial sigma algebra $$\mathcal{B}=\{\emptyset,S\}$$. If $$S$$ has some structure, then $$\mathcal{B}=\mathcal{P}(S)$$<sup>1</sup> is also a sigma algebra.

#### **I wonder how many sigma algebras there are for a set of size $$n$$?**

Example:

Let $$\left\vert{S}\right\vert=3$$ with $$S=\{1,2,3\}$$

$$\mathcal{B}_1=\{\emptyset,S\}$$<br>
$$\mathcal{B}_2=\{\emptyset,\{1\},\{2,3\},S\}$$<br>
$$\mathcal{B}_3=\{\emptyset,\{2\},\{1,3\},S\}$$<br>
$$\mathcal{B}_4=\{\emptyset,\{3\},\{1,2\},S\}$$<br>
$$\mathcal{B}_5=\{\emptyset,\{1\},\{2\},\{3\},\{1,2\},\{1,3\},\{2,3\},S\}=\mathcal{P}(S)$$<br>

So when $$n=3$$, there are 5 sigma algebras total. I believe in general, the answer is related to [Bell numbers](https://en.wikipedia.org/wiki/Bell_number):

$$B_n=\sum_{k=0}^{k=n} {n\brace k}$$, where $${n\brace k}$$ are the [Sterling numbers of the second kind](https://en.wikipedia.org/wiki/Stirling_numbers_of_the_second_kind).

To help substantiate the claim, we find the third bell number:

$$B_{3}=0+1+3+1=5$$

Of course this doesn't constitute a proof. But it does satisfy my suspicions :)

<sup>1</sup> Read as the **power set of $$S$$**, which is the set of all subsets of $$S$$.