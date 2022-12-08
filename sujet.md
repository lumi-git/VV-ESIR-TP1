
# Q1 :


Find in news sources a general public article reporting the discovery of a software bug. Describe the bug. If possible, say whether the bug is local or global and describe the failure that manifested its presence. Explain the repercussions of the bug for clients/consumers and the company or entity behind the faulty program. Speculate whether, in your opinion, testing the right scenario would have helped to discover the fault.
## Answer Q1 :

>### Map 256 Glitch in them pacman game: 
>In the 256th level of Pac-Man, a bug results in a kill screen. The maximum number of fruit available is seven and when that number rolls over, it causes the entire right side of the screen to become a jumbled mess of symbols while the left side remains normal.

 >A stage or level in a video game (often an arcade game) that stops the player's progress due to a software bug. Not to be mistaken for a game over screen, kill screens can result in unpredictable gameplay and bizarre glitches [[1](https://pacman.fandom.com/wiki/Map_256_Glitch#:~:text=Otherwise%20known%20as%20the%20%22split,It%20is%20impossible%20to%20beat)].




# Q2 :
Apache Commons projects are known for the quality of their code and development practices. They use dedicated issue tracking systems to discuss and follow the evolution of bugs and new features. The following link https://issues.apache.org/jira/projects/COLLECTIONS/issues/COLLECTIONS-794?filter=doneissues points to the issues considered as solved for the Apache Commons Collections project. Among those issues find one that corresponds to a bug that has been solved. Classify the bug as local or global. Explain the bug and the solution. Did the contributors of the project add new tests to ensure that the bug is detected if it reappears in the future?

## Answer Q2 :
>__Issue choice__ : https://issues.apache.org/jira/projects/COLLECTIONS/issues/COLLECTIONS-813?filter=doneissues


>__Type__ : local

>__Bug__ : Partial check of function parameters, whether they are NULL.

>__Solution__ : add a check on each function parameter 

>__Test__ :  The contributor adds units tests witch pass null parameters to the function to assert NULL parameter are recognized.

# Q3 :
Netflix is famous, among other things we love, for the popularization of *Chaos Engineering*, a fault-tolerance verification technique. The company has implemented protocols to test their entire system in production by simulating faults such as a server shutdown. During these experiments they evaluate the system's capabilities of delivering content under different conditions. The technique was described in [a paper](https://arxiv.org/ftp/arxiv/papers/1702/1702.05843.pdf) published in 2016. Read the paper and briefly explain what are the concrete experiments they perform, what are the requirements for these experiments, what are the variables they observe and what are the main results they obtained. Is Netflix the only company performing these experiments? Speculate how these experiments could be carried in other organizations in terms of the kind of experiment that could be performed and the system variables to observe during the experiments.

## Answer Q3
>The experiments are about doing tests during the load. This is called “Chaos Engineering”.
For Netflix, this behaves as shutting down servers and seeing how the service responds.

>this is how a experiment is done :
Based on the principles, define an experiment: 
>1. Start by defining ‘steady state’ as some measurable output of a system that indicates normal behavior. 
>2. Hypothesize that this steady state will continue in both the control group and the experimental group.
 >3. Introduce variables that reflect real world events like servers that crash, hard drives that malfunction, network connections that are severed. 
>4. Try to disprove the hypothesis by looking for a difference in steady state between the control group and the experimental group.

>Netflix is not the only one company to use this type of testing strategy we can also find Amazon , Google, Microsoft, and Facebook

>To apply this strategy to other company, they need to have a pretty big server network, to be able to redirect services to other server during the chaos. The company also need to have a way to monitor the network to compare the control group and the experimental group datas during a period.


# Q4
[WebAssembly](https://webassembly.org/) has become the fourth official language supported by web browsers. The language was born from a joint effort of the major players in the Web. Its creators presented their design decisions and the formal specification in [a scientific paper](https://people.mpi-sws.org/~rossberg/papers/Haas,%20Rossberg,%20Schuff,%20Titzer,%20Gohman,%20Wagner,%20Zakai,%20Bastien,%20Holman%20-%20Bringing%20the%20Web%20up%20to%20Speed%20with%20WebAssembly.pdf) published in 2018. The goal of the language is to be a low level, safe and portable compilation target for the Web and other embedding environments. The authors say that it is the first industrial strength language designed with formal semantics from the start. This evidences the feasibility of constructive approaches in this area. Read the paper and explain what are the main advantages of having a formal specification for WebAssembly. In your opinion, does this mean that WebAssembly implementations should not be tested?
## Answer Q4
>The formal specification allows a large number of properties to be caused. This does not prevent the occurrence of bugs related to properties outside the fields verified by the formal specification, such as human error and probabilistic processes.

# Q5
Shortly after the appearance of WebAssembly another paper proposed a mechanized specification of the language using Isabelle. The paper can be consulted here: https://www.cl.cam.ac.uk/~caw77/papers/mechanising-and-verifying-the-webassembly-specification.pdf. This mechanized specification complements the first formalization attempt from the paper. According to the author of this second paper, what are the main advantages of the mechanized specification? Did it help improving the original formal specification of the language? What other artifacts were derived from this mechanized specification? How did the author verify the specification? Does this new specification removes the need for testing?
## Answer Q5

>
 ### Answer of question 5

a) The Mechanical is safer because the specification is
examined by software using maths. 

b) By using this, it helps to highlight some
issues found in the former version. 


c) This time, the testing is happening on the software testing the software.

d) The artifacts derived from the mechanization are typechecker and executable interpreter.

e) We verify the specification with the result of this methode : 
the interpreter, test, artifacts.

f) The Mechanical Specification is not a reason for stopping
using tests, it can be used as a secondary verification.

