* Logical connectives allow us to create new propositions from existing ones.
* The truth value of the new propositions depends on the truth value of its components.
* The dependency is made through a table called a truth table.
# Negation
*The proposition $\overline{p}$ (often also denoted $\neg{p}$ or $\sim p$, which is read "not $p$", is true that whose truth value is always distinct of p.*
# Or/Disjunction
*The proposition $p \lor v$, which is read "$p$ or $q$", is true when at least one of the propositions $p$ or $q$ is true.*
# And/Conjunction
*The propostion $p \land q$, which is read "$p$ and $q$", is true when both propositions $p$ and $q$ are true.*
# Implication
*The proposition $p \implies q$, which is read "$p$ implies $q$" or "if  $p$, then $q$", its false only when $p$ is true and $q$ is false.*
# Equivalence
*The proposition $p \Longleftrightarrow q$, which is read "$p$ is equivalent to $q$" (or "$p$ if and only if $q$), its true when $p$ and $q$ has the same value of truth and false when not.*
# Tautologies
*A tautology is a proposition that, regardless of the truth value of the propositions that constitute it, is always truth.*
## Basic tautologies
### Dominance
$$
p \lor V \Longleftrightarrow V
$$
$$
p \land F \Longleftrightarrow F
$$
### Identity
$$
p \land V \Longleftrightarrow p$$
$$
p \lor F \Longleftrightarrow p
$$
### Idempotence
$$
p \land p \Longleftrightarrow p
$$
$$
p \lor p \Longleftrightarrow p
$$
### Double negation
$$
\neg(\neg p) \Longleftrightarrow V
$$
### Excluded middle
$$
p \lor \neg p \Longleftrightarrow V
$$
### Consistency
$$
p \land \neg p \Longleftrightarrow F
$$
### Absortion
$$
p \lor (p \land q) \Longleftrightarrow p
$$
$$
p \land(p \lor q) \Longleftrightarrow p 
$$
### Relaxation
$$
p \land q \implies p
$$
$$
p \implies p \lor q
$$
### Characteization of the implication
$$
(p \implies q) \Longleftrightarrow \neg p \lor q
$$
## Other tautologies
### Morgan laws
$$
\neg(p \land q) \Longleftrightarrow \neg p \lor \neg q
$$
$$
\neg(p \lor q) \Longleftrightarrow \neg p \land \neg q
$$
### Conmutativity
$$
p \lor q \Longleftrightarrow q \lor p
$$
$$
p \land q \Longleftrightarrow q \land p
$$
### Associativity
$$
p \lor (q \lor r) \Longleftrightarrow (p \lor q) \lor r
$$
$$
p \land (q \land r) \Longleftrightarrow (p \land q) \land r
$$
### Distributivity
* Of $\land$ with respect to $\land$:
$$
p \land (q \lor r) \Longleftrightarrow (p \land q) \lor (p \land r)
$$
$$
(q \lor r) \land p \Longleftrightarrow (q \land p) \lor (r \land p)
$$
* Of $\land$ with respect to $\lor$
$$
p \lor (q \land r) \Longleftrightarrow (p \lor q) \land (p \lor r)
$$
$$
(q \land r) \lor p \Longleftrightarrow (q \lor p) \land (r \lor p)
$$
### Transitivity
* Of $\implies$
$$
(p \implies q) \land (q \implies r) \implies (p \implies r)
$$
* Of $\Longleftrightarrow$
$$
(p \Longleftrightarrow q) \land (q \Longleftrightarrow r) \implies (q \Longleftrightarrow r)
$$
### Divided equivalence
$$
(p \Longleftrightarrow q) \Longleftrightarrow (p \implies q) \land (q \implies p)
$$
### Case demonstration
$$
(p_1 \lor p_2 \implies q) \Longleftrightarrow (p_1 \implies q) \land (p_2 \implies q)
$$
# Contradiction
*A contradiction is a proposition that, regardless of the truth value of the propositions that constitute it, is always false.*
## Proof techniques
### Separation rule (Modus ponens)
$$
p \land (p \implies q) \implies q
$$
### Contraposition or Counterreciprocal
$$
(p \implies q) \Longleftrightarrow (\neg q \implies \neg p)
$$
### Contradiction or Reduction to absurdity
$$
[(p \implies q) \Longleftrightarrow V] \Longleftrightarrow [p \land \neg q \implies F]
$$
