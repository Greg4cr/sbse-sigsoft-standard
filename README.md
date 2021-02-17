# Optimization Studies in SE (including Search-Based Software Engineering)
<standard name="Optimization Studies in SE (including Search-Based Software Engineering)">

Research studies that focus on the formulation of software engineering problems as search problems, and apply optimization techniques to solve such problems<sup>[1](#footnote1)</sup>.  

## Application

This standard applies to empirical studies that meet the following criteria:

- Formulates a software engineering task<sup>[2](#footnote2)</sup> as an optimization problem, with one or more specified fitness functions<sup>[3](#footnote3)</sup> used to judge success in this task.
- Applies one or more approaches that generate solutions to the problem in an attempt to maximize or minimize the specified fitness functions.

## Specific Attributes

We stress that the use of optimization in SE is still a rapidly evolving field. Hence, the following criteria are approximate and many exceptions exist to these criteria. Reviewers should reward sound and novel work and, where possible, support a diverse range of studies.

### Essential
<checklist name="Essential">

- [ ] Describe the search space (including constraints and independent variables choices) and explain why the optimization problem cannot be solved manually or through a brute force enumeration of all solutions within a reasonable timeframe<sup>[4](#footnote4)</sup>. 
- [ ] Use realistic and limited simplifications and constraints for the optimization problem. Simplifications and constraints must not reduce the search to one where all solutions could be enumerated through brute force.
- [ ] Either include a description of prior state of the art in this area or carefully motivate and define the problem tackled and the solution proposed. 
- [ ] The algorithm underlying an approach<sup>[5](#footnote5)</sup> should be justified and appropriate for the problem being optimized<sup>[6](#footnote6)</sup>.
- [ ] Approaches must be compared to a justified and appropriate baseline<sup>[7](#footnote7)</sup>.
- [ ] The solution formulation must be explicitly defined, including a description of what a solution represents<sup>[8](#footnote8)</sup>, how a solution is represented<sup>[9](#footnote9)</sup>, and how solutions are manipulated by the evaluated approaches. 
- [ ] All fitness functions used must be explicitly defined, including a description of the type of goals that are minimized or maximized and the equations for calculating the fitness value. 
- [ ] The evaluated approaches must be explicitly defined, including the applied techniques, specific heuristics applied, and the algorithm parameters and their values<sup>[10](#footnote10)</sup>. 
- [ ] Follow and clearly describe a sound process to collect and prepare the datasets used to run and to evaluate the optimization approach. If the subjects are taken from previous work, fully reference the original source and explain whether any transformation or cleaning was applied to the datasets. Otherwise, clearly describe the collection process and, wherever possible, make the subjects publicly available or explain why this is not possible<sup>[11](#footnote11)</sup>.
- [ ] All possible sources of stochasticity need to be identified, explained and accounted for by executing multiple repetition for each source where possible (otherwise, explain why this is not possible)<sup>[12](#footnote12)</sup>.
- [ ] Stochastic approaches must be executed multiple times. If this is not possible, a justification should be provided<sup>[13](#footnote13)</sup>.
- [ ] One should sample from data multiple times in a controlled manner (where appropriate and possible).
- [ ] Multiple trials can either be performed as a cross-validation (multiple independent executions) or temporally (multiple applications as part of a timed sequence), depending on the problem at hand. 
- [ ] Compare results using statistics that compare distributions, rather than comparing the mean.

</checklist>

### Desirable
<checklist name="Desirable">

- [ ] State if and how the study explores a new problem type (or a new area within an existing problem space) that has never been studied in the literature, or if the study reproduces and replicates prior work (and explains any small improvement). 
- [ ] Provide a detailed explanation on how subjects or datasets were collected and chosen in order to mitigate selection bias and improve the generalization of the findings. Describe the main features of the subjects used to run and evaluate the optimization approach(es) and discuss what characterizes the different instances in terms of "hardness". In case of data-driven approaches, if random data splits are used, this should be made publicly available or at least reproducibile. In case of synthetic data, clearly explain why real-world data cannot be used, and to what extend the proposed approach and the findings can be applicable to a real-world setting.
- [ ] To enable open science, a replication package should be made available that conforms to SIGSOFT standards for artifacts. 
- [ ] If data cannot be shared, it is desirable to create a sample dataset that can be shared to illustrate the use of the algorithms. 
- [ ] The option space chosen from in formulating a solution should be realistic. If setting a value for an attribute, that value should reflect one that might be chosen in a "real-world" solution, and not generated from an arbitrary distribution.
- [ ] Provide justification for the parameter values used when executing the evaluated approaches (and note that experiments trying a wide range of different parameter values would be extraordinary, see below). 
- [ ] Use an appropriate meta-evaluation criteria to compare solutions<sup>[14](#footnote14)</sup>. Regardless of the chosen criteria, provide a justification for that choice. 

</checklist>

### Extraordinary
<checklist name="Extraordinary">

- [ ] Provide an analysis of different parameter choices to the algorithm, indicating how the final parameters were selected<sup>[15](#footnote15)</sup>. 
- [ ] Provide an analysis of the fitness landscape for one or more of the chosen fitness functions. 
</checklist>

## General Quality Criteria

The most valuable quality criteria for optimization studies in SE include reliability, replicability, reproducibility, rigor, and usefulness (see **Glossary**). 

## Examples of Acceptable Deviations

 - The number of trials can be constrained by available time or experimental resources, in cases where experiments are time-consuming to repeat or have human elements. In such cases, multiple trials are still ideal, but a limited number of trials can be justified as long as the limitations are disclosed, and as long as the possible effects of stochasticity are discussed.
 - The use of industrial case studies is important in demonstrating the real-world application of a proposed technique, but industrial data generally cannot be shared. In such cases, it is recommended that a small open-source example be prepared and distributed as part of a replication package to demonstrate how the approach can be applied.

## Antipatterns

- Significance tests (e.g., Mann-Whitney Wilcoxon test) are used without effect size tests. 
  For more on these two tests, see **Notes**
- Multiple trials conducted, but no disclosure or discussion on the variation between trials. Reporting a median, without any indication of variance (e.g., a boxplot), does not indicate potential variation between each trial.

## Invalid Criticisms

- The paper is unimportant. Be cautious of rejection papers that seem “unimportant” (in the eyes of a reviewer). Research is exploratory and about taking risks. Clealy-motivated research and speculative exploration are both important and should be rewarded.
- The paper just uses older algorithms with no reference to recent work. Using  older (and widely understood algorithms) may be valid when they are used, e.g., (1) as part of a larger set that compares many approaches; e.g. (2) to offer a “straw man” method that defines the “floor” of the performance (that everything else needs to beat); or (3), as a workbench within which one thing is changed (e.g., the fitness function) but everything else remains constant.
- That an approach is not benchmarked against an inappropriate or unavailable baseline. If a state-of-the-art approach lacks an available and functional implementation, it is not reasonable to expect the author to recreate that approach for benchmarking purposes. 
- That a multi-objective approach is not compared to a single-objective approach by evaluating each objective separately. This is not a meaningful comparison because, in a multi-objective problem, the trade-off between the objectives is a major factor in result quality. It is more important to consider the Pareto frontiers and quality indicators.
- Reviewers should not reject a paper based on the fact that one or very few subjects are used as long as the paper clearly justifies why this was the case. We reccomend the reviewers to provide valid criticism as to why in their opinion a single subject is not sufficient, and whenever possible seek for more clarification from the authors on why it is not possible to use more subjects.

## Suggested Readings

- Shaukat Ali, Lionel C. Briand, Hadi Hemmati, Rajwinder Kaur Panesar-Walawege. 2010. A Systematic Review of the Application and Empirical Investigation of Search-Based Test Case Generation," in IEEE Transactions on Software Engineering, vol. 36, no. 6, pp. 742-762, DOI: https://doi.org/10.1109/TSE.2009.52
- Andrea Arcuri and Lionel Briand. 2014. A Hitchhiker's guide to statistical tests for assessing randomized algorithms in software engineering. Softw. Test. Verif. Reliab. 24, 3, pp. 219–250. DOI: https://doi.org/10.1002/stvr.1486 
- Amritanshu Agrawal, Tim Menzies, Leandro L. Minku, Markus Wagner, and Zhe Yu. 2020. Better software analytics via DUO: Data mining algorithms using/used-by optimizers." Empirical Software Engineering 25, no. 3. pp.2099-2136. DOI: https://doi.org/10.1007/s10664-020-09808-9
- Efron, Bradley, and Robert J. Tibshirani. An introduction to the bootstrap. CRC press, 1994
- Mark Harman, Phil McMinn, Jerffeson Teixeira Souza, and Shin Yoo. 2011. Search-Based Software Engineering: Techniques, Taxonomy, Tutorial. Empirical Software Engineering and Verification. Lecture Notes in Computer Science, vol. 7007, pp. 1–59. DOI: https://doi.org/10.1007/978-3-642-25231-0_1
- Vigdis By Kampenes, Tore Dybå, Jo E. Hannay, and Dag I. K. Sjøberg. 2007. Systematic review: A systematic review of effect size in software engineering experiments. Inf. Softw. Technol. 49, 11–12 (November, 2007), 1073–1086. DOI:https://doi.org/10.1016/j.infsof.2007.02.015
- M. Li, T. Chen and X. Yao. 2020. How to Evaluate Solutions in Pareto-based Search-Based Software Engineering? A Critical Review and Methodological Guidance. In IEEE Transactions on Software Engineering. DOI: https://doi.org/10.1109/TSE.2020.3036108.
- Nikolaos Mittas and Lefteris Angelis. Ranking and clustering software cost estimation models through a multiple comparisons algorithm. IEEE Trans. Software Eng.,
39(4):537–551, 2013.
- Guenther Ruhe. 2020. Optimization in Software Engineering - A Pragmatic Approach. In  Felderer, M. and Travassos, G.H. eds., Contemporary Empirical Methods in Software Engineering, Springer. DOI: https://doi.org/10.1007/978-3-030-32489-6_9


## Exemplars

- Hussein Almulla, Gregory Gay. 2020. Learning How to Search: Generating Exception-Triggering Tests Through Adaptive Fitness Function Selection. In Proceedings of 13th IEEE International Conference on Software Testing (ICST’20). IEEE, 63-73. DOI: https://doi.org/10.1109/ICST46399.2020.00017 
- Jianfeng Chen, Vivek Nair, Rahul Krishna, Tim Menzies. “Sampling” as a Baseline Optimizer for Search-Based Software Engineering. IEEE Transactions on Software Engineering 2019 45(6), 2019. DOI: https://doi.org/10.1109/TSE.2018.279092
- José Campos, Yan Ge, Nasser Albunian, Gordon Fraser, Marcelo Eler and Andrea Arcuri. 2018. An empirical evaluation of evolutionary algorithms for unit test suite generation. Information and Software Technology. vol. 104, pp. 207–235. DOI: https://doi.org/10.1016/j.infsof.2018.08.010
- Feather, Martin S., and Tim Menzies. "Converging on the optimal attainment of requirements." Proceedings IEEE Joint International Conference on Requirements Engineering. IEEE, 2002.
- G. Mathew, T. Menzies, N. Ernst and J. Klein. 2017.  "SHORT"er Reasoning About Larger Requirements Models. In 2017 IEEE 25th International Requirements Engineering Conference (RE), Lisbon, Portugal, pp. 154-163. doi: 10.1109/RE.2017.3
- Annibale Panichella, Fitsum Meshesha Kifetew and Paolo Tonella. 2018. Automated Test Case Generation as a Many-Objective Optimisation Problem with Dynamic Selection of the Targets. IEEE Transactions on Software Engineering. vol. 44, no. 2, pp. 122–158. DOI: https://doi.org/10.1109/TSE.2017.2663435
- Federica Sarro, Filomena Ferrucci, Mark Harman, Alessandra Manna and Jen Ren.  2017. Adaptive Multi-Objective Evolutionary Algorithms for Overtime Planning in Software Projects. IEEE Transactions on Software Engineering, vol. 43, no. 10, pp. 898-917. DOI: https://doi.org/10.1109/TSE.2017.2650914
- Federica Sarro, Alessio Petrozziello, and Mark Harman. 2016. Multi-objective software effort estimation. In Proceedings of the 38th International Conference on Software Engineering (ICSE'16). Association for Computing Machinery, New York, NY, USA, 619–630. DOI: https://doi.org/10.1145/2884781.2884830
- Norbert Siegmund, Stefan Sobernig, and Sven Apel. 2017. Attributed variability models: outside the comfort zone. In Proceedings of the 2017 11th Joint Meeting on Foundations of Software Engineering (ESEC/FSE. Association for Computing Machinery, New York, NY, USA, 268–278. DOI: https://doi.org/10.1145/3106237.3106251

## Notes

**This standard is a living artifact.** We welcome pull requests with suggested edits to 
existing items, additional items in each category, suggested reading, and exemplar papers. 

Regarding the difference between "significance" and "effect size" tests: "Significance" checks if distributions can be distinguished from each other while "Effect size" tests are required to check if the difference between distributions is "interesting" (and not just a trivially "small effect"). These tests can be parametric or non-parametric. For example, the parametric t-test/Hedges significance/effect tests endorsed by Kampenese et al. are coded up at https://tinyurl.com/y4o7ucnx.  Also a parametric Scott-Knot/Cohen test of the kind endorsed by Mittas et al. is coded at https://tinyurl.com/y5tg37fp. The non-parametric bootstrap/Cliffs Delta significant/effect tests of the   kind endorsed by  Efron et al. and Arcuri et al.
is coded at https://tinyurl.com/y2ufofgu.  


## Footnotes

<sup><a name="footnote1">1</a></sup>: Note that there are many such optimization techniques (metaheuristic; numerical optimizers; constraint solving theorem provers SAT,SMT,CSP; and other), some of which are stochastic. 

<sup><a name="footnote2">2</a></sup>: E.g., test input creation, design refactoring, effort prediction.

<sup><a name="footnote3">3</a></sup>: A "fitness function", or "objective function", is a numerical scoring function used to indicate the quality of a solution to a defined problem. Optimization approaches attempt to maximize or minimize such functions, depending on whether lower or higher scores indicate success.

<sup><a name="footnote4">4</a></sup>: E.g., if the cross-product of the space of options is very large or if the time required to perform a task manually is very slow.

<sup><a name="footnote5">5</a></sup>: E.g., the numerical optimizer, the specific metaheuristic, the constraint solving method, etc.

<sup><a name="footnote6">6</a></sup>: For example, do not use an algorithm such as Simulated Annealing, or even a specific approach such as NSGA-II, to solve an optimization problem unless it is actually appropriate for that problem. While one rarely knows the *best* approach for a new problem, one should at least consider the algorithms applied to address similar problems and make an informed judgement. 

<sup><a name="footnote7">7</a></sup>: If the approach addresses a problem never tackled before, then it should be compared - at least - to random search. Otherwise, compare the proposed approach to the existing state of the art.

<sup><a name="footnote8">8</a></sup>: E.g., a test suite or test case in test generation.

<sup><a name="footnote9">9</a></sup>: E.g., a tree or vector structure.

<sup><a name="footnote10">10</a></sup>: Example techniques - Simulated Annealing, Genetic Algorithm. Example heuristic - single-point crossover. Example parameters - crossover and mutation rates.

<sup><a name="footnote11">11</a></sup>: E.g., proprietary data, ethics issues, or a Non-Disclosure Agreement.

<sup><a name="footnote12">12</a></sup>: For example, stochasticity may arise from the use of randomized algorithms, from the use of a fitness function that measures a random variable from the environment (e.g., a fitness function based on execution time may return different results across different executions), from the use of data sampling or cross-validation approaches.

<sup><a name="footnote13">13</a></sup>: E.g., the approach is too slow, human-in-the-loop.

<sup><a name="footnote14">14</a></sup>: For example, if applying a multi-objective optimization approach, then use a criterion that can analyze the Pareto frontier of solutions (e.g., generational distance and inverse generational distance)

<sup><a name="footnote15">15</a></sup>: E.g., applying hyperparameter optimization.
