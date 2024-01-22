# IBM Quantum Platform Quantum Composer [Notes]

+ Not gate flips 0 state to 1 state and vice versa, like classical gate
+ By default initialized to state 0
+ Can see probability of gate being in a certain state
+ Double not gate flips 0 to 1 then back to 0
+ Qubits can be in 0, 1, or superposition of two
+ Not gate flips probabilities associated with each of the states
+ Quantum superpostition: quantum phenomena that quantum computer harnesses
+ Flipping between 0 & 1 (100%)
+ H-gate is Hadamard gate
  + Splits probability 50-50 between 0 & 1 state
  + Many algorithms apply this gate first
+ Other probabilities for superpositions are possible depending on rotation
+ U-gate applies rotation
  + Changing rotation values can make the probabilities uneven
+ Applying Hadamard gates to two quibits creates an equal superposition of all four possibilities
+ 4 possibilities is all possible combinations of 2 bits
+ Many algorithms start by applying Hadamard to all qubits because it creates an equally weighted probability to all 4; this gives you all 4 possibilities to work with simultaneously
+ Can operate on them more than one at a time, unlike classical computing
+ q[0] is control qubit
+ Can correlate qubit states to know the probability of one state if you know the probability of the other, even if you separate them -> quantum entanglement
  + Allows you to know you get the same outcomes by performing the same operation on both
+ Measurement, quantum physics is proabbilities; therefore there is uncertainty & things can behave randomly
+ Despite state being definite, the physical can still behave randomly
+ Perform measurement operation to see what the states are
+ You don't know the final answer while processing until it is done
+ Equal proabbility while operation is being performed
+ Bell states (4 commonly used)
+ Measurement operators
  + After measurement, get one of two possible answer
  + Moving from uncertainty to certainty 
  + All possibilities reduce to just one
+ Ideal cases with perfect qubits; quantum systems are noisy & sensitive, so real case may be different than answer; run multiple times because you may get the wrong answer (shots), then the answer you get most often is answer
+ Statistics for ideal case with perfect qubits; compare to find results
+ Quantum Algoithm goal: find answer by manipulate probabilities by performing operations on the qubits such that the probabilities of getting the correct answer is increased; wrong answer is decreased
+ Quantum interference:
  + Destructive interference: two waves cancel each other out
  + Complementary interference: two waves amplify each other
+ Search algorithm
  + Search DB for some entry
+ Inspect in composer allows you to walk through what is happening in each step
+ Blue means positive, red means negative
+ Probability amplitudes can be negative because they are square roots; probability is always positive
+ Amplification vs. suppression
+ Iteration allows you to increase probability
+ Ensure place measurement operators in circuit to get results
+ Qubits are all connected to one another
+ Choose back end to run job on via Quantum Platform
+ Unwanted answers can turn up more often than expected due to noisiness of system
+ Export feature allows you to export circuit diagrams

+ Practice via: https://github.com/qiskit-community/quantum-explorers/blob/main/Captain_Badge/2023/QE_Introductory_Demo_2023.ipynb