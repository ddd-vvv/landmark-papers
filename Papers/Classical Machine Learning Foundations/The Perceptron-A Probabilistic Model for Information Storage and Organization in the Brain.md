# Metadata
* Title: The Perceptron: A Probabilistic Model for Information Storage and Organization in the Brain.
* Author: Roseblatt, F.
* Published: 1958.
* Psichological Review, 65(6), 386-408.
# Content
# Three main questions
* For understanding the capability of higher organism for perceptual recognition, generalization, recall, and thinking:
	1) How is information about the physical world sensed, or detected, by the biological system? ([[Sensing | sensing]])
	2) In what form is information stored, or remembered? ([[Memory | memory]]).
	3) How does information contained in [[Storage | storage]], or in [[Memory | memory]], influence recognition and behavior?
* With regard to the second question:
	1) Storage of sensory information is in the form of coded representations or images, with one-to-one mapping between the sensory stimulus and the stored pattern.
	2) Nothing is recorded, the [[Central Nervous System | central nervous system]] simply acts as an intricate switching network, where retention takes the form of new connections, or pathways, between centers of activity.
		* The response represents the "idea".
		* There is never any simple mapping of the stimulus into memory $\rightarrow$ NO RECONSTRUCTION IS POSSIBLE.
		* The information that is retained is stored as a *preference for a particular response*.
* With regard to the third question:
	1) Coded Memory: The recognition of any stimulus involves the matching or systematic comparison of the contents of storage with incoming sensory patterns.
	2) Empericist Traidition: Stored information takes the form of new connections; then a new stimuli will make use of these new connections, automatically activating the appropiate response without requiring any separate process.
* **The theory of the paper takes the empiricist approach (connectionist)**.
## Perceptron
* Hypothetical nervous system or machine.
* Designed to illustrate some of the fundamental properties of intelligent systems in general.
* Outside of the biology paradigm itself.
* Still represents and analogy to biological systems.
* Based on the similarity between a neuron and the simple on-off ([[Boolean]]) units of which [[Computer| computers]] are constructed.
* Partially based on [[A logical calculus of the ideas immanent in nervous activty]], between others.
* The author formulates the theory in terms of [[Probability | probability]] theory rather than symbolic logic.
* It says that the other articles were concerned with the question of how a theoreticall system work rather than how the brain works.
	* Older models failed in important aspects:
		* Absence of equipotentiality.
		* Lack of neuroeconomy.
		* Excessive specificity of connections.
		* Synchronization requirements.
		* Unrealistic specificity of stimuli sufficient for cell firing.
		* Postulation of variables or functional feaetures with no kwnown neurological correlates.
	* Those models propose that, once it has been shown how a physical system works, then you could understand everything.
* The author takes the position that those models, even with the refinements that they need, they could never account for biological intelligence.
* The author proposes that the [[Theory of statistical separability | theory of statistical separability]] appears to offer a solution in principle to all of these difficulties.
* Assumptions of the theory:
	1) The physical connections of the nervous system which are involved in learning and recognition are not indetical from one organims to another. At birth, the construction of the most important networks is largely random, subjhet to a minimum number of genetic constraints ([[Genetic lottery]]).
	2) The original system of connected cells is capable of a certain amount of  [[Neuroplasticity | neruoplasticity]]; after a preiod of neural activity, the probability that a stimulus applied to one set of cells will cause a response in some other set is likely to change, due to some relatively long-lasting changes in the neurons themselves.
	3) Through exposure to a large sample of stimuli, those which are most "similar" (in some snese which must be defined in terms of the particular physical system) will tend to form pathways to the same sets of responding cells. Those which are markedly "dissimilar" will tend to develop connections to different sets of responding cells ([[Mastery]]).
	4) The application of postive and/or negative reinforcement (or stimuli which serve this function) may facilitate or hinder whatever formation of connections is currently in progress ([[Perfect practices makes perfect learning]]).
	5) *Similarity*, in such a system, is represented at some level of the nervous system by a tendency of similar stimuli to activate the same sets of cells. Similarity is not necessary attribute of particular formal or geometrical classes of stimuli, but depends on the physical organization of the perceiveing system, and organization which evolves through interaction with a given enviroment. The structure of the system, as well as the ecology of the stimulus-enviroment, will affect, and will largely determine, the clases of "things" into which the perceptual world is divided ([[Reinforcement learning]]).
## The Organization of a Perceptron
1) 
	* Stimuli impinge on a retina of sensory units (S-points), which are assumed to respond on an all-or-nothing basis ([[Go big or go home]]), in some models, or with a pulse amplitude or frequency proportional to the stimulus intensity, in other models. 
	* In the models considered here, an all-or-nothing response will be assumed ([[Go big or go home]]).
2) 
	* Impulses are transmitted to a set of association cells (A-units) in a "projection area" ($A_I$). This projection area may be ommited in some models, where the retina is connected directly to the association area ($A_{II}$).
	* The set if S-points transmitting impulses to a particular A-unit will be called *origin points*.
	* These *origin points* may be either *excitatory* or *inhibitory* in their effect on the A-unit.
	* If the algebraic sum of that impulses is $>= \theta$ of the A-unit, then the A-unit fires again.
	* The *origin points* of the A-units in the projection area tend to be clustered or focalized, about some central point, corresponding to each A-unit.
	* The number of *origin points* falls off exponentially as the retinal distance from the central point of the A-unit increases.
3) 
	* Between the projection area and the association area ($A_{II}$), connections are assumed to be random. 
	* Each A-unit in the $A_{II}$ set recieves some number of fibers from origin points in the $A_I$ set, but these origin points are scattered at random trhoughout the projection area.
	* Apart from their connection distribution $A_I \equiv A_{II}$.
4) 
	* The "responses" $R_1, R_2, \ldots, R_n$ are cells (or sets of cells) which respond in much the same fashion as the A-units.
	* Each response has a typically large number of origin points located at random in the $A_{II}$ set.
	* The set of A-units transmitting impulses to a particular response will be called the source-set for that response.
	* Feedback connections (Similar to the [[Endocrine system]]):
		1. Excitatory feedback connections to the cells in its own soruce-set.
		2. Inhibitory feedback connections to the complement of its own source-set.
### Comparison of logical characteristics of $\alpha$, $\beta$ and $\gamma$ systems
|                                                         | $\alpha$ (Uncompensated Gain System)                                                     | $\beta$ (Constant Feed System) | $\gamma$ (Parasitic Gain System)     |
| ------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------ | ------------------------------------ |
| Total value-gain of source set per reinforcement        | $$N_{a_r}$$                                                                              | $$K$$                          | $$0$$                                |
| $\Delta V$ for A-units active for 1 unit of time        | $$+1$$                                                                                   | $$K/N_{a_r}$$                  | $$+1$$                               |
| $\Delta V$ for inactive A-units outside of dominant set | $$0$$                                                                                    | $$K/N_{A_r}$$                  | $$0$$                                |
| $\Delta V$ for inactive A-units of dominant set         | $$0$$                                                                                    | $$0$$                          | $$\frac{-N_{a_r}}{N_{A_r}-N_{a_r}}$$ |
| Mean value of A-system                                  | Increases with number of reinforcements                                                  | Increases with time            | Constant                             |
| Difference between means values of source-sets          | Proportional to differences of reinforcement frequency ($n_{\theta_r1} - n_{\theta_r2}$) | $$0$$                          | $$0$$                                |
Where:
* $N_{a_r} = \text{Number of active units in source-set}$
* $N_{A_r} = \text{Total number of units in source-set}$
* $n_{\theta_{ri}} = \text{Number of stimuli associated to response} r_i$
* $K = \text{Arbitrary constat}$
## Analysis of the predominant phase
* For the following, assume a fixed threshold for the activation of the A-units (*fixed threshold model*).
* The other model is called *continuous transducer model*.
* Prediction of the learning curves of fixed-threshold perceptron, two variables: $$P_a = \text{the expected proportion of A-units activated by stimulus of a given size}$$
$$P_c = \text{the conditional probability that an A-unit which responds to a given stimulus}, S_1, \text{will also respond to another givent stimulus}, S_2$$
* As the size of the retina is increased, the number of S-points ($N_a$) quickly ceases to be a significant parameter, and the values of $P_a$ and $P_c$ approach the value that they would have for a retina with infinitely many points, therefore:
	$$
	P_a = \sum_{e=0}^x\sum_{i=0}^{\min(y,e-\theta)}P(e,i)
	\tag{1}
	$$
	where
$$
P(e,i) =  {{x}\choose{e}} R^e(1-R)^{x-e}\times{{y}\choose{i}}R^i(1-R)^{y-i}
$$
	and
$$
R = \text{proportion of S-points activated by the stimulus}
$$
$$
x = \text{number of excitatory connections to each A-unit}
$$
$$
y = \text{number of inhibitory connections to each A-unit}
$$
$$
\theta = \text{threshold of A-units}
$$
The quantities $e$ and $i$ are the excitatory and inhibitory components of the excitation received by the A-unit from the stimulus. If the algebraic sum $\alpha = e + i$ is equal to or greater tha $\theta$, the A-unit is assumed to respond.

$$
P_c = \frac{1}{P_a}\sum^x_{e=0}\sum^y_{i=e-\theta}\sum^e_{l_e=0}\sum^i_{l_i=0}\sum^{x-e}_{g_e=0}\sum^{y-i}_{g_i=0}P(e,i,l_e,l_i,g_e,g_i)
\tag{2}
$$
$$
(e-i-l_e+l_i+g_e-g_i \ge \theta)
$$
where
$$
\begin{align}
	P(e,i,l_e,l_i,g_e,g_i) \\
	&= {{x}\choose{e}}R^e(1-R)^{x-e} \\
	&\times {{y}\choose{i}}R^i(1-R)^{y-i} \\
	&\times {{e}\choose{l_e}}L^{l_e}(1-R)^{e-l_e} \\
	&\times {{i}\choose{l_i}}L^{l_i}(1-L)^{i-l_i} \\
	&\times {{x-e}\choose{g_e}} G^{g_e}(1-G)^{x-e-g_e} \\
	&\times {{y-i}\choose{g_i}} G^{g_i}(1-G)^{y-i-g_i}
\end{align}
$$
and
$$
L = \text{proportion of the S-points illuminated by the first stimulus}, S_1,
\text{which are not illuminated by}, S_2.
$$
$$
G = \text{proportion of the residual S-set (left over from the frist stimulus) which is included in the second stimulus} (S_2) \text{.}
$$
* The quantities $R$, $L$ and $G$ specify the two stimuli and their retinal overlap. 
* $l_e$ and $l_i$ are, respectively, the numbers of excitatory and inhibitory origin points "lost" bu the A-unit stimulus $S_1$ is replaced by $S_2$.
* $g_e$ and $g_i$ are the numbers of excitatory and inhibitory *origin points*  "gained" when stimulus $S_1$ is replaced by $S_2$.
* The summation in Equation 2 are between the limits indicated, subject to the side condition $e-i-l_e+l_i+g_e-g_i \geq \theta$.
* $P_a$ can be reduced in magnitude by either increasing the threshold or by incresing the proportion of inhibitory connections.
* $P_c$ is even more influenced by those changes.
$$
P_{e_\min} = (1 - L)^x(1 - G)^y
\tag{3}
$$
## Mathematical analysis of learning in the perceptron
* Activity is limitet to a single source-set, the other sets being suppressed.
* Two possible systems have been studied for the determination of the "dominant" response:
	1) $\mu-\text{system}$: The response whose inputs have the greatest mean value responds first.
	2) $\sum-\text{system}$: The response whose inputs have the greatest net value gains and advantage.
* The perceptron is expected to learn, as a result of the changes in value that occurs as a result of the activity in the cells. Two hypothetical experiments (They are the paradigm of [[Supervised learning | supervised learning]]); The perceptron is exposed to some series of stimulus patterns and:
	1) Is "forced" to give the desire response; Positive reinforcment when the response happens to be correct, and negative when not; When evaluating, the perceptrons are frozen (no values changes). Then, the probability that the perceptron will show a bias towards the "correct" response in preference to any given alternative response is called $P_r$.
	2) It's free to guess in front of a never seen stimuli. The thing here is the probability of the class of the stimuli, $P_g$, the probability of correct generalization; The probability that a bias will be found in favor of the proper response rather than any one alternative.
* The correct values are declared $P_R$ and $P_G$.
* Close approximation to them:
$$
P = P(N_{a_r} > 0) \cdot \phi(Z)
\tag{4}
$$
Where:
$$
P(N_{a_r} > 0) = 1 - (1 - P_a)^{N_e}
$$
$$
\phi = \text{normal curve integral from} \infty \to Z
$$
$$
Z = \frac{c_1 n_{a_r} + c_2}{\sqrt{c_3 n_{a_r}^2 + c_4 n_{a_r}}}
$$
* If $R_1$ is the "correct" response, and $R_2$ is the alternative response under consideration, Equation 4 is the probability that $R_1$ will be preferred over $R_2$ after $n_{a_r}$ stimuli have ben show for each of the two responses, during the learning period.
* $N_e$ is the number of "effective" A-units in each source-set; that is, the number of A-units in either soruce-set which are not connected in common to both responses.
* $N_{a_r}$ is the number of active units in a source-set, which respond to the test stimulus, $S_t \cdot P(N_{a_r} > 0)$ is the probability that at least one of the $N_e$ effective units in the source-set of the correct response will be activated by the test stimulus, $S_t$.
## Bivalent systems
* Two types of reinforcement:
	1) Positive ([[Reward | reward]]).
	2) Negative ([[Punishment | punishmet]]).
## Improved perceptrons and spentonaeous organization
* Preceding sections have omitted any consideration of *time* as stimulus dimension.
* The perceptron which has no capability for temporal pattern recognition is referred to as a *momentary stimulus perceptron*.
* The principle of statistical separability will permit the perceptron to distingish velocities, sound sequences, etc.
* The limit of the perceptron's capabilty seems to lie in the area of [[Relative judgment | relative judgment]], and [[Abstraction of relationships | abstraction of relationships]].
* Statistical separibily alone **does not provide a sufficient basis for higher order abstraction**.
* For that, we needs a more advanced system.
## Conclusions and evaluation
1) In an enviroment of random stimuli, a system constituted by percepron's, can learn to associate specific responses to specific stimuli.
2) The probability of a correct response diminishes towars its original random level as the number of the simuli learned increases.
3) No basis for generaliation exists.
4) The probability that a learned association of some specific simulus will be correctly retained typically approeaches a better-than-chance asymptote as the number of stimuli learned by the system incrases. This asymptote can be made arbitrarly close to unity by increasing the number of association cells in the system.
5) The probability that stimulus *which has not been en before* will be correctly recognized and associated to its appropiate class approaches the same asymptote as the probability of a correct response to a previously reinforced stimulus.
6) The performance of the system can be inmproved by the use of a contour-sensitive projection area and by thbe use of a [[Binary numeral system| binary]] response system.
7) Trial-and-error learning is possible in bivalent reinforcement systems.
8) Temporal organizations of both stimilus patterns and responses can be learned by a system which uses only an extension of the original principles of statistical separabilty.
9) The memory of the perceptron is *distributed*, in the sense that any association may make use of a large proportion of the cells in the system and the removal of a portion of the asociation system would not have an appreciable effect on the performance of any one discrimation or association, but would begin to show ups as a general deficit in *all* learned associations.
10) Simple cognitive sets, selective recall, and spontaneous recognition of the classes present in a given enviroment are possible. Relationships in space and time, seems to represent a limit to the perceptron's ability to form cognitive abstractions ([[Being and Time]]).
* The present system goes far beyond existing learning and behavior theories in three main points:
	1) Parsimony: All the variables and laws used in the system already exists. Only one hypotethical variable called V was postulated (value of an association cell - potential).
	2) Verifiability: Extrapolation of the learning in front of new stimuli.
	3) Explanatory power and generality: Not specific to any one organism or learning situation.