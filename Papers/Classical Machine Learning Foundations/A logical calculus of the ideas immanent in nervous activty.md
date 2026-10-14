# Metadata
* Title: A logical calculus of the ideas immanent in nervous activity
* Authors: Warren S. McCulloch & Walter Pitts
* Published: December 1943
* The bulletin of mathematical biophysics, Volume 5, pages 115-133 (1943)
# Content
## Introduction
* The nervous system is a net of neurons.
* Each [[Neuron | neuron]] have a [[Soma | soma]] and an [[Axon | axon]].
* [[Synapses]] occur between the axon of one and the soma of another.
* Each neuron has a threshold, which when the excitation exceeds it, the neuron initiates and impulse.
	* The threshold is determined by the neuron.
	* The impulse is propagated to all parts of the neuron.
* The velocity on the axon varies directly with its dyameter :
	* $< 1 ms^{-1}$ in thin axons (usually short).
	* $> 150 ms^{-1}$ in thick axons (usually long).
* [[Latent addition]] lasts around $<0.25 ms$.
* [[Synaptic delay]] $> 0.5 ms$ between receiving and sending impulses.
* At the start of the impulse, the neuron is blocked to other stimulus.
	* Then the neuron get back to its normal or subnormal activity ($subnormal \rightarrow_{\text{slowly}} normal$).
	* Frequent activity augments this subnormality.
*  The specificity depends solely upon their time and place ([[Theory of relativity]]); not on any other specificity of nervous energies.
	* Only Inhibition could break this thesis.
		* Inhibition is the prevention of the activity of neurons.
		* Was previously explained by the supposition that previous activity of neurons of one group might raise the thresholds of a second group.
		* Inhibitory synapse raises the threshold.
* Neurons can be modeled in terms of propositions:
$$
\Rightarrow \text{Network of Neurons} \Leftrightarrow \text{Propositions}
$$
* "All-or-none" law of nervous activity ([[Go big or go home]]).
* Difficulties:
	1) Facilitation and extinction: 
		Antecedent activity temporarily alters responsiveness to subsequent stimulation of one and the same part of the net
	2) Learning:
		Networks can be altered, meaning that, stimulus which would previously have been inadequete are now adequate
* Solution:
	* Use equivalent netwroks with unaltered neurons
* This is not a factual explanation - Per contra!:
	* Facilitation and exctinction are dependant upon continous change in threshold related to electrical and chemical variables
	* Learning is an enduring change that survives everything
	* Alteration actually underlying facilitation, extinction and learning in no way affect the conclusions
	* Nervous systems contains many circular paths, whose activity regenerates the excitation of any participant neuron that reference to time past becomes indefinite.
	* Recursive functions and determination of those that can be embodied in the activity of nervous networks
## The Theory: Nets Without Circles
Assumptions:
1) $\text{Neuron Activity} \leftrightarrow \text{"all-or-none" process}$
2) Fixed number of synapses must be excited within the period of latent addition in order to excite a neuron at any time. That number is always independent.
3) The only significant delay within the nervous systmen is the synaptic delay.
4) Inhibition prevent the excitation of a neuron in a given time.
5) The structure of the net is invariant to time.
### Time and Delay Operator ($S$)
* Time is handled in discrete steps representating "synaptic delays" ([[Discretization | discretization]]).
* Function S("predecessor"): The property or event $P$ holds for a number when $P$ holds of its predecessor (i.e., at time $t-1$).
$$
S(P)(t)
$$
### Cyclic Neworks
* A net will be called *cyclic* if it contains a circle, i.e. if there exists a chain $c_i,c_{i+1}, \ldots, c_n$ of neurons on it, each member of the chain synapsing upon the next with the same beginning and end ([[Where i end you begin]]).
* If a set of neurons is such that its removal from $\textrm{N}$ leaves without circles, and no smaller class of neurons has this property, the set is called a *cyclic set*, and its [[Cardinality | cardinality]] is of the order of $\textrm{N}$.
### Temporal Propositional Expression (TPE) and Temporal Propositional Function (TPF)
1) A $p¹[z_1]$ is a TPE, where $p_1$ is a *predicate-variable*.
	This establishes the simplest possible valid expression:
	* $p_1$ (Predicate-variable): Think of this as a basic statement or event which have a [[Boolean | boolean]] value.
	* $z_1$ (Free individual variable): This represents a specific moment in time.
	* Together, it justs means: "Event $p$ happens at time $z$".
2) If $S_1$ and $S_2$ are TPE containing the same free individual variable, so are $SS_1,S_1 \lor S_2,S_1.S_2$ and $S_i \sim S_2$.
	 This rule states that if yoy already have two valid expressions ($S_1$ and $S_2$) that happen at the same time, you can use logical operators to combine them into a new perfect valid TPEs.
	 Here are the four allowwed combinations:
	 * $SS_1$ (Precession/Delay): Time-delay operator $S$.
	 * $S_1 \lor S_2$ (Logical OR): This is disjunction.
	 * $S_1.S_2$ (Logical AND): This is a conjunction.
	 * $S_1. \sim S_2$ (Logical NOT): This is a negation. 
3) Nothing else is a TPE.
### Theorem 1
*Every net of order 0 can be solved in terms of temporal propositional expressions*.
* Let $c_i$ be any neuron of $\textrm{N}$ with a threshold $\beta_i > 0$, and let $c_{i1},c_{i2},\ldots,c_{ip}$ have respectively $n_{i1},n_{i2},\ldots,n_{ip}$ excitatory synapses upon it.
* Let $c_{j1},c_{j2},\ldots,c_{jq}$ have inhibitory synapses upon it.
* Let $k_i$ be the set of the subclasses of ${n_{i1},n_{i2},\ldots,n_{ip}}$ such that the sum of their members exceeds $\theta_i$.
$$
N_i(z_1) \equiv S \{ \prod_{m=1}^{q} \sim N_{jm}(z_1) . \sum_{\alpha \in \kappa_{i}} \prod_{s \in \alpha} N_{is}(z_1) \}
\tag{1}
$$
- **$N_i(z_1)$:** The proposition asserting that neuron $c_i$ fires at time $z_1$.
- **$\equiv$:** Logical equivalence ("if and only if").
- **$S\{...\}$:** Indicates that everything inside the braces must have been true exactly one synaptic delay prior.
- **The inhibitory barrier ($\prod_{m=1}^{q} \sim N_{jm}(z_1)$):** The $\prod$ symbol represents a logical conjunction (a multiple logical "AND"). The tilde $\sim$ represents negation ("NOT"). This part states that out of the $q$ inhibitory synapses connected to the neuron, _none_ must have fired. This reflects their physical assumption 4: the activity of an inhibitory synapse absolutely prevents the excitation of the neuron.
- **The excitatory impulse ($\sum_{\alpha \in \kappa_i} \prod_{s \in \alpha} N_{is}(z_1)$):** The $\sum$ symbol represents a logical disjunction (a multiple logical "OR"). Each neuron has a threshold ($\theta_i$) that the excitation must exceed. $\kappa_i$ represents the set of the subclasses of excitatory synapses whose sum exceeds that threshold $\theta_i$. This formula dictates that at least one ($\sum$) of these winning combinations must occur (where a winning combination requires _all_ synapses in that particular group to fire, represented by the inner $\prod$).
### Theorem 2
*Every TPE is realizable by  a net of order zero.*
### Theorem 3
*Let there be a complex sentence $S_1$ built up in any manner out of elementary sentences of the form $p(z_1-zz)$ where $zz$ is any numeral. by any of the propositional connections:  negation, disjunction, conjunction, implication, and equivalence. Then $S_1$ is a TPE and only if its is false when its constituent $p(z_1-zz)$ are all assumed false; i.e. replaced by false sentences; or that the last line in its truth-table contains an 'F'; or there is no term in its Hibler disjunctive normal form composed exclusively of negated terms.*
### Theorem 4
*Relative and absolute inhibition are equivalent in the extended sense.*
### Theorem 5
*Extinction is equivalent to absolute inhibition.*
### Theorem 6
*Facilitation and temporal summation may be replaced by spatial summation.*
### Theorem 7
*Alterable synapses can be replaced by circles.*
## The Theory: Nets with Circles
* Unlike zero-order nets, networks with circlers are much more difficult to model mathematically.
* Activity can reverberate araoun a cricuit indefinitely, meaning a neuron's current state migh depend on inputs that happened an indefinite amount of time in the past.
### Theorem 8
*The expression for neurons of the cyclic set of a net $\textrm{N}$ together with certain TPE expressing te actions of other neurons in terms of them, constitute a solution of $\textrm{N}.$*

Solution: A "cyclic set" of neurons ($c_1, \dots, c_p$) whose removal would eliminate all loops in the network.
* Every other neuron outside this set can be expressed using standard Temporal Propositional Expressions (TPEs).
* Synchronize the synaptic delays by finding their least common multiple ($n$).
* Because the cyclic set of size $p$ can have $2^p$ possible truth-states, it can map the transitions between these states over time.
### Theorem 9
*A series of classes $\alpha_1, \alpha_2, \ldots, \alpha_\gamma$ is a series of prehensible classes if and only if:*
$$\begin{aligned} (Em)(En)(p)n(i)(\psi) :.\; & (x)m \; \psi(x)=0 \vee \psi(x)=1 :\rightarrow: \\ & (E\beta)(Ey)m \; .\; \psi(y)=0 \; .\; \beta \epsilon \mathbb{R}[\hat{\gamma}((Ei).\gamma=\alpha_{i})] \\ & .\vee.\; (x)m \;.\; \psi(x)=0 \;.\; \beta \epsilon \overline{\mathcal{R}}[\hat{\gamma}((Ei).\gamma=\alpha_{i})] \\ :\; & (t)(\phi) : \phi \epsilon \alpha_{i} \;.\; \sigma(\phi,nt+p) .\rightarrow. \\ & (Ef) \;.\; f \epsilon \beta \lambda (w)m(x)t-1 \;.\; \phi(n(t+1)+p,nx+p,w)=f(nt+p,nx+p,w). \end{aligned}$$

"realizability": determining if a specific logical formula can actually be physically wired into a nervous net.
- Fundamental rule is that no nervous net can account for _future_ peripheral inputs.
- "prehensible classes" and generate Boolean rings to define the boundaries of what can be built.
- Applying this theorem practically requires exploring up to $2^{2^n}$ function classes, making it highly complex.
### Theorem 10
*Let us define a set K of S by the following recursion: 
	(1) any TPE and any TPE whose arguments have been replaced by members of K belong to K
	(2) if ${Pr}_1(z_1)$ of K, then $(z_2)z_1.{Pr}_1(z_2), ({Ez}_2)z_1.{Pr}_1(z_2),$ and $C{mn}(z_1).s$ belong to it, where $C_{mn}$ denotes the property of being congruent to $m$ modulo $n$, $m<n$
	(3) The set K has no further members

Provide a more practical tool for neurophysiologists and mathematicians, te authors offer a simplified rule.
* Guarantees that you can physically build a network for any mathematical expresson that combines basics TPEs with standar periodic functions.
* Specifically, this involves properties congruent to $m$ modulo $n$ ($C_{mn}$), effectively allowing the network to use simple timing loops as biological clocks.
### Biological Turing Machines
* A nueronal net equipped with a tape, scanners, and efferents can compute exactly the same numbers as a [[Turing machine]].
* This offers a profound phychological justification for Churchs's and Turing's definitions of computability: if a biological organism can compute a number, so can these theoretical machines.
## Consequences
* Causality in this theory is highly irreciprocal.
* Specifying the current state of afferent stimulation and the activity of all neurons completly determines the succeding state.
* However, disjunctive relations (logical ORs) prevent the complete determination of the preceding state. 
* Regenerative activity in cruclar networks makes refrence to past time indefinite as to time.
* Every idea and sensation is realized by network activity, but this activity never fully determines the actual afferents (the external inputs).
* If the nervous net is altered (e.g., tinnitus, hallucinations, delusions), our reference to external facts becomes defective.
* If our nets are undefined, our facts are undefined; determining the exact net removes the unknowability of the "thing in itself".
* Psychology:
	* The ultimate psychic unit or "psychon" is equivalent to the activity of a single neuron.
	* Because thsi activity is inherently propositional, all psychi events have an intentional or "semiotic" character.
	* The fundamental relations of psychology, wheter introspective, behavioristic, or physiological, are governed by two-valued logic.
* Psychiatry and Causality:
	* For prognosis, a patient's history is theoretically never necessary, because the present state of the net dictates the future.
	* Overt behavior does not uniquely identify the underlying neural network (multiple imaginalbe networks could produce the same behavior, though only one actually exists in the brain).
	* "Mind" is demystified; diseased mentality can be rigorously understood through scientific neurophysiology rather than as a "ghostly" phenomenon.
* Neurology and Mathematical Biophysics:
	* The theory sharpens the distinction between networks that are necessary versus those that are merely *sufficient* for given activities, clarifying how disturbed physical structuers relate to disturbed functions.
	* It provides mathematical biophysics with a rigorous symbolic tool to treat known networks and easily construct hypothetical ones.
* *The future is predictable, the past is erased, memory is blurry* ([[1984]]).
	* If you know the exact state of every neuron rigth now ($t$), you can mathematically predict the very next state.
	* Because neural networks use "OR" logic, you cannont reverse-engineer the past. If a neuron $C$ is firing, you don't know if is $A$ caused it, $B$ caused it, or both.
	* Because the circular feedback loops (network with circles), a signal migth have been bouncing around your brain for a millisecond or a decade. Therefore, our physical brains make our knowledge of the past fundamentally *indefinite*.
* *The illusion of objective reality* ([[The Matrix]]).
	* Every thought, sensation, and idea you have is just a physicial realiozation of activity within this logical net.
		* You never actually experience the "real world"; you only experience your brain's internal mathematical computation of it.
		* If your biological network gets altered (through disease, drugs or injury), your "facts" about reality literally changes, resulting in hallucinations or delusions. Reality is only stable as the biological wiring processing it.
* *Solving Kant's "[[Thing-in-Itself]]"*  
	* The "unknowable" nature of the universe is simply byproduct of the biological limits of our nerual wiring.
	* If we can completly define the mathematical structure of the neural net, the mistery vanishes. The limits of human knowledge are just the limits of a biological logic gate.
* The "Psychon" and the Death of the Soul
	* Psychon is similar to atom, the ultimate, smallest unit of psychic activity.
	* Human consciousnes is stripped of any mystical or spiritual elements. The mind is srtrictly a machine governed by two-valued logic.