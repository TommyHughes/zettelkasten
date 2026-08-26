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

# Part 3:  Model Theory for Propositional Logic
[reference](https://www.youtube.com/watch?v=FTM3sgteZs4&list=PLVjjsDYdCTMTBGgesCNEcrmy3JFJjz_Mt&index=4)

The basic idea is **models are possible worlds**. Take a very simple example where

$$\mathcal{S} = \{ p, q \}$$

A sentence like $p \rightarrow q$ can be either true or false depending on the values of $p$ and $q$. In other words, **in some possible worlds the sentence is true, and in other possible worlds, it's false**.

---

A `model`, $A$, for sentence symbols $\mathcal{S}$ simply is $A \subseteq \mathcal{S}$.

---

Intuitively, we hope this will result in something like

$$
\begin{align*}
p \in A &\text{ means } p = \top \\
p \not\in A &\text{ means } p = \bot
\end{align*}
$$

Later we'll want to expand from expecting models being able to simply tell us which senteces are true to being able to "exhibit an object in which those sentences are true".

## Truth in a Model

---

For a sentence $\phi$ and model $A$, we write

$$A \models \phi$$

which can be read "$A$ models $\phi$" or "$A$ is a model of $\phi$". It is defined as follows:

(i) If $\phi = p \in \mathcal{S}$ then $A \models \phi$ iff $p \in A$.

(ii) If $\phi = \lnot \psi$ for a sentence $\psi$ then $A \models \phi$ iff $A \not\models \psi$.

(iii) If $\phi = \psi \land \pi$ then $A \models \phi$ iff $A \models \psi$ and $A \models \pi$

---

We'll utilize simplfying notation and say that

$$\models \phi$$

if for every model $A$

$$A \models \phi$$

Equivalently, we'll say $\phi$ is `valid`. As an example of a valid sentence we have

$$\phi = \lnot p \lor p$$

# Part 4: Completeness Theorem for Prop Logic
[reference](https://www.youtube.com/watch?v=wPEHYTEPWuw&list=PLVjjsDYdCTMTBGgesCNEcrmy3JFJjz_Mt&index=5)

Our goals for this section will be to

1. Build a method for determining the `validity` of statements.

1. Show this method is correct.

As a motivating example to build our intuition consider

$$\mathcal{S} = \{ x_1, \ldots, x_n, \ldots \}$$

How do we know

$$ x_1 \lor \lnot x_1 $$

is valid? We'd need to show this is true in all models of $\mathcal{S}$. However, in this case there are infinitely many models of $\mathcal{S}$ since $\mathcal{S}$ is infinite. This means we can't actually go through each model and check.

---

Considering $\mathcal{S} = \{ x_1, x_2, \ldots \}$ An `assignment` is a sequence 

$$\alpha_1, \alpha_2, \ldots$$

where $\alpha_i = \mathbb{T}$ or $\alpha_i = \mathbb{F}$

---

Intuitively we are determining which sentence symbols are true and which are false.

---

The `value` of $\phi$ given some assignment $\alpha_1, \ldots, \alpha_n$ is

(i) If $\phi = x_i \in \mathcal{S}$, the value of $\phi$ is $\alpha_i$.

(ii) If $\phi = \lnot \psi$ the value of $\phi$ is the opposite of $\psi$.

(iii) If $\phi = \psi \land \pi$ the value of $\phi$ is true only when the value of $\psi$ and the value of $\pi$ are true.

---

To try to help illustrate the distinction within the related concepts we've discussed we summarize in the table.

| Syntax | Model | Value |
|-|-|-|
| Is $\phi$ even a sentence? | Is $\phi$ true in a model? | Can we can compute validity |

A further note of clarification: you might have noticed assignment works finitely: $\alpha_1, \ldots, \alpha_n$ whereas Models could be infinite. Recall though that a sentence $\phi$ is necessarily finite (see above) and therefore only requires a finite assignment to compute its value.

Gemini added another summary included in the table below:

| Property | Formula | Intuition |
|-|-|-|
| Soundness | $\Gamma \vdash \phi \rightarrow \Gamma \models \phi$ | If my proof system can derive it, is it actually true in the real world? Our proof rules don't produce false garbage. |
| Completeness | $\Gamma \models \phi \rightarrow \Gamma \vdash \phi $ | If something is universally true in every possible world, is our proof system strong enough to find a proof for it. |

---

We say

$$\vdash \phi$$

if for all assignments $\alpha_1, \ldots, \alpha_n$ the value of $\phi$ is true. Equivalently, we say $\phi$ is a `tautology`.

---

## The Completeness Theorem (or at least part of it)

**Theorem**

$$\vdash \phi \text{ iff } \models \phi$$

---

**Proof Idea**

I didn't watch but I suspect the basic idea is $\phi$ is always finite and so even if $A$ is infinite, $\phi$ is always a finite subset of $A$ and then it proceeds exactly like you'd expect.