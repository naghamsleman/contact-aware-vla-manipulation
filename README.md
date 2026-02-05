
# Towards Contact-Aware and Generalizable Vision-Language Manipulation
## Motivation

Recent Vision-Language-Action (VLA) models have demonstrated impressive generalization across diverse manipulation tasks by leveraging large-scale visual and linguistic pretraining. Systems such as RT-2 and CogACT show that semantic reasoning and hierarchical task understanding can be transferred from web-scale data to robotic control.

However, when deployed in real-world manipulation scenarios, these models often struggle in contact-rich settings where task success depends on precise physical interactions, accumulated execution errors, and incomplete visual feedback. Real robotic environments are inherently partially observable due to occlusions, sensor noise, and dynamic object interactions.

This indicates a significant disconnect between high-level semantic reasoning and low-level contact-sensitive execution. Although recent work has made progress in transforming the model to a robotic application (e.g., object-based generalization, continual action generation), there is no single framework that can allow for the execution of robust long-term manipulations while incorporating high-level semantic intent, the geometry of the object, and the physical dynamics of the contact.

## Related Work Analysis

### RT-2 (2023): Semantic and Task-Level Generalization

### CogACT (2024): Hierarchical Vision-Language Reasoning

### OmniManip (2024): Object-Level Generalization via Geometric Constraints

### Diffusion Policy (2023): Smooth and Contact-Rich Action Execution

### RT-2 (2023): Semantic and Task-Level Generalization

RT-2 demonstrates that large-scale vision-language models can be directly adapted to robotic control, enabling a single policy to perform a wide range of manipulation tasks specified through natural language. By leveraging semantic knowledge acquired from web-scale pretraining, RT-2 achieves strong task-level generalization without explicit task-specific pipelines.

However, this generalization is primarily semantic rather than physical. RT-2 lacks an explicit representation of object geometry or contact dynamics, leading to brittle behavior in contact-rich manipulation scenarios. Small execution errors often accumulate over time, limiting its effectiveness in long-horizon tasks and partially observable environments.

### CogACT (2024): Hierarchical Vision-Language Reasoning

CogACT introduces a more structured Vision-Language-Action architecture that separates perception, reasoning, and action generation. This componentized design enables hierarchical task decomposition and improves robustness across unseen objects and robot embodiments.

Despite these improvements, CogACT still relies on implicit physical reasoning. While hierarchical planning mitigates some long-horizon issues, the model does not explicitly model contact forces or interaction dynamics. As a result, its performance degrades in manipulation tasks where success critically depends on precise contact-aware control under partial observability.

### OmniManip (2024): Object-Level Generalization via Geometric Constraints

OmniManip focuses on improving generalization across unseen objects by introducing object-centric interaction primitives derived from geometric constraints. By grounding manipulation policies in spatial object representations, it enables more consistent behavior across variations in object shape and structure.

However, this approach assumes reliable object perception and accurate geometric representations, which are often unavailable in real-world scenarios with occlusions or sensor noise. Moreover, while object-level generalization is improved, OmniManip does not address semantic task understanding or long-horizon execution in contact-rich environments.

### Diffusion Policy (2023): Smooth and Contact-Rich Action Execution

Diffusion Policy models manipulation as a trajectory generation problem, using diffusion processes to produce smooth and temporally consistent action sequences. This approach significantly improves execution stability and is well-suited for contact-rich manipulation tasks where precise motion is required.

Nevertheless, Diffusion Policy operates primarily at the low-level control layer and lacks semantic reasoning or task-level planning. Without hierarchical structure or explicit feedback-driven replanning, its generalization to long-horizon tasks and novel environments remains limited.

