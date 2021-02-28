# Evolution-strategy

Experiments:
Evolve/train weights of neural networks on mediumMaze and hardMaze from Assignments 3 and 4.
Add one new algorithm not already in the notebook, to compare performance on the same domain. You can implement yourself, or use existing Python code (with attribution).
Add one new maze to test on. When designing the new maze, think about what you want it to test. What kind of challenges does your new maze pose?

How to analyze and present results:
You should plot quantitative results of your experiments. When designing such plots, think about: What are you hypothesizing or comparing? How does a plot answer or give insight into these questions?
Are your results reliable? For example, if you reran the same experiment a 2nd time, how similar would the results be? One way to answer this is to run multiple trials, compute standard deviation, and add error bars to the plot.
Look at animations of agent behavior. Besides the quantitative numbers, can you qualitatively conclude anything about what is going on with agent performance by observing successful and failed trials? When agents perform worse, what’s happening, where do they screw up? This should be part of the discussion/analysis of your results.


Write ups (answer questions such as):
What was your network topology?
What algorithm did you add and why?
What maze did you add and why?
What algorithm did best for each maze?
Etc.
Defend your statements with graphs/results.

Deliverables:
Code: Please submit your final assignment by extending this Google Colab file: https://colab.research.google.com/drive/1PG4rK79FqUsDvtkVMIkktGmU540hpBVs?usp=sharing
In your Colab notebook, show code corresponding to the three bullet points discussed under Experiments above. Then plot and discuss the results of those experiments, following the guidance in the three bullet points under “How to analyze and present results” above.
Summarize and discuss your overall findings. What did your experiments find?
Presentation (about 5 minutes): You will present your results to the class. You can do so during the final exam hours held on Discord December 17th: 2:30-5:00pm or through video. 
If you choose to present your results live, you do not need to submit a video
If you choose to present your results through video, you may submit a private Youtube link or Google Drive link through the Canvas assignment called Final Project Video (Optional) 


------------------
https://github.com/hardmaru/estool
Sample Questions: 
Which algorithms perform better on the domain(s) and why? Are there differences between the absolute performances or relative performances of the algorithms between domains (e.g., if alg 1 performs better than algorithm 2 on domain 1, and alg 2 performs better than alg 1 on domain 2, is there a clear potential reason why?). If alg1 performs better than alg 2 on domain 1 and alg1 performs better than alg2 on domain 2, is there an overall performance difference between domain 1 and 2 that makes one of the domains more difficult than the other?

Something core to your success as a researcher is learning to build experiments to test your ideas. Interestingly though, from my experience, this skill is often acquired through apprenticeship with your advisor rather than explicitly taught in courses. Often instructors define the parameters of the experiment for you by the way that they present the assignment to you (like I do below), but I think it is important to understand the process by which the experiments are truly formed rather than the idealized notions you often see described by science historians through the “scientific process.”

Because of normal space-time continuum constraints, like semesters ending, we are forced into a more narrow (i.e., typical) assignment structure (to be improved next semester). I formulate it with the maze code that we have gotten to know, but you are permitted to work with any domain of your choosing.

Many areas of AI detail the tradeoff between exploration and exploitation. Unlike the explicit tradeoff between exploration and exploitation phases in some RL algorithms in policies like epsilon-greedy, the tradeoff is often implicitly acknowledged in genetic algorithms, where exploration occurs through the representation of individuals, the genetic operators of mutation and crossover, the elitist selection process, and number of parents versus children. While typically the fitness function in GAs is designed only to exploit the space of possible solutions, Novelty Search (Lehman & Stanley, 2008) is the first genetic algorithm to use the fitness function to primarily explore.

In Lehman & Stanley (2008), the hypothesis is that novelty search will outperform fitness-based search when a fitness landscape is deceptive. That is, novelty search will find higher quality (i.e., fitness) solutions than standard fitness-based algorithms. Both algorithms are compared to a baseline random search, typical in the literature, which indicates the level of difficulty of the problem. Fitness is calculated at 300 minus distance to goal, where both mazes have a maximum distance to the goal of 300. Named for their relative levels of deception, the medium and hard maze are considered solved when after 400 steps in the environment, the controller ends within a threshold of “five units” or fitness points of the goal. 

The plots in figure 3a and 3b from the paper show the maximum fitness averaged over 40 runs by number of evaluations. Because fitness is calculated as f = 300 - distance, higher fitness means a better solution, a robot that gets closer to the goal. The Success Threshold is a horizontal line at y = 295 (fitness of 295)
