Here is a more detailed and professional version of your README, expanded with technical specifics from your project's methodology and findings:

Predicting Variation in Emotional Valence and Arousal over Time from Ecological Essays
This repository contains the full implementation and documentation for the SemEval-2026 Task 2 project. The study focuses on capturing the dynamic nature of human emotions in written ecological essays, modeling them as continuous values within the Circumplex Model of Affect.

🚀 Project Overview

Traditional sentiment analysis often treats emotion as a static label. This project approaches emotion as a shifting state, predicting Valence (pleasure to displeasure) and Arousal (intensity to calmness) as they evolve through a narrative. By treating this as a continuous regression problem, we aim to capture subtle contextual nuances that categorical models often miss.

🛠️ Technical Deep Dive

1. Data Pipeline & Preprocessing
To handle the informal and narrative nature of ecological essays, we implemented a rigorous cleaning pipeline:

Noise Reduction: Systematic removal of non-alphanumeric characters and artifacts while preserving temporal cues.

Linguistic Filtering: Used vowel-based detection and consonant-run analysis to filter out malformed tokens or non-linguistic noise.

Normalization: Scaling of valence and arousal scores to a unified range to ensure stability during model convergence.

2. Modeling Architecture
We experimented with and fine-tuned state-of-the-art Transformer models to adapt them from classification to regression:

BERT (Bidirectional Encoder Representations from Transformers): Leveraged for its deep understanding of context and inter-sentence relationships.

DeBERTa (Decoding-enhanced BERT with disentangled attention): Utilized to improve the model's grasp of relative positioning and dependency in long-form essays.

Regression Head: Replaced the standard Softmax layers with linear activation layers specifically optimized to minimize Mean Squared Error (MSE) for continuous score prediction.

3. Evaluation & Metrics

Performance was evaluated using a multi-faceted approach to ensure both mathematical accuracy and emotional alignment:

Regression Analysis: Evaluated using standard error metrics to measure the distance between predicted and ground-truth emotional scores.

Classification Mapping: For better interpretability, continuous predictions were mapped back to intensity levels to generate Confusion Matrices, measuring the model's ability to distinguish between high, neutral, and low emotional states.
