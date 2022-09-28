# Non- Deterministics Algorithm

<a href= "https://www.techopedia.com/definition/24618/non-deterministic-algorithm">Link 1</a>
<a href = "https://www.engati.com/glossary/non-deterministic-algorithm">Link 2</a>
<a href = "https://www.tutorialspoint.com/difference-between-deterministic-and-non-deterministic-algorithms">Link 3</a>

- can provide different outputs for the same inout of different execution
- useful when an exact solution is difficult or expensive to derive using a deterministic algorithm

### Example: Execution of concurrent algorithm with race condition

<u>concurrent</u>
: the ability of different parts or units of a program, algorithm, or problem to be executed out-of-order or in partial oder, without affecting the final outcome.

- nondeterministic algorithm takes many paths, with some arriving at the same outputs, but other different
- usualy has two phases and output stpes (guessing phase and verifying phase)
- guessing phase - makes use of arbitrary characters to run te problem
- verifying phase- returns true or ralse for the chosen string. 

