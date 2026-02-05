
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

## Comparative Insight
Even though the analyzed studies cover separate pieces of how robots grasp objects, there is no single method that handles complex scenarios - especially when objects move, touch each other, and appear in unpredictable settings.

Though built for vision tasks, CogACT leans too heavily on unseen physical cues. RT-2 handles meaning and actions better after extensive learning across images and text. Over months, its steps drift slightly, losing precision. Yet it lacks direct interaction practice in design. What helps CogACT falter is also what it fails to make explicit.

OmniManip looks at objects in a more detailed way, helping it work better with different shapes. Still, fixing on geometry means less room to interpret what things mean. It also needs clear object detection to function well. On the flip side, the Diffusion Policy handles step-by-step actions by producing flowing, consistent paths. Yet, those paths come without deeper understanding or changing plans mid-task.

When looked at as a whole, something stands out. Most efforts focus on just one type of task - like understanding language, making broad predictions about things, or adjusting small actions. Yet hardly any attempt to bring these pieces together into a single system. That kind of setup would allow robots to plan ahead, respond physically, and adapt across time.

## Open Problem

Despite recent progress in vision-language models, object-centric representations, and learning-based control, robotic manipulation systems still struggle with long-horizon tasks in real-world settings. Most existing approaches handle reasoning, perception, and control as largely separate problems, which works for short and well-structured tasks but breaks down as interactions become longer and more complex.

In contact-rich environments, small errors in perception or execution tend to accumulate over time, especially under partial observability. Systems that reason well often lack physical grounding, while those that execute stable motions typically operate without a strong understanding of task semantics or object relationships.

The open problem is how to design a manipulation system that can maintain coherent task-level reasoning while staying physically grounded and stable throughout extended sequences of actions, rather than succeeding only at isolated skills.


## Research Hypothesis

A more robust approach to long-horizon manipulation may emerge from combining three complementary ideas. High-level vision-language reasoning can help a robot understand what needs to be done and break complex tasks into meaningful steps. Object-centric geometric representations can anchor these decisions in the physical structure of the environment, making actions more consistent with real-world interactions. Diffusion-based control, in turn, can shape low-level motions into smooth and stable trajectories over time.

When these components are allowed to interact, the system is less likely to accumulate small execution errors that typically derail long tasks. Such an integration could lead to more stable behavior under uncertainty, especially in contact-rich and partially observed settings where both reasoning and precise control are required.



