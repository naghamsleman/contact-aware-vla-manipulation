# Paper Analysis

## RT-2 (2023)

**What problem does it address?**  
RT-2 focuses on semantic and task-level generalization in robotic manipulation by leveraging large-scale vision-language pretraining.

**Main idea / approach**  
The model maps vision-language inputs directly to actions using a transformer trained on a mixture of web-scale data and robot demonstrations.

**Strengths**  
Strong semantic generalization and the ability to perform unseen tasks through language conditioning.

**Limitations**  
Lacks explicit physical grounding and exhibits execution drift in long-horizon tasks, particularly in contact-rich scenarios.

**Relation to generalization & long-horizon**  
Generalizes well at the task level but struggles to maintain consistency over extended action sequences.


## CogACT (2024)

**What problem does it address?**  
CogACT aims to improve long-horizon task execution through hierarchical reasoning and cognitive planning.

**Main idea / approach**  
Introduces a hierarchical architecture where high-level reasoning guides lower-level action policies.

**Strengths**  
Improved task decomposition and robustness compared to flat policies.

**Limitations**  
Relies on implicit physical understanding and does not explicitly model object geometry or contacts.

**Relation to generalization & long-horizon**  
Better long-horizon stability, but limited physical grounding affects generalization in complex manipulation.


## OmniManip (2024)

**What problem does it address?**  
Targets object-level generalization across varying shapes and geometries.

**Main idea / approach**  
Uses object-centric representations to guide manipulation policies across different object instances.

**Strengths**  
Strong generalization across object geometries and improved physical consistency.

**Limitations**  
Reduced semantic flexibility and dependency on reliable object perception.

**Relation to generalization & long-horizon**  
Improves physical generalization but does not address long-horizon task reasoning.


## Diffusion Policy (2023)

**What problem does it address?**  
Focuses on stable and smooth low-level control for robotic manipulation.

**Main idea / approach**  
Generates action trajectories using diffusion models conditioned on observations.

**Strengths**  
Produces smooth, contact-aware motions and robust execution.

**Limitations**  
Lacks task-level reasoning and cannot adapt behavior over long horizons.

**Relation to generalization & long-horizon**  
Strong execution, but limited adaptability and no semantic generalization.

