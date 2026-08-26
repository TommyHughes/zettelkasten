---
type: note
date: 2026-08-25
tags: [math, mathematics, logic, model, theory, propositional logic, proposition]
source: https://www.youtube.com/playlist?list=PLVjjsDYdCTMTBGgesCNEcrmy3JFJjz_Mt
---

# Part 2: Syntax of Propositional Logic
[reference](https://www.youtube.com/watch?v=BPkgknWZ4tY&list=PLVjjsDYdCTMTBGgesCNEcrmy3JFJjz_Mt&index=2)

## Notation

$p, q$ are propositions that take on values of true or false. These are `sentence symbols` in $\mathcal{S}$. Think of this like an alphabet.

$\land, \lor, \lnot, \leftrightarrow, \rightarrow$ are `connectives`. Axiomatically we'll define $\lnot, \land$ as the only primitive connectives. The others we know we can derive from these two alone. This will simplify our proofs later.

Parentheses, (), are technically going to be considered primitive elements of our language. They are used to clarify the order of operations. For example we distinguish

$$\lnot (p \land q) \text{ from } (\lnot p) \land q$$

## Sentences

`Sentences` are defined by

(i) For every $p \in \mathcal{S}$, $p$ is a sentence.

(ii) If $\phi$ is a sentence, so is $\lnot \phi$.

(iii) If $\phi, \psi$ are each a sentence, then so is $\phi \land \psi$.

(iv) $\phi$ is a sentence iff it is a finite sequence of applications of i, ii, and iii. Note that this ensures we don't have to worry about questions like "is this a sentence" (e.g. $p\lnot$ would not be a sentence).

---

A quick note on the difference between `syntax` and `semantics`. 

You can think of syntax as "what is said". It's concerned with things like whether or not a specific arrangement of sentence symbols is valid.

Semantics is "what it means". It's about taking specific arrangements of sentence symbols and assigning sentences or meanings to them and evaluating if it becomes true or false.

Note the above implies a subtle distinction: a specific arrangement of sentence symbols, like

$$ p \land q$$

has no truth value. For truth or falsity we have to assign meaning to the symbols first. Then, under that assignment, we can evaluate if it is true or false. This is the case even when we have tautologies like 

$$p \lor \lnot p$$

which is still, itself, neither true nor false, but would be true under all assignments (it cannot be false).

# Part 2.5 A Simple Proof
[reference](https://www.youtube.com/watch?v=XEsfAPCleBg&list=PLVjjsDYdCTMTBGgesCNEcrmy3JFJjz_Mt&index=3)

It might be helpful for the upcoming videos if we just look at a very basic proof. Just so we know what it looks like and what to look out for as we develop our understanding.

**Theorem** Every sentence $\phi$ has the same number of open and closed parentheses.

**Proof**

We'll proceed by induction on the length of $\phi$ (number of symbols). For the base case, we take $\phi = p \in \mathcal{S}$. So $\phi$ has 0 left parentheses and 0 right parentheses.

Now suppose the claim holds for $n$.

If $\psi, \pi$ are a sentences of length $n$ then $\psi$ and $\pi$ each have the same number of left parentheses as right parentheses and

$$
\begin{align*}
    \phi &= \lnot ( \psi ) \\
    \phi &= (\psi \land \pi)
\end{align*}
$$

do too. By definition of a sentence (iv), that exhausts all cases.

$\square$

## Part 3:  Model Theory for Propositional Logic
[reference](https://www.youtube.com/watch?v=FTM3sgteZs4&list=PLVjjsDYdCTMTBGgesCNEcrmy3JFJjz_Mt&index=4)

