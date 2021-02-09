# Optimization Studies in SE (including Search-Based Software Engineering)
<standard name="Optimization Studies in SE (including Search-Based Software Engineering)">

Research studies that focus on the formulation of software engineering problems as search problems, and apply optimization techniques (e.g., metaheuristics and evolutionary algorithms) to solve such problems.

## Application

This standard applies to empirical studies that meet the following criteria:

- Formulates a software engineering task (e.g., test input creation, design refactoring, effort prediction) as an optimization problem, with one or more specified fitness functions used to judge success in this task.
- Applies one or more approaches that generate solutions to the problem in an attempt to maximize or minimize the specified fitness functions.

## Specific Attributes

We stress that the use of optimization in SE is still a rapidly evolving field. Hence, the following criteria are approximate and many exceptions exist to these criteria. Reviewers should reward sound and novel work and, where possible, support a diverse range of studies.

### Essential
<checklist name="Essential">

- [ ] Describe the search space  (e.g., constraints, independent variables choices) and explains why the optimization problem cannot be solved manually or through a brute force enumeration of all solutions within a reasonable timeframe (e.g., if the cross-product of the space of options is very large or if the time required to perform a task manually is very slow). 
- [ ] Do not over-simplify the optimization problem. In formulating the problem, simplifications and constraints should not reduce the search to one where all solutions could be enumerated through brute force.
- [ ] Include a description of prior state of the art in this area, if it exists. If it does not, then this study must carefully motivate and define the problem tackled and the solution proposed. 
- [ ] The algorithm underlying an approach (e.g., the specific metaheuristic) should be justified and appropriate for the problem being optimized. For example, do not use an algorithm such as Simulated Annealing, or even a specific approach such as NSGA-II, to solve an optimization problem unless it is actually appropriate for that problem. While one rarely knows the *best* approach for a new problem, one should at least consider the algorithms applied to address similar problems and make an informed judgement. 
- [ ] Approaches must be compared to a justified and appropriate baseline. If the approach addresses a problem never tackled before, then compare it to random search, at least. Otherwise, compare the proposed approach to the existing state of the art.
- [ ] The solution formulation must be explicitly defined, including a description of what a solution represents (e.g., a test suite or test case in test generation), how a solution is represented (e.g., a tree or vector structure), and how solutions are manipulated by the evaluated approaches. 
- [ ] All fitness functions used must be explicitly defined, including a description of the type of goals that are minimized or maximized and the equations for calculating the fitness value. 
- [ ] The evaluated approaches must be explicitly defined, including the applied techniques (e.g., Simulated Annealing, Genetic Algorithm), specific heuristics applied (e.g., single-point crossover), and the algorithm parameters and their values (e.g., crossover and mutation rates). 
- [ ] The effects of stochasticity must be understood and accounted for at all levels (e.g., in the use of randomized algorithms, in fitness functions that measure a random variable from the environment, and in data sampling). 
- [ ] Stochastic approaches must be executed multiple times, if this is not possible a justification should be provided (e.g., the approach is too slow, human-in-the-loop). 
- [ ] One should sample from data multiple times in a controlled manner. 
- [ ] Multiple trials can either be performed as a cross-validation (multiple independent executions) or temporally (multiple applications as part of a timed sequence) depeding on the problem at hand. 
- [ ] Compare results using statistics that compare distributions, rather than comparing the mean.
- [ ] When using statistics, favor non-parametric to parametric methods, as distributions are generally not known. Do not assume that data is normally distributed, unless you can provide an analysis showing normality. 
- [ ] Threats to validity must be made explicit. In replication or reproduction studies, the threats of the original study must be either addressed or acknowledged as still being threats.

</checklist>

### Desirable
<checklist name="Desirable">

- [ ] State if and how the study explores a new problem type (or a new area within an existing problem space) that has never been studied in the literature, or if the study reproduces and replicates prior work (and explains any small improvement). 
- [ ] To enable open science, a replication package should be made available that conforms to SIGSOFT standards for artifacts. 
- [ ] If data cannot be shared (e.g., industrial case study), it is desirable to create a sample dataset that can be shared to illustrate the use of the algorithms. 
- [ ] The option space chosen from in formulating a solution should be realistic. For example, if setting a value for an attribute, that value should reflect one that might be chosen in a "real-world" solution, and not generated from an arbitrary distribution.
- [ ] Provide justification for the parameter values used when executing the evaluated approaches (and note that experiments trying a wide range of different parameter values would be extraordinary, see below). 
- [ ] Use an appropriate meta-evaluation criteria to compare solutions. For example, if applying a multi-objective optimization approach, then use a criterion that can analyze the Pareto frontier of solutions (e.g., generational distance and inverse generational distance). Regardless of the chosen criteria, provide a justification for that choice. 

</checklist>

### Extraordinary
<checklist name="Extraordinary">

- [ ] Provide an analysis of different parameter choices to the algorithm, indicating how the final parameters were selected (e.g., applying hyperparameter optimization). 
- [ ] Provide an analysis of the fitness landscape for one or more of the chosen fitness functions. 
</checklist>

## General Quality Criteria

The most valuable quality criteria for optimization studies in SE include soundess, credibility, reliability, replicability, reproducibility, rigor, and usefulness (see **Glossary**). 

## Examples of Acceptable Deviations

 - The number of trials can be constrained by available time or experimental resources, in cases where experiments are time-consuming to repeat or have human elements. In such cases, multiple trials are still ideal, but a limited number of trials can be justified as long as the limitations are disclosed, and as long as the possible effects of stochasticity are discussed.
 - The use of industrial case studies is important in demonstrating the real-world application of a proposed technique, but industrial data generally cannot be shared. In such cases, it is recommended that a small open-source example be prepared and distributed as part of a replication package to demonstrate how the approach can be applied.

## Antipatterns

- Significance tests (e.g., Mann-Whitney Wilcoxon test) are used without effect size tests. 
   - "Significance" tests if distributions can be distingused from each other. But "Effect size" tests are required to check if the difference between distributions is "interesting" and not just a trivially "small effect".
- Multiple trials conducted, but no disclosure or discussion on the variation between trials. Reporting a median, without any indication of variance (e.g., a boxplot), does not indicate potential variation between each trial.

## Invalid Criticisms

- The paper is unimportant. Be cautious of rejection papers that seem “unimportant” (in the eyes of a reviewer).  While it is true that papers need a motivational statement (in order to increase the audience of a paper), it is also true that some major advances in the field arise only after much speculative exploration of novel approaches (that may currently seem unpromising).
- The paper just uses older algorithms with no reference to recent work.  Using  older (and widely understood algorithms) may be valid when they are used, e.g., (1) as part of a larger set that compares many approaches; e.g. (2) to offer a “straw man” method that defines the “floor” of the performance (that everything else needs to beat); or (3), as a workbench within which one thing is changed (e.g., the fitness function) but everything else remains constant.
 - A reproduction or replication study is just a repeat of prior work (see **Replication Studies**). Replications and reproductions are essential to the scientific method and the advancement of a field. Authors writing such reproduction/replication papers: (a) motivate the importance of the initial work (being replicated or reproduced here); (b) offer new insight beyond the initial study.
- That an approach is not benchmarked against an inappropriate or unavailable baseline. If a state-of-the-art approach lacks an available and functional implementation, it is not reasonable to expect the author to recreate that approach for benchmarking purposes. 
- That results of a study are negative (i.e., worse than a random search or other state-of-the-art). Such results are still valuable and advance the state of the field, as long as the study meets the general quality criteria and the essential attributes at least.
- That a multi-objective approach is not compared to a single-objective approach by evaluating each objective separately. This is not a meaningful comparison because, in a multi-objective problem, the trade-off between the objectives is a major factor in result quality. It is more important to consider the Pareto frontiers and quality indicators.

## Suggested Readings

- Amritanshu Agrawal, Tim Menzies, Leandro L. Minku, Markus Wagner, and Zhe Yu. 2020. Better software analytics via DUO: Data mining algorithms using/used-by optimizers." Empirical Software Engineering 25, no. 3. pp.2099-2136. DOI: https://doi.org/10.1007/s10664-020-09808-9
- Shaukat Ali, Lionel C. Briand, Hadi Hemmati, Rajwinder Kaur Panesar-Walawege. 2010. A Systematic Review of the Application and Empirical Investigation of Search-Based Test Case Generation," in IEEE Transactions on Software Engineering, vol. 36, no. 6, pp. 742-762, https://doi.org/10.1109/TSE.2009.52
- Andrea Arcuri and Lionel Briand. 2014. A Hitchhiker's guide to statistical tests for assessing randomized algorithms in software engineering. Softw. Test. Verif. Reliab. 24, 3, pp. 219–250. DOI: https://doi.org/10.1002/stvr.1486 
- Mark Harman, Phil McMinn, Jerffeson Teixeira Souza, and Shin Yoo. 2011. Search-Based Software Engineering: Techniques, Taxonomy, Tutorial. Empirical Software Engineering and Verification. Lecture Notes in Computer Science, vol. 7007, pp. 1–59. DOI: https://doi.org/10.1007/978-3-642-25231-0_1
- M. Li, T. Chen and X. Yao. 2020. How to Evaluate Solutions in Pareto-based Search-Based Software Engineering? A Critical Review and Methodological Guidance. In IEEE Transactions on Software Engineering. DOI: https://doi.org/10.1109/TSE.2020.3036108.
- Guenther Ruhe. 2020. Optimization in Software Engineering - A Pragmatic Approach. In Felderer, M. and Travassos, G.H. eds., Contemporary Empirical Methods in Software Engineering, Springer. DOI: https://doi.org/10.1007/978-3-030-32489-6_9 
- Norbert Siegmund, Stefan Sobernig, and Sven Apel. 2017. Attributed variability models: outside the comfort zone. In Proceedings of the 2017 11th Joint Meeting on Foundations of Software Engineering (ESEC/FSE 2017). Association for Computing Machinery, New York, NY, USA, 268–278. DOI: https://doi.org/10.1145/3106237.3106251

## Exemplars

- Hussein Almulla, Gregory Gay. 2020. Learning How to Search: Generating Exception-Triggering Tests Through Adaptive Fitness Function Selection. In Proceedings of 13th IEEE International Conference on Software Testing (ICST’20). IEEE, 63-73. DOI: https://doi.org/10.1109/ICST46399.2020.00017 
- José Campos, Yan Ge, Nasser Albunian, Gordon Fraser, Marcelo Eler and Andrea Arcuri. 2018. An empirical evaluation of evolutionary algorithms for unit test suite generation. Information and Software Technology. vol. 104, pp. 207–235. DOI: https://doi.org/10.1016/j.infsof.2018.08.010
- Jianfeng Chen, Vivek Nair, Rahul Krishna, Tim Menzies. “Sampling” as a Baseline Optimizer for Search-Based Software Engineering. IEEE Transactions on Software Engineering 2019 45(6), 2019. DOI: https://doi.org/10.1109/TSE.2018.2790925
- Annibale Panichella, Fitsum Meshesha Kifetew and Paolo Tonella. 2018. Automated Test Case Generation as a Many-Objective Optimisation Problem with Dynamic Selection of the Targets. IEEE Transactions on Software Engineering. vol. 44, no. 2, pp. 122–158. DOI: https://doi.org/10.1109/TSE.2017.2663435
- Federica Sarro, Alessio Petrozziello, and Mark Harman. 2016. Multi-objective software effort estimation. In Proceedings of the 38th International Conference on Software Engineering (ICSE'16). Association for Computing Machinery, New York, NY, USA, 619–630. DOI: https://doi.org/10.1145/2884781.2884830
- Federica Sarro, Filomena Ferrucci, Mark Harman, Alessandra Manna and Jen Ren.  2017. Adaptive Multi-Objective Evolutionary Algorithms for Overtime Planning in Software Projects. IEEE Transactions on Software Engineering, vol. 43, no. 10, pp. 898-917. DOI: https://doi.org/10.1109/TSE.2017.2650914

## Notes

**This standard is a living artifact.** We welcome pull requests with suggested edits to existing items, additional items in each category, suggested reading, and exemplar papers. 
