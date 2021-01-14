# Optimization Studies in SE (including SBSE)

*Research studies that focus on the formulation of software engineering problems as search problems, and apply optimization techniques (e.g., metaheuristics and evolutionary algorithms) to solve such problems.*

## Application

This standard applies to empirical studies that meet the following criteria:
- Formulates a software engineering task (e.g., test input creation, design refactoring, effort prediction) as an optimization problem, with one or more specified fitness functions used to judge success in this task.
- Applies one or more approaches that generate solutions to the problem in an attempt to maximize or minimize the specified fitness functions.

## Specific Attributes

We stress that the use of optimization in SE is still a rapidly evolving field. Hence, the following criteria are approximate and many exceptions exist to these criteria. Reviewers should reward sound and novel work and, where possible, support a diverse range of studies.

### Essential

- [ ] Describes the search space  (e.g. constraints, independent variables choices) and explains why the optimization problem cannot be solved manually or through a brute force enumeration of all solutions within a reasonable timeframe (e.g., if the cross-product of the space of options is very large or if the time required to perform a task manually is very slow). 
- [ ] Includes a description of prior state of the art in this area, if it exists. If it does not, then this study must carefully motivate and define the new problem and solution. 
- [ ] Approaches are compared to a justified and appropriate baseline. If the approach solves a new problem, compare it to random search, at least. If not a new problem, compare to the existing state of the art.
- [ ] As to algorithm selection:  The algorithm underlying an approach (e.g., the metaheuristic) should be justified and appropriate for the problem being optimized. Perhaps do use  not use simulated annealing, NSGA-II, etc. to solve an optimization problem unless it is actually the appropriate approach for the optimization problem.
- [ ] Also, using older older (and well udnerstfandood algorithms) may be valid when they are used as (1) as part of a larger  test suite that compares many approaches; e.g. (2) to offer a “straw man” method that defines the “floor” of the performance (that everything else needs to beat); e.g. (3) as a workbench within which one thing is changed (e.g. the fitness function) but everything else remains constant.
- [ ] The solution formulation is explicitly defined, including a description of what a solution represents (e.g., a test suite or test case in test generation), how a solution is represented in evaluated approaches (e.g., a tree or vector structure), and how solutions are manipulated by the evaluated approaches. 
- [ ] All fitness functions used are explicitly defined, including a description of the type of goals that are minimized or maximized and the equations for calculating the fitness score. 
- [ ] The evaluated approaches are explicitly defined, including the applied techniques (e.g., simulated annealing, genetic algorithm), specific heuristics applied (e.g., single-point crossover), and the algorithm parameters and their values (e.g. crossover and mutation rates). 
- [ ] The effects of stochasticity must be understood and accounted for at all levels (e.g., from the application of randomized algorithms, in fitness functions that measure a random variable from the environment, and in data sampling). 
  - Execute stochastic algorithms multiple times (using a different seed each time) or justify why this is not possible (e.g., approach is too slow, human-in-the-loop) 
  - Sample from data multiple times in a controlled manner. 
  - Multiple trials can either be performed as a cross-validation (multiple independent executions) or temporally (multiple applications as part of a timed sequence). 
- [ ] Compare results using statistics that compare distributions, rather than comparing the mean.

### Desirable

- [ ] Novelty is highly desirable. Where possible, authors should explore a new problem type (or a new area within an existing problem space) which has never been studied in the literature. 
- [ ] Reproductions and replications of prior work (perhaps with some small improvements) should be encouraged and rewarded. 
- [ ] To enable open science, a replication package should be made available that conforms to SIGSOFT standards for  artifacts. 
  - If data cannot be shared (e.g., industrial case study), it is desirable to create a sample dataset that can be shared to illustrate the use of the algorithms. 
- [ ] When using statistics, favor non-parametric to parametric methods, as distributions are generally not known. Do not assume that data is normally distributed, unless you can provide an analysis showing normality. 
- [ ] Provide justification for the parameter values used when executing the evaluated approaches (and note that experiments trying a wide range of different parameter values would be extraordinary, see below). 
- [ ] Use an appropriate meta-evaluation criteria to compare solutions. For example, if applying a  multi-objective optimization approach, then use a criterion that can analyze the Paretor frontier of solutions (e.g., generational distance and inverse generational distance). Regardless of the chosen criteria, provide a justification for that choice. 

### Extraordinary

- [ ] Provide an analysis of different parameter choices to the algorithm, indicating how the final parameters were selected (e.g., applying hyperparameter optimization). 
- [ ] Provide an analysis of the fitness landscape for one or more of the chosen fitness functions. 

## General Quality Criteria

The most valuable quality criteria for optimization studies in SE include credibility, reliability, replicability, reproducibility, rigor, and usefulness (see **Glossary**). 

## Examples of Acceptable Deviations

 - The number of trials can be constrained by available time or experimental resources, in cases where experiments are time-consuming to repeat or have human elements. In such cases, multiple trials are still ideal, but a limited number of trials can be justified as long as the limitations are disclosed, and as long as the possible effects of stochasticity are discussed.
 - The use of industrial case studies is important in demonstrating the real-world application of a proposed technique, but industrial data generally cannot be shared. In such cases, it is recommended that a small open-source example be prepared and distributed as part of a replication package to demonstrate how the approach can be applied.
 - Be cautious of rejection papers that seem “unimportant” (in the eyes of a reviewer).  While it is true that paper need a motivational statement (in order to increase the audience of a paper), it is also true that some major advances in the field arise only after much speculative exploration of novel approaches (that may currently seem unpromising).


## Antipatterns

- Significance tests (e.g., Mann-Whitney Wilcoxan test) without effect size tests. 
   - "Significance" tests if distriubtuins can be distingused fro each other.
   - But "effect size" tests are required to check if the difference between distributions is "interesting" and not just a trivirally "small effect".
- Multiple trials conducted, but no disclosure or discussion on the variation between trials. Reporting a median, without any indication of variance (e.g., a boxplot), does not indicate potential variation between each trial.

## Invalid Criticisms

- That a reproduction or replication study is just a repeat of prior work (see **Replication Studies**). Replications and reproductions are essential to the scientific method and the advancement of a field. 
  - To the authors writing such  reprodictiom papers: (a) motivate the importance of the initial work (being replicated or reproduced here) ; (b) offer new insight beyond the initial study. 
- That an approach is not benchmarked against an inappropriate or unavailable baseline. If a state-of-the-art approach lacks an available and functional implementation, it is not reasonable to expect the author to recreate that approach for benchmarking purposes. 
- That results are negative (i.e., worse than a random search or other state-of-the-art). Such results are still valuable and advance the state of the field.

## Notes

## Suggested Readings

- Amritanshu Agrawal, Tim Menzies, Leandro L. Minku, Markus Wagner, and Zhe Yu. "Better software analytics via" DUO": Data mining algorithms using/used-by optimizers." Empirical Software Engineering 25, no. 3 (2020): 2099-2136.
- Andrea Arcuri and Lionel Briand. 2014. A Hitchhiker's guide to statistical tests for assessing randomized algorithms in software engineering. Softw. Test. Verif. Reliab. 24, 3 (May 2014), 219–250. DOI:https://doi.org/10.1002/stvr.1486 
- M. Li, T. Chen and X. Yao, "How to Evaluate Solutions in Pareto-based Search-Based Software Engineering? A Critical Review and Methodological Guidance" in IEEE Transactions on Software Engineering, doi: 10.1109/TSE.2020.3036108

## Exemplars

- Hussein Almulla, Gregory Gay. Learning How to Search: Generating Exception-Triggering Tests Through Adaptive Fitness Function Selection. In Proceedings of 13th IEEE International Conference on Software Testing (ICST’20). IEEE, 63-73. DOI: https://doi.org/10.1109/ICST46399.2020.00017 
- Federica Sarro, Alessio Petrozziello, and Mark Harman. 2016. Multi-objective software effort estimation. In Proceedings of the 38th International Conference on Software Engineering (ICSE '16). Association for Computing Machinery, New York, NY, USA, 619–630. DOI:https://doi.org/10.1145/2884781.2884830
- Federica Sarro, Filomena Ferrucci, Mark Harman, Alessandra Manna and Jen Ren. Adaptive Multi-Objective Evolutionary Algorithms for Overtime Planning in Software Projects. IEEE Transactions on Software Engineering, vol. 43, no. 10, pp. 898-917, 1 Oct. 2017, doi: 10.1109/TSE.2017.2650914.
