Detailed Project Proposal & Description
Project Title: Decoding Motor Imagery EEG: Traditional Machine Learning vs. Deep Learning with Explainable AI (XAI)  Student: Hyojeong Lee A18491673 (Major: Cognitive Science with a Specialization in Machine Learning)
Format: Solo Project (Non-Headset) 
Target TA for Consultation: Srinivas Ravishankar (Expertise: ML/Classification, Motor Decoding)
1. Introduction & Objective
The primary goal of this project is to explore and compare the efficacy of different pattern recognition algorithms for processing electroencephalography (EEG) signals in a Brain-Computer Interface (BCI) context. While traditional BCI pipelines rely heavily on manual feature extraction, recent advancements in deep learning offer end-to-end processing capabilities. This project will implement both a traditional machine learning pipeline and a deep learning architecture to classify 4-class motor imagery data. Furthermore, to move beyond a "black-box" approach and demonstrate a deeper understanding of the neural mechanisms, this project will employ Explainable AI (XAI) techniques to visually verify the physiological plausibility of the deep learning model's decision-making process.
2. Dataset
	•	Source: BCI Competition IV-2a Dataset (accessed via MOABB).
	•	Details: EEG recordings from 9 subjects performing 4 distinct motor imagery tasks (Left Hand, Right Hand, Feet, Tongue).
	•	Properties: 22 EEG channels, sampled at 250Hz.
3. Methodology & Implementation Plan
To rigorously evaluate the classification methods, the project is divided into two main approaches:
Approach A: Traditional Machine Learning (Baseline)
	•	Preprocessing: Epoching the continuous EEG data and applying a bandpass filter (8-30Hz) to isolate the Mu and Beta rhythms. 
	•	Feature Extraction: Implementing Common Spatial Patterns (CSP) to extract variance-based spatial features representing the distinct cortical activations of different motor tasks. 
	•	Classification: Training a Linear Discriminant Analysis (LDA) classifier. (Current baseline achieved: ~72% cross-validation accuracy).
Approach B: Deep Learning Architecture
	•	Model: Implementation of EEGNet (Lawhern et al., 2018), a compact Convolutional Neural Network (CNN) specifically designed for EEG signals.
	•	Framework: Built entirely in PyTorch. The model uses depthwise and separable convolutions to independently capture temporal and spatial features without relying on prior manual feature extraction.
	•	Training: Optimized using Cross-Entropy Loss and Adam optimizer (Current test accuracy achieved: ~74.14%).
4. Model Interpretation (Explainable AI)
A key component of this project is the critical analysis of the deep learning model to ensure it is learning meaningful neural correlates rather than noise artifacts.
	•	Saliency Maps: By computing the gradients of the output scores with respect to the input EEG trials, spatio-temporal saliency maps will be generated.
	•	Physiological Validation: The analysis will specifically look for heightened model attention around the 10-12Hz frequency range within the temporal domain, and focal importance on the sensorimotor cortex channels (e.g., C3, C4, Cz) in the spatial domain.
5. Workload Justification (Solo Project Alignment)
This project is designed to strictly adhere to the expectation that solo projects must exhibit a workload equivalent to a 2-person group. This is achieved by:
	•	Implementing and optimizing two distinct classification pipelines (Traditional ML and Deep Learning) rather than relying on a single off-the-shelf model.
	•	Writing custom PyTorch code for model architecture and training loops.
	•	Going beyond basic classification metrics by integrating advanced Saliency Map visualizations (XAI) for physiological interpretation, demonstrating significant analytical effort and a deep understanding of the course material.

