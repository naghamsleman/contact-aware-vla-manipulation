
# Towards Contact-Aware and Generalizable Vision-Language Manipulation
## Motivation

Recent Vision-Language-Action (VLA) models have demonstrated impressive generalization across diverse manipulation tasks by leveraging large-scale visual and linguistic pretraining. Systems such as RT-2 and CogACT show that semantic reasoning and hierarchical task understanding can be transferred from web-scale data to robotic control.

However, when deployed in real-world manipulation scenarios, these models often struggle in contact-rich settings where task success depends on precise physical interactions, accumulated execution errors, and incomplete visual feedback. Real robotic environments are inherently partially observable due to occlusions, sensor noise, and dynamic object interactions.

This indicates a significant disconnect between high-level semantic reasoning and low-level contact-sensitive execution. Although recent work has made progress in transforming the model to a robotic application (e.g., object-based generalization, continual action generation), there is no single framework that can allow for the execution of robust long-term manipulations while incorporating high-level semantic intent, the geometry of the object, and the physical dynamics of the contact.
