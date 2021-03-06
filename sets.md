## Set axioms

In mathematics we study objects. A **set**, informally an unordered collection of objects, is a certain kind of object. If an object $x$ belongs to a set $A$, we denote this fact by $x \in A$, and we write $x \notin A$ if $x$ does not belong to $A$. If $A$ is not a set, then it is meaningless to ask whether $x \in A$ or $x \notin A$.

Sets satisfy the following axioms:

 1. Every set $A$ is an object (i.e. a set could be an element of another set).
 2. There exists a set, denoted $\emptyset$, called the **empty set**, such that for every object $x$, $x \notin \emptyset$.
 3a. For every object $a$, there is a set $A$ such that $a \in A$ and for all $x \in A$, $x = a$. Such sets are called **singleton** sets.
 3b. For any objects $a$ and $b$, there is a set $C$ such that $a \in C$, $b \in C$, and if $x \in C$, then ($x = a$ or $x = b$).
 4. (Axiom of pairwise union) For any two sets $A$ and $B$, there is a set $A \cup B$ called the **union** of $A$ and $B$ such that $x \in A \cup B$ iff ($x \in A$ or $x \in B$).
 5. (Axiom of specification) For any set $A$ and property $P$ defined over all $x \in A$, there is a set $B$ whose elements are exactly the $x \in A$ such that $P(x)$ is true. This is often written $B := \{x \in A : P(x) \}$.
 6. (Axiom of replacement) For any set $A$ and any property $P$ such that for any $x \in A$, there is at most one object $y$ for which $P(x, y)$ is true. Then there is a set $B$ that contains exactly the $y$ such that $P(x, y)$ is true for some $x \in A$.
 7. (Axiom of infinity) There exists a set $\mathbb{N}$ that satisfies the Peano axioms (see the page on the natural numbers).
 8. (Power set axiom) For any sets $X$ and $Y$, there is a set $Y^X$ of all functions (to be defined below) from $X$ to $Y$.
 9. (Axiom of union) If $A$ is a set whose elements are all sets, then there is a set $\bigcup A$ whose elements are exactly those elements in one of the sets in $A$. ($x \in \bigcup A$ iff $\exists S \in A$ such that $x \in S$)

## Definition of set equality

For sets $A$ and $B$, they are **equal**, written $A = B$, if $\forall x \in A$, $x \in B$ and $\forall x \in B$, $x \in A$. That is, if the sets contain exactly the same objects.


## Uniqueness of empty set
If $A$ and $B$ are both empty sets, then $A = B$.

 1. It suffices to prove that $x \notin B$ implies $x \notin A$.

    *Proof:* Proof by contrapositive. Symmetry of set equality establishes the other direction of implication.

 2. Q.E.D.

    *Proof:* For every object $x$, by definition of $B$, $x \notin B$ and $x \notin A$.


## Uniqueness of singleton sets
If $x$ is an object and $X$ is the singleton set containing $x$ that exists by Axiom 3a, then if $Y$ is another singleton set for $x$, we must have $X = Y$.

*Proof:* $x \in X$ and $x \in Y$, and neither $X$ nor $Y$ contain any other objects. So they must be equal.


## Single choice
If $A$ is a non-empty set, then there is some object $x \in A$.

*Proof:* If no object $x$ is such that $x \in A$, then $A$ is the empty set, which contradicts the assumption that it is non-empty.


## Set equality is an equivalence relation

### Reflexivity
For every set $A$, $A = A$.

*Proof:* For all $x$, ($x \in A$) clearly implies ($x \in A$).


### Symmetricity
For all sets $A$ and $B$, $A = B$ implies $B = A$

 1. ($\forall x$, $x \in A$ iff $x \in B$) implies ($\forall x$, $x \in B$ iff $x \in A$).

    *Proof:* By basic logic, bidirectional implication is symmetric.

 2. Q.E.D.

    *Proof:* ($\forall x$, $x \in A$ iff $x \in B$) is just a restatement of the definition of $A = B$.

### Transitivity
For all sets $A$, $B$ and $C$, ($A = B$ and $B = C$) imply $A = C$.

 1. It suffices to assume

      1. $A = B$
      2. $B = C$

    and prove $A = C$.

 2. $x \in A$ implies $x \in C$

    *Proof:* If $x \in A$, then $x \in B$ by (1.1). But $x \in B$ implies $x \in C$ by (1.2).

 3. $x \in C$ implies $x \in A$.

    *Proof:* By applying symmetricity to $A = B$ and $B = C$, we use (2).

 4. Q.E.D.

    *Proof:* By the definition of $A = C$.


## Definition of subset, proper subset
If $A$ and $B$ are sets, then $A$ is a **subset** of $B$, denoted $A \subseteq B$, if for all objects $x$, $x \in A$ implies $x \in B$.

$A$ is a **proper subset** of $B$, denoted $A \subset B$, if $A \subseteq B$ and $A \neq B$.


## A lemma about subsets
For any sets $A$ and $B$, 

 1. $A \subseteq A \cup B$
 2. $A \cap B \subseteq A$

*Proof:* If $x \in A, then clearly ($x \in A$ or $x \in B$), establishing (1). If ($x \in A$ and $x \in B$), then $x \in A$, establishing (2)


## Equivalent definitions for subsets
For any sets $A$ and $B$, $A \subseteq B$ iff $A \cup B = B$ iff $A \cap B = A$

 1. $A \subseteq B$ implies $A \cup B = B$

    *Proof:* From the previous lemma we have B \subseteq A \cup B$. If $x \in A \cup B$, $x$ must also be in $B$ since $x \in A$ implies $x \in B$ via the hypothesis.

 2. $A \cup B = B$ implies $A \cap B = A$

    *Proof:* The previous lemma proves $A \cap B \subseteq A$. Conversely, If $x \in $A$, $x$ must be in $B$ as well since by hypothesis $A \cup B = B$, so if $x \notin B$ it's not in $A \cup B$, implying it's not in $A$ either. This proves $x \in A \cap B$.

 3. $A \cap B = A$ implies $A \subseteq B$

    *Proof:* If there were an element of $x \in A$ that wasn't in $B$, then $A$ would not be a subset of $A \cap B$, a contradiction.


## Set inclusion is a partial order
### Reflexivity
For any set $A$, $A \subseteq A$.

*Proof:* $x \in A$ implies $x \in A$.

### Antisymmetricity
For any sets $A$, $B$, $A \subseteq B$ and $B \subseteq A$, then $A = B$.

*Proof:* This is essentially a restatement of the definition of set equality.

### Transitivity
For any sets $A$, $B$, $C$, if $A \subseteq B$ and $B \subseteq C$ then $A \subseteq C$.

*Proof:* $x \in A$ implies $x \in B$ (since $A \subseteq B$), and $x \in B$ implies $x \in C$ (since $B \subseteq C$).

## Strict set inclusion is transitive
If $A, B, C$ are sets such that $A \subset B$ and $B \subset C$, then $A \subset C$.

*Proof:* From the hypothesis and transitivity of set inclusion, we know $A \subseteq C$. If $A = C$, then $C \subseteq A$ in particular, meaning $C \subseteq B$ by transitivity. But we already had $B \subseteq C$, so $B = C$, a contradiction.


## Definition of set intersection
An operation $\cap$ on sets is defined, via the axiom of specification, by $X \cap Y := \{x \in X : x \in Y\}$

## Definition of disjoint sets
Sets $A$ and $B$ are **disjoint** if $A \cap B = \emptyset$

## Definition of difference sets
If $X$ and $Y$ are sets, the set $X\Y$ is defined by $X\Y := \{x \in X : x \notin Y\}$. This is also denoted $X - Y$.


## Another lemma about subsets
For any sets $A, B, C$, 

 - if $C \subseteq A$ and $C \subseteq B$, then $C \subseteq A \cap B$

 - if $A \subseteq C$ and $B \subseteq C$, then $A \cup B \subseteq C$.


 1. if $C \subseteq A$ and $C \subseteq B$, then $C \subseteq A \cap B$

    *Proof:* Every element of $C$ is an element of both $A$ and $B$, so it must be an element of $A \cap B$ as well.

 2. if $A \subseteq C$ and $B \subseteq C$, then $A \cup B \subseteq C$.

    *Proof:* If every element of $A$ is an element of $C$ and every element of $B$ is an element of $C$, then every element of $A \cup B$ is an element of $C$.


## Absorption laws
If $A$ and $B$ are sets, then $A \cap (A \cup B) = A = A \cup (A \cap B)$

 1. $A \cap (A \cup B) \subseteq A$ and $A \subseteq A \cup (A \cap B)$

   *Proof:* "A lemma about subsets"

 2. $A \subseteq A \cap (A \cup B)$

    *Proof:* If $x \in A$, then ($x \in A$ and $x \in B$).

 3. $(A \cap B) \subseteq A \cap (A \cup B)$

    *Proof:* If ($x \in A$ and $x in B$), then ($x \in A$ and $x \in A \cup B$).

 4. $A \cup (A \cap B) \subseteq A \cap (A \cup B)$

    *Proof:* (2) and (3) and "Another lemma about subsets" imply the statement.


## Partition of the union
For any sets $A$ and $B$, $A - B$, $A \cap B$ and $B - A$ are pairwise disjoint and $(A - B) \cup (A \cap B) \cup (B - A) = A \cup B$

*Proof:* If $x \in A \cap B$, $x$ could not be in either $A - B$ or $B - A$ by definition (since $x$ is in both $A$ and $B$). If $x \in A - B$, $x$ is not in $B - A$ since $x \notin B$. The rest follow from contrapositives of the above.

## Sets form a boolean algebra
For any set $X$, if $A, B, C$ are any subsets of $X$, then the following properties hold:

 a. (Minimal element) $\emptyset \cup A = A$ and $\emptyset \cap A = \emptyset$

 b. (Maximal element) $X \cup A = X$ and $X \cap A = A$.

 c. (Idempotent) $A \cap A = A$, $A \cup A = A$

 d. (Commutativity) $A \cap B = B \cap A$, $A \cup B = B \cup A$

 e. (Associativity) $A \cap (B \cap C) = (A \cap B) \cap c$ and $A \cup (B \cup C) = (A \cup B) \cup c$

 f. (Distributivity) $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$ and $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$

 g. (Partition) $A \cup (X - A) = X$ and $A \cap (X - A) = \emptyset$

 h. (DeMorgan laws) $X - A \cup B$ = (X - A) \cap (X - B)$ and $X - A \cap B = (X - A) \cup (X - B)$

*Proof (a):*

 1. $\emptyset \cup A = A$

    *Proof:* $x \in \emptyset \cup A$ means $x \in emptyset$ or $x \in A$, which implies $x \in A$ since no object is an element of $\emptyset$.  Clearly $x \in A$ implies $x \in \emptyset \cup A$.

 2. $\emptyset \cap A = \emptyset$

    *Proof:* $x \in \emptyset \cap A means $x \in \emptyset$ and $x \in A$. The former is false for every object, so $\emptyset \cap A$ contains no objects and must be the empty set.

*Proof (b):*

 1. $X \cup A = X$

    *Proof:* It is immediate that $X \subseteq X \cup A$. Conversely, if $x \in X \cup A$, then $x \in X$ or $x \in A$. But $A$ is a subset of $X$, so $x \in A$ implies $x \in X$.

 2. $X \cap A = A$

    *Proof:* $X \cap A \subseteq A$. If $x \in A$

*Proof (c):* Follows from the idempotence of logical "and" and logical "or".
*Proof (d):* Follows from the commutativity of logical "and" and logical "or".
*Proof (e):* Follows from the associativity of logical "and" and logical "or".
*Proof (f):* Follows from the distributivity of logical "and" and logical "or".

*Proof (g):*

 1. $A \cup (X - A) = X$

    *Proof:* Both $A$ and $X - A$ are subsets of $X$, so $A \cup (X - A) \subseteq X$. Conversely, if $x \in X$, it's either in $A$ or in $X - A$.

 2. $A \cap (X - A) = \emptyset$

    *Proof:* We need only prove $A \cap (X - A) \subseteq \emptyset$, which is true since no object is both in $A$ and not in $A$.


*Proof (h):*
 1. $X - A \cup B$ = (X - A) \cap (X - B)$ 

    *Proof:* For all $x \in X$, $x$ is not in $A \cup B$ implies it is neither in $A$ nor in $B$. Conversely, if $x$ is not in $A$ and not in $B$, it must not be in $A \cup B$ either.

 2. $X - A \cap B = (X - A) \cup (X - B)$

    *Proof:* If $x \in X$ isn't in $A \cap B$, it is either not in $A$ or not in $B$. If $x$ is in $A \cap B$, then $x$ is both in $A$ and in $B$.


## Definition of functions
For any sets $X$ and $Y$, let $P$ be a property such that for every $x \in X$ there is exactly one $y \in Y$ such that $P(x,y)$ is true. Then a **function** $f: X \to Y$ is defined to be an object which gives for every $x \in X$, the unique element $f(x) \in Y$ such that $P(x, f(x))$ is true.


## Definition of function equality
If $f$ and $g$ are two functions $X \to Y$ for some sets $X$ and $Y$, then $f$ and $g$ are **equal** ($f = g$) iff for every $x \in X$, $f(x) = g(x)$.


## Function equality is an equivalence relation
### Reflexivity
For all sets $X$ and $Y$ and every function $f: X \to Y$, $f = f$.

### Symmetricity
For all sets $X$ and $Y$ and all functions $f: X \to Y$, and $g: X \to Y$, if $f = g$.

### Transitivity
For all sets $X, Y, Z$ and all functions $f: X \to Y$, $g: X \to Y$, $h: X \to Y$, if $f = g$ and $g = h$, then $f = h$.

*Proof:* All of the above follow from the equality relation on objects that can be elements of sets. Tao really doesn't seem to define or axiomatize this, but I have to assume it is there, otherwise this doesn't make any sense.

## Definition of function composition
If $f: X \to Y$ and $g: Y \to Z$ for sets $X, Y, Z$, then the **composition** of $f$ and $g$ is defined to be a function $g \circ f: X \to Z$ such that for all $x \in X$, $(g \circ f)(x) := g(f(x))$.

The range of $f$ must match the domain of $g$ for $g \circ f$ to be defined.


## Composition is associative
For functions $f: X \to Y$, $g: Y \to Z$, $h: Z \to W$, we have

$$h \circ (g \circ f) = (h \circ g) \circ f$$

*Proof:* $(h \circ (g \circ f))(x) = h((g \circ f)(x)) = h(g(f(x)) = (h \circ g)(f(x)) = ((h \circ g) \circ f)(x)$

## Definition of injective functions
A function $f: X \to Y$ is **injective** iff for any $a, b \in X$, $f(a) = f(b)$ implies $a = b$

## Definition of surjective functions
A function $f: X \to Y$ is **surjective** iff for any $y \in Y$ there is an $x \in X$ such that $f(x) = y$.

## Definition of bijective functions
A function $f: X \to Y$ is **bijective** iff it is both injective and surjective.

Equivalently, $f$ is bijective iff for every $y \in Y$ there is exactly one $x \in X$ such that $f(x) = y$.


## Bijections have inverses
If $f: X \to Y$ is a bijection, then there is a unique function $f^{-1}: Y \to X$ such that $(f \circ f^{-1})(y) = y$ and $(f^{-1} \circ f)(x) = x$ for all $x \in X$ and $y \in Y$.

 1. If such a function exists, it is unique.

    *Proof:* Assume $g$ and $h$ are inverses for $f$. Then for all $y \in Y$, $g(y) = g(f(h(y))) = (g \circ f)(h(y)) = h(y)$.

 2. Such a function exists.

    *Proof:* We define the property $P(y, x)$ to be true exactly when $y \in Y$ and $x \in X$ is the unique element of $X$ such that $f(x) = y$, which is possible by the definition of bijective functions. Then $f^{-1}: Y \to X$ is defined to be the function associated with $P$.

 3. Q.E.D.

    *Proof:* (2) and (1) establish existence and uniqueness

### Corollary
$f^{-1}$'s inverse is $f$

## Composition of injective/surjective functions is injective/surjective
If $f: X \to Y$ and $g: Y \to Z$ are functions then

 - $f$ and $g$ injective implies $g \circ f$ injective
 - $f$ and $g$ surjective implies $g \circ f$ surjective

 1. $f$ and $g$ injective implies $g \circ f$ injective

    *Proof:* $g(f(a)) = g(f(b))$ implies $f(a) = f(b)$ by $g$'s injectivity, which implies $a = b$ by $f$'s injectivity.

 2. $f$ and $g$ surjective implies $g \circ f$ surjective

    *Proof:* Every $z \in Z$ has a $y$ such that $g(y) = z$ by $g$'s surjectivity. There is an $x$ such that $f(x) = y$ by $f$'s surjectivity. so $z = g(f(x))$.


### Corollary
If $f: X \to Y$ and $g: Y \to Z$ are bijective, then $g \circ f$ is too and $(g \circ f)^{-1} = f^{-1} \circ g^{-1}$

*Proof:* It follows that $g \circ f$ is bijective since bijections are both injective and surjective. By associativity, $f^{-1} \circ g^{-1}$ is the inverse.


## Cancellation laws for function composition
If $f, \tilde{f} : X \to Y$ and $g, \tilde{g} : Y \to Z$, then

 - if $g$ injective, then $g \circ f = g \circ \tilde{f}$ implies $f = \tilde{f}$
 - if $f$ surjective, then $g \circ f = \tilde{g} \circ f$ implies $g = \tilde{g}$

 1. if $g$ injective, then $g \circ f = g \circ \tilde{f}$ implies $f = \tilde{f}$

    *Proof:* By assumption, For all $x \in X$, $g(f(x)) = g(\tilde{f}(x))$, so $f(x) = \tilde{f}(x)$ by $g$'s injectivity, which proves $f = \tilde{f}$.


 2. if $f$ surjective, then $g \circ f = \tilde{g} \circ f$ implies $g = \tilde{g}$

    *Proof:* For all $y \in Y$, there is an $x \in X$ such that $f(x) = y$, by $f$'s surjectivity, so $g(y) = $g(f(x)) = \tilde{g}(f(x)) = \tilde{g}(y)$.


## Definition of inclusion and identity maps
If $X \subseteq Y$, the **inclusion** $\iota_{X \to Y}$ is defined by $\iota_{X \to Y}(x) = x$ for all $x \in X$. It is an **identity** map when $X = Y$.

## Hashtag inclusionfacts
If $A$, $B$ and $C$ are sets, then:

 - $A \subseteq B \subseteq C$ implies that $\iota_{B \to C} \circ \iota_{A \to B} = \iota_{A \to C}$
 - if $f: A \to B$ then $f = f \circ \iota_{A \to A} = \iota_{B \to B} \circ f$
 - if $f: A \to B$ is bijective, then $f^{-1} \circ f = \iota_{A \to A}$ and $f \circ f^{-1} = \iota_{B \to B}$
 - If $A$ and $B$ are disjoint and $f: A \to C$ and $g: B \to C$ are functions then there is a unique $h: A \cup B \to C$ such that $h \circ \iota_{A \to A \cup B} = f$ and $h \circ \iota_{B \to A \cup B} = g$


 1. $A \subseteq B \subseteq C$ implies that $\iota_{B \to C} \circ \iota_{A \to B} = \iota_{A \to C}$

    *Proof:* First note that $\iota_{B \to C} \circ \iota_{A \to B} : A \to C$. For all $a \in A$, $(\iota_{B \to C} \circ \iota_{A \to B})(a) = \iota_{B \to C} (\iota_{A \to B}(a)) = a = \iota_{A \to C}(a)$.

 2. If $f: A \to B$ then $f = f \circ \iota_{A \to A} = \iota_{B \to B} \circ f$

    *Proof:* For all $a \in A$, $f(a) = f(\iota_{A \to A}(a)) = (f \circ \iota_{A \to A})(a)$ and $f(a) = \iota_{B \to B}(f(a)) = (\iota_{B \to B} \circ f)(a)$.

 3. If $f: A \to B$ is bijective, then $f^{-1} \circ f = \iota_{A \to A}$ and $f \circ f^{-1} = \iota_{B \to B}$

    *Proof:* Since the domains and ranges agree, this follows from "Bijections have inverses".

 4. If $A$ and $B$ are disjoint and $f: A \to C$ and $g: B \to C$ are functions then there is a unique $h: A \cup B \to C$ such that $h \circ \iota_{A \to A \cup B} = f$ and $h \circ \iota_{B \to A \cup B} = g$

    *Proof:* We define a property $P(x,y)$ to be true exactly when $x \in A$ and $y = f(x)$ or $x \in B$ and $y = g(x)$. This property is suitable for defining a function since for all $x \in A \cup B$, there is exactly one $y$ (either $f(x)$ or $g(x)$, depending on whether $a \in A$ or $x \in B$) such that $P(x, y)$ is true. The resulting function $h$ has, for all $x \in A$,  $h(\iota_{A \to A \cup B}(x)) = h(x) = f(x)$, where the latter holds by definition of $h$ since $x \in A$. Also, for all $y \in B$, $h(\iota_{B \to A \cup B}(y)) = h(y) = g(y)$, where the latter holds once again since $y \in B$.


## Definition of function images
If $X$ and $Y$ are sets and $f: X \to Y$ is a function, then for any set $S \subseteq X$, we define a new set 

$$f(S) := \{y \in Y : \exists x \in S, f(x) = y\}$$

This set is well-defined via the axiom of replacement by using a property $P(x,y)$ which is only true when $x \in S$ and $y = f(x)$.

$f(S) \subseteq Y$, by definition, and is called the **image** of $f$ under $S$.

## Definition of function pre-image
If $X$ and $Y$ are sets and $f: X \to Y$ is a function, then for any $T \subseteq Y$, we define a new set

$$f^{pre}(T) := \{ x \in X : $f(x) \in T$ \}$$

This set is well-defined, via the axiom of specification via a property $P(x)$ which is only true when $x \in X$ and $f(x) \in T$.

$f^{pre}(T)$ is called the pre-image of $T$.


## Power sets exist.
If $X$ is a set, then the set $\{Y: Y \subseteq X\}$ exists. This set is called the **power set**, and is denoted $2^X$.

*Proof:* The set $\{0, 1\}^X$ of all functions $X \to \{0, 1\}$, exists by the power set axiom. TODO


## Definition of an index set
A set $I$ is called an **index set** if for every $x \in I$ there is some unique set $S_x$. 

### Union of an indexed family
For any such index set, there is a set $\mathcal{A}$ of all the indexed sets: use the axiom of replacement on set $I$ along with a property $P(x,A)$ which is true exactly when $x \in I$ and $A$ is the unique set $S_x$ indexed by $x$. This new set is the $\mathcal{A}$ previously mentioned. We can now use the axiom of union to obtain a set that contains exactly the elements of the sets that are indexed by $I$.

### Intersection of a non-empty indexed family
If $I$ is non-empty, some $x \in I$ exists. Via the axiom of specification we construct the set

$$S_x = \{a \in A_x : \forall y \in I, a \in A_y\}$$

We define the **intersection** of the family of sets indexed by $I$ to be $S_x$.

Note that if $z \in S_x$, then $z \in A_y$ for all $y \in I$. Conversely, if $z \in A_y$ for all $y \in I$, then it's in $A_x$ in particular, and so in $S_x$. This establishes that for any $x, y \in I$, $S_x = \{a \in \bigcup_{\alpha in I} A_{\alpha} : \forall \alpha \in I a \in A_{\alpha} \} = S_y$. In other words, the definition of intersection is independent of the choice of $x \in I$.


## Pre-image and image
For any function $f: X \to Y$ and any set $S \subseteq X$, $f^{pre}(f(S)) \subseteq S$. For any set $T \subseteq Y$, $f(f^{pre}(T)) = T$.

*Proof (sketch):* In the former case, more elements than what's in $S$ may map into the elements that $S$ maps into, whereas the elements in $Y$ that are mapped to by elements that map to $T$ is exactly $T$. TODO: clean up.


## Definition of ordered pairs
If $a$ and $b$ are objects, we define a set $\{\{a\}, \{a, b\}\}$ by 3 invocations of the pair axiom (3b). Notate this set $(a, b)$. Then for two more objects $c$ and $d$, we can prove:

$$(a,b) = (x, y) iff (a = x \and b = y)$$

*Proof:* If $a = b$, then $(a, b) = \{\{a\}\}$, so if $x \neq y$ then $(a, b) \neq (x ,y)$ (the latter has two elements). So we have $x = y$. By set equality, $\{a\} = \{x\}$, implying $a = x$. This implies $b = y$ as well. Conversely, if $a = x$ and $b = y$, then $(a, b) = \{\{a\}\} = \{\{x\}\} = (x, y)$.

The above can be said for $x = y$.

We now assume $a \neq b$ and $x \neq y$. If $(a, b) = \{\{a\}, \{a, b\}\}$ = \{\{x\}, \{x, y\}\} = (x, y)$, then $\{a\} \neq \{x, y\}$ and $\{x\} \neq \{a, b\}$ since the number of elements differ. So we must have $a = x$. This implies $b = y$ as well. Conversely if $a = x$ and $b = y$, then the two sets are clearly equal. $\Box$

The set defined above is called an **ordered pair**.


## Definition of Cartesian product
For sets $X$ and $Y$, the set $X \times Y := \{(x, y) : x \in X, y \in Y\}$ exists.

*Proof:* I haven't carefully thought this out, but I believe you can use, for every $y \in Y$, the axiom of replacement on set $X$ to construct a set $S_y = \{(x,y) : x \in X\}$. This is an indexed family of sets, so you can create a set containing all of these sets. Then uset he axiom of union to bring them all into a single set.

To be honest, while it's nice to know that you can build these things out of sets, including $n$-tuples and $n$-fold Cartesian products, I am much more willing to just lay down an axiom that says that they exist exactly like we expect they do.


## Definition of $n$-tuples and $n$-fold Cartesian products
This is a new axiom or whatever. For any sets $A_1, \ldots, A_n$, $n$-tuples $(x_1, \ldots, x_n)$ with $x_i \in A_i$ exist, and you can use these to define $n$-fold cartesian products notated

$$\Prod_{i = 1}^n A_i$$

$n$-tuple equality behaves like you'd expect it to: $(x_1, \ldots, x_n) = (y_1, \ldots, y_m)$ iff $n = m$ and $x_i = y_i$ for all $i$.


## Finite choice
Let $n \in \mathbb{N}^+$. For each $i$ with $1 \leq i \leq n$, let $X_i$ be a non-empty set. Then there is a tuple $(x_i)_{1 \leq i \leq n}$ such that $x_i \in X_i$ for all $i$.

*Proof:* Blugh, too burned out to do this. TODO
