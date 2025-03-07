- **Probabilistic model**: mathematical framework to solve uncertainty problem
- **Random event**: an outcome or a set of outcomes from a random experiment, where the result is uncertain before the experiment is conducted
- **Sample space**: a set of **all possible outcomes** of a random experiment
- **Event**: a **subset** of the sample space that includes one or more possible outcomes

| Feature                       | Discrete Model                                  | Continuous Model                       |
| ----------------------------- | ----------------------------------------------- | -------------------------------------- |
| Values of the Variable        | Countable, distinct values (e.g., 0, 1, 2, ...) | Infinite possible values in a range    |
| Probability Function          | **Probability Mass Function (PMF)**             | **Probability Density Function (PDF)** |
| Probability of a Single Value | Can be **greater than zero**                    | Always **zero**                        |
| Example Distributions         | Bernoulli, Binomial, Poisson                    | Uniform, Normal, Exponential           |
| Example Applications          | Coin flips, dice rolls, customer count          | Temperature, time, height              |

### Axioms of Probability (**Kolmogorov’s Axioms**)
- non negativity: Probabilities cannot be negative
- normalization: The probability of entire sample is 1
- Additivity: Probabilities of disjoint events add up
		P(A∪B)=P(A)+P(B),if A∩B=∅

### Extended Rules Derived from Axioms
- Complement: $P(A)^c=1−P(A)$
	Example: If the probability of rain today is 0.3, the probability that it **won’t** rain is
- Inclusion-Exclusion (for Non-Disjoint Events)
	P(A∪B)=P(A)+P(B)−P(A∩B)
	Example: If 60% of students like math and 50% like science, but 30% like both, the probability of a student liking either subject is 60% + 50% - 30% = 80%
