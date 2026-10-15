# Replication package

Beyond Racing Games: A Survey of Driving Intelligence Across Virtual Environments

## 1. Files and identifiers

[01_Final_included_reports.xlsx](01_Final_included_reports.xlsx) contains 452 included publication reports in the Included reports worksheet. It records bibliographic information, experimental settings, contribution and capability codes, system organization, evaluation results, evidence appraisal, and links between related reports.

[02_Selection_flow.xlsx](02_Selection_flow.xlsx) records the selection process in seven worksheets, preceded by a Flow summary:

| Worksheet | Contents |
| --- | --- |
| 01 Identified 3255 | database-export records before deduplication. |
| 02 Duplicates 976 | removed duplicate records and their Retained_Record_ID links. |
| 03 Screened 2279 | screened reports with inclusion or exclusion codes. |
| 04 Removed 1830 | excluded reports with E1–E4 codes. |
| 05 Database included 449 | reports included through database searching. |
| 06 Citation added 3 | additional reports included through citation searching. |
| 07 Final included 452 | the combined final corpus. |

Report_ID links a publication report across the two workbooks. Record_ID identifies an individual database-export occurrence. A publication may have several Record_ID values but one Report_ID. The final 452 Report_ID values are the same in both workbooks.

## 2. Search coverage

The literature searches were conducted between August 11 and August 30, 2026. Publications available by August 30, 2026 were eligible, with no lower publication-year limit.

Search fields:

- Scopus: Title–Abstract–Keywords (TITLE-ABS-KEY).
- Web of Science: Topic (TS).
- ACM Digital Library: Title, Abstract, and Author Keywords.
- IEEE Xplore: All Metadata.

Terms were organized into seven concept groups, listed in Appendix A. Terms within each group were joined with OR. Four search branches were used in each database:

- Branch A: A AND M.
- Branch B: R AND S AND M.
- Branch C: G AND V AND M.
- Branch D: D AND M.

Query_ID identifies the database and search branch. The branch letter is distinct from the concept-group letter. Appendix B contains the 16 database-specific expressions and their export counts. Its source labels distinguish saved protocol expressions from expressions recorded in the search log. Not all platform settings were preserved.

## 3. Retrieval and selection counts

| Database | A | B | C | D | Total |
| --- | ---: | ---: | ---: | ---: | ---: |
| Scopus | 361 | 210 | 1067 | 10 | 1648 |
| Web of Science | 87 | 61 | 215 | 110 | 473 |
| ACM Digital Library | 20 | 4 | 20 | 17 | 61 |
| IEEE Xplore | 165 | 129 | 634 | 145 | 1073 |
| Total | 633 | 404 | 1936 | 282 | 3255 |

Counts before deduplication refer to exported record occurrences. The same publication may be retrieved from several databases or through several branches within one database. Duplicate matching uses titles, author lists, and publication years. Retained_Record_ID links each removed occurrence to the retained record.

- 3,255 retrieved records - 976 duplicates = 2,279 screened reports.
- 2,279 screened reports - 1,830 exclusions = 449 database inclusions.
- 449 database inclusions + 3 citation-search additions = 452 included reports.

## 4. Eligibility codes

Inclusion criteria:

| Code | Meaning |
| --- | --- |
| `I1` | Studies on game driving, virtual racing, or directly relevant racing simulations. |
| `I2` | Autonomous-racing studies whose simulation or physical experiments directly inform these tasks, or general road-driving studies directly relevant to the review questions. |
| `I3` | Studies investigating computational driving behavior, enabling components evaluated within an eligible task, or empirical effects of driving-agent behavior. |

Included reports satisfy either I1 or I2, together with I3, and do not meet an exclusion criterion. In 03 Screened 2279, Inclusion_code records I1 + I3 for 275 reports and I2 + I3 for 174 reports. I1 and I2 can overlap; the code records the task route used for inclusion. The field is blank for excluded reports.

Exclusion criteria:

| Code | Meaning |
| --- | --- |
| `E1` | Outside the defined task scope or without an eligible contribution to driving-agent behavior or its evaluated effects. |
| `E2` | Publications other than primary journal articles or archival conference papers, including secondary studies, posters, invited summaries, and book chapters. |
| `E3` | Non-English main text. |
| `E4` | Insufficient methodological or experimental detail for classification, including reports whose full texts could not be obtained. |

Exclusion_code records E1 for 1,514 reports, E2 for 265, E3 for 3, and E4 for 48. 
The first and second authors independently screened reports, with disagreements adjudicated by the third author. The first and fourth authors independently coded included reports, with disagreements adjudicated by the fifth author.

## 5. Reading the coding fields

Each publication receives one Primary_Contribution_Capability label. Capability codes are nonexclusive and describe evaluated behavior:

| Code | Meaning |
| --- | --- |
| `C1` | Course following/steering. |
| `C2` | Speed/braking regulation. |
| `C3` | Stability/recovery. |
| `C4` | Resource-aware control. |
| `T1` | Obstacle/traffic negotiation. |
| `T2` | Overtaking/defending. |
| `T3` | Local coordination/following. |
| `S1` | Route/objective selection. |
| `S2` | Race/resource scheduling. |
| `S3` | Team-role coordination. |

Capability status:

| Code | Meaning |
| --- | --- |
| `DEM` | Implemented and evaluated through relevant behavior. |
| `IMP` | Implemented, without established corresponding behavioral evaluation. |
| `ABS` | Absence supported by the described system or task. |
| `PROP` | Proposed but not implemented. |
| `NR` | Insufficient information to resolve the code. |
| `N/A` | Not applicable. |

Control_Status, Tactical_Status, and Strategic_Status summarize the corresponding subcategories. An overall capability is DEM if at least one of its subcategories is DEM. Counts across capabilities or platforms may overlap and should not be summed as unique reports.

Policy_Organization describes unified, modular, cascaded, or multiple evaluated configurations. Decision_Hierarchy and Runtime_Hybrid_Flag are separate properties. Runtime_Hybrid_Flag uses 1 for confirmed hybridization, 0 when not identified, Variant_dependent when it depends on the evaluated configuration, NR when unresolved, and N/A when inapplicable. Training_Methods_confirmed and Runtime_Methods_confirmed distinguish methods used to obtain a policy from components used at deployment.

Q1–Q7 record task/system clarity, comparator fairness, experimental conditions, repetition/uncertainty, holdout/generalization, human-measure validity, and material traceability. Yes indicates adequate support, Partial limited support, No that the criterion is not met, NR unresolved evidence, and N/A an inapplicable criterion. These ratings describe evidence and are not combined into a quality score. Quality_rationale and Human_measure_rationale explain the assessments.

Study_link_IDs and Evidence_reuse_action identify related reports and shared empirical material. Publication counts do not represent independent replications.

## 6. Citation searching

One round of backward and forward citation searching used four seeds:

- R02205: Outracing champion Gran Turismo drivers with deep reinforcement learning.
- R02216: Driving as a human: a track learning based adaptable architecture for a car racing controller.
- R00005: EVOR: An online evolutionary algorithm for car racing games.
- R00003: Studying believability assessment in racing games.

Candidates were assessed using the same eligibility criteria as database reports. Reports already in the database corpus were not counted again, and newly identified reports were not used for another search round.

The three additions in 06 Citation added 3 are:

- SN001: Learning to Race: Experiments with a Simulated Race Car (1998). Backward search from R02205, reference 16.
- SN002: Deep Latent Competition: Learning to Race Using Visual Control Policies in Latent Space (2021). Backward search from R02205, reference 33.
- SN004: A Super-human Vision-based Reinforcement Learning Agent for Autonomous Racing in Gran Turismo (2024). Forward search from R02205, citing report section 4.2.

## Appendix A. Concept groups

### A

```text
"racing game" OR "racing games" OR "driving game" OR "driving games" OR "car racing game" OR "car racing games" OR "kart racing game" OR "kart racing games" OR "arcade racing"
```

### R

```text
"autonomous racing" OR "autonomous race car" OR "autonomous race cars" OR "autonomous racecar"
```

### S

```text
"simulation" OR "simulator" OR "simulators" OR "simulated" OR "virtual environment" OR "virtual environments" OR "video game" OR "video games"
```

### G

```text
"video game" OR "video games" OR "computer game" OR "computer games"
```

### V

```text
"vehicle" OR "vehicles" OR "driving" OR "racing" OR "car" OR "cars" OR "kart" OR "karts"
```

### D

```text
"TORCS" OR "Gran Turismo" OR "SuperTuxKart" OR "Forza" OR "Drivatar" OR "Drivatars" OR "Rocket League" OR "CarRacing"
```

### M

```text
"artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm"
```

## Appendix B. Database-specific search expressions

### ACM-A — 20 exported records

Source: Saved protocol expression.

```text
(Title:("racing game" OR "racing games" OR "driving game" OR "driving games" OR "car racing game" OR "car racing games" OR "kart racing game" OR "kart racing games" OR "arcade racing") OR Abstract:("racing game" OR "racing games" OR "driving game" OR "driving games" OR "car racing game" OR "car racing games" OR "kart racing game" OR "kart racing games" OR "arcade racing") OR Keyword:("racing game" OR "racing games" OR "driving game" OR "driving games" OR "car racing game" OR "car racing games" OR "kart racing game" OR "kart racing games" OR "arcade racing"))
AND
(Title:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm") OR Abstract:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm") OR Keyword:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm"))
```

### ACM-B — 4 exported records

Source: Saved protocol expression.

```text
(Title:("autonomous racing" OR "autonomous race car" OR "autonomous race cars" OR "autonomous racecar") OR Abstract:("autonomous racing" OR "autonomous race car" OR "autonomous race cars" OR "autonomous racecar") OR Keyword:("autonomous racing" OR "autonomous race car" OR "autonomous race cars" OR "autonomous racecar"))
AND
(Title:("simulation" OR "simulator" OR "simulators" OR "simulated" OR "virtual environment" OR "virtual environments" OR "video game" OR "video games") OR Abstract:("simulation" OR "simulator" OR "simulators" OR "simulated" OR "virtual environment" OR "virtual environments" OR "video game" OR "video games") OR Keyword:("simulation" OR "simulator" OR "simulators" OR "simulated" OR "virtual environment" OR "virtual environments" OR "video game" OR "video games"))
AND
(Title:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm") OR Abstract:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm") OR Keyword:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm"))
```

### ACM-C — 20 exported records

Source: Saved protocol expression.

```text
(Title:("video game" OR "video games" OR "computer game" OR "computer games") OR Abstract:("video game" OR "video games" OR "computer game" OR "computer games") OR Keyword:("video game" OR "video games" OR "computer game" OR "computer games"))
AND
(Title:("vehicle" OR "vehicles" OR "driving" OR "racing" OR "car" OR "cars" OR "kart" OR "karts") OR Abstract:("vehicle" OR "vehicles" OR "driving" OR "racing" OR "car" OR "cars" OR "kart" OR "karts") OR Keyword:("vehicle" OR "vehicles" OR "driving" OR "racing" OR "car" OR "cars" OR "kart" OR "karts"))
AND
(Title:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm") OR Abstract:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm") OR Keyword:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm"))
```

### ACM-D — 17 exported records

Source: Saved protocol expression.

```text
(Title:("TORCS" OR "Gran Turismo" OR "SuperTuxKart" OR "Forza" OR "Drivatar" OR "Drivatars" OR "Rocket League" OR "CarRacing") OR Abstract:("TORCS" OR "Gran Turismo" OR "SuperTuxKart" OR "Forza" OR "Drivatar" OR "Drivatars" OR "Rocket League" OR "CarRacing") OR Keyword:("TORCS" OR "Gran Turismo" OR "SuperTuxKart" OR "Forza" OR "Drivatar" OR "Drivatars" OR "Rocket League" OR "CarRacing"))
AND
(Title:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm") OR Abstract:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm") OR Keyword:("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm"))
```

### IEEE-A — 165 exported records

Source: Execution expression recorded in search log.

```text
("All Metadata":"racing game" OR "All Metadata":"racing games" OR "All Metadata":"driving game" OR "All Metadata":"driving games" OR "All Metadata":"car racing game" OR "All Metadata":"car racing games" OR "All Metadata":"kart racing game" OR "All Metadata":"kart racing games" OR "All Metadata":"arcade racing") AND ("All Metadata":"artificial intelligence" OR "All Metadata":"agent" OR "All Metadata":"agents" OR "All Metadata":"non-player character" OR "All Metadata":"non-player characters" OR "All Metadata":"NPC" OR "All Metadata":"AI opponent" OR "All Metadata":"AI opponents" OR "All Metadata":"computer-controlled opponent" OR "All Metadata":"adaptive opponent" OR "All Metadata":"dynamic difficulty adjustment" OR "All Metadata":"planning" OR "All Metadata":"control" OR "All Metadata":"controller" OR "All Metadata":"path planning" OR "All Metadata":"motion planning" OR "All Metadata":"decision making" OR "All Metadata":"decision-making" OR "All Metadata":"reinforcement learning" OR "All Metadata":"imitation learning" OR "All Metadata":"machine learning" OR "All Metadata":"deep learning" OR "All Metadata":"neural network" OR "All Metadata":"neural networks" OR "All Metadata":"rule-based" OR "All Metadata":"rule based" OR "All Metadata":"behavior tree" OR "All Metadata":"behaviour tree" OR "All Metadata":"finite state machine" OR "All Metadata":"model predictive control" OR "All Metadata":"optimization" OR "All Metadata":"optimisation" OR "All Metadata":"evolutionary algorithm" OR "All Metadata":"genetic algorithm")
```

### IEEE-B — 129 exported records

Source: Execution expression recorded in search log.

```text
("All Metadata":"autonomous racing" OR "All Metadata":"autonomous race car" OR "All Metadata":"autonomous race cars" OR "All Metadata":"autonomous racecar") AND ("All Metadata":"simulation" OR "All Metadata":"simulator" OR "All Metadata":"simulators" OR "All Metadata":"simulated" OR "All Metadata":"virtual environment" OR "All Metadata":"virtual environments" OR "All Metadata":"video game" OR "All Metadata":"video games") AND ("All Metadata":"artificial intelligence" OR "All Metadata":"agent" OR "All Metadata":"agents" OR "All Metadata":"non-player character" OR "All Metadata":"non-player characters" OR "All Metadata":"NPC" OR "All Metadata":"AI opponent" OR "All Metadata":"AI opponents" OR "All Metadata":"computer-controlled opponent" OR "All Metadata":"adaptive opponent" OR "All Metadata":"dynamic difficulty adjustment" OR "All Metadata":"planning" OR "All Metadata":"control" OR "All Metadata":"controller" OR "All Metadata":"path planning" OR "All Metadata":"motion planning" OR "All Metadata":"decision making" OR "All Metadata":"decision-making" OR "All Metadata":"reinforcement learning" OR "All Metadata":"imitation learning" OR "All Metadata":"machine learning" OR "All Metadata":"deep learning" OR "All Metadata":"neural network" OR "All Metadata":"neural networks" OR "All Metadata":"rule-based" OR "All Metadata":"rule based" OR "All Metadata":"behavior tree" OR "All Metadata":"behaviour tree" OR "All Metadata":"finite state machine" OR "All Metadata":"model predictive control" OR "All Metadata":"optimization" OR "All Metadata":"optimisation" OR "All Metadata":"evolutionary algorithm" OR "All Metadata":"genetic algorithm")
```

### IEEE-C — 634 exported records

Source: Execution expression recorded in search log.

```text
("All Metadata":"video game" OR "All Metadata":"video games" OR "All Metadata":"computer game" OR "All Metadata":"computer games") AND ("All Metadata":"vehicle" OR "All Metadata":"vehicles" OR "All Metadata":"driving" OR "All Metadata":"racing" OR "All Metadata":"car" OR "All Metadata":"cars" OR "All Metadata":"kart" OR "All Metadata":"karts") AND ("All Metadata":"artificial intelligence" OR "All Metadata":"agent" OR "All Metadata":"agents" OR "All Metadata":"non-player character" OR "All Metadata":"non-player characters" OR "All Metadata":"NPC" OR "All Metadata":"AI opponent" OR "All Metadata":"AI opponents" OR "All Metadata":"computer-controlled opponent" OR "All Metadata":"adaptive opponent" OR "All Metadata":"dynamic difficulty adjustment" OR "All Metadata":"planning" OR "All Metadata":"control" OR "All Metadata":"controller" OR "All Metadata":"path planning" OR "All Metadata":"motion planning" OR "All Metadata":"decision making" OR "All Metadata":"decision-making" OR "All Metadata":"reinforcement learning" OR "All Metadata":"imitation learning" OR "All Metadata":"machine learning" OR "All Metadata":"deep learning" OR "All Metadata":"neural network" OR "All Metadata":"neural networks" OR "All Metadata":"rule-based" OR "All Metadata":"rule based" OR "All Metadata":"behavior tree" OR "All Metadata":"behaviour tree" OR "All Metadata":"finite state machine" OR "All Metadata":"model predictive control" OR "All Metadata":"optimization" OR "All Metadata":"optimisation" OR "All Metadata":"evolutionary algorithm" OR "All Metadata":"genetic algorithm")
```

### IEEE-D — 145 exported records

Source: Saved protocol expression.

```text
("All Metadata":"TORCS" OR "All Metadata":"Gran Turismo" OR "All Metadata":"SuperTuxKart" OR "All Metadata":"Forza" OR "All Metadata":"Drivatar" OR "All Metadata":"Drivatars" OR "All Metadata":"Rocket League" OR "All Metadata":"CarRacing") AND ("All Metadata":"artificial intelligence" OR "All Metadata":"agent" OR "All Metadata":"agents" OR "All Metadata":"non-player character" OR "All Metadata":"non-player characters" OR "All Metadata":"NPC" OR "All Metadata":"AI opponent" OR "All Metadata":"AI opponents" OR "All Metadata":"computer-controlled opponent" OR "All Metadata":"adaptive opponent" OR "All Metadata":"dynamic difficulty adjustment" OR "All Metadata":"planning" OR "All Metadata":"control" OR "All Metadata":"controller" OR "All Metadata":"path planning" OR "All Metadata":"motion planning" OR "All Metadata":"decision making" OR "All Metadata":"decision-making" OR "All Metadata":"reinforcement learning" OR "All Metadata":"imitation learning" OR "All Metadata":"machine learning" OR "All Metadata":"deep learning" OR "All Metadata":"neural network" OR "All Metadata":"neural networks" OR "All Metadata":"rule-based" OR "All Metadata":"rule based" OR "All Metadata":"behavior tree" OR "All Metadata":"behaviour tree" OR "All Metadata":"finite state machine" OR "All Metadata":"model predictive control" OR "All Metadata":"optimization" OR "All Metadata":"optimisation" OR "All Metadata":"evolutionary algorithm" OR "All Metadata":"genetic algorithm")
```

### SCO-A — 361 exported records

Source: Saved protocol expression.

```text
TITLE-ABS-KEY("racing game" OR "racing games" OR "driving game" OR "driving games" OR "car racing game" OR "car racing games" OR "kart racing game" OR "kart racing games" OR "arcade racing")
AND
TITLE-ABS-KEY("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm")
```

### SCO-B — 210 exported records

Source: Saved protocol expression.

```text
TITLE-ABS-KEY("autonomous racing" OR "autonomous race car" OR "autonomous race cars" OR "autonomous racecar")
AND
TITLE-ABS-KEY("simulation" OR "simulator" OR "simulators" OR "simulated" OR "virtual environment" OR "virtual environments" OR "video game" OR "video games")
AND
TITLE-ABS-KEY("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm")
```

### SCO-C — 1067 exported records

Source: Saved protocol expression.

```text
TITLE-ABS-KEY("video game" OR "video games" OR "computer game" OR "computer games")
AND
TITLE-ABS-KEY("vehicle" OR "vehicles" OR "driving" OR "racing" OR "car" OR "cars" OR "kart" OR "karts")
AND
TITLE-ABS-KEY("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm")
```

### SCO-D — 10 exported records

Source: Saved protocol expression.

```text
TITLE-ABS-KEY("TORCS" OR "Gran Turismo" OR "SuperTuxKart" OR "Forza" OR "Drivatar" OR "Drivatars" OR "Rocket League" OR "CarRacing")
AND
TITLE-ABS-KEY("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm")
```

### WOS-A — 87 exported records

Source: Saved protocol expression.

```text
TS=("racing game" OR "racing games" OR "driving game" OR "driving games" OR "car racing game" OR "car racing games" OR "kart racing game" OR "kart racing games" OR "arcade racing")
AND
TS=("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm")
```

### WOS-B — 61 exported records

Source: Saved protocol expression.

```text
TS=("autonomous racing" OR "autonomous race car" OR "autonomous race cars" OR "autonomous racecar")
AND
TS=("simulation" OR "simulator" OR "simulators" OR "simulated" OR "virtual environment" OR "virtual environments" OR "video game" OR "video games")
AND
TS=("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm")
```

### WOS-C — 215 exported records

Source: Saved protocol expression.

```text
TS=("video game" OR "video games" OR "computer game" OR "computer games")
AND
TS=("vehicle" OR "vehicles" OR "driving" OR "racing" OR "car" OR "cars" OR "kart" OR "karts")
AND
TS=("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm")
```

### WOS-D — 110 exported records

Source: Saved protocol expression.

```text
TS=("TORCS" OR "Gran Turismo" OR "SuperTuxKart" OR "Forza" OR "Drivatar" OR "Drivatars" OR "Rocket League" OR "CarRacing")
AND
TS=("artificial intelligence" OR "agent" OR "agents" OR "non-player character" OR "non-player characters" OR "NPC" OR "AI opponent" OR "AI opponents" OR "computer-controlled opponent" OR "adaptive opponent" OR "dynamic difficulty adjustment" OR "planning" OR "control" OR "controller" OR "path planning" OR "motion planning" OR "decision making" OR "decision-making" OR "reinforcement learning" OR "imitation learning" OR "machine learning" OR "deep learning" OR "neural network" OR "neural networks" OR "rule-based" OR "rule based" OR "behavior tree" OR "behaviour tree" OR "finite state machine" OR "model predictive control" OR "optimization" OR "optimisation" OR "evolutionary algorithm" OR "genetic algorithm")
```
