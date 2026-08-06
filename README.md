# Important Note
Please configure the path for the dataset as required.
If you just want to run the saved models, please refer to section 19.2


# DrDos-Attack-Detection-in-Network-Security
Benchmark of 11 ML/DL models on 33,925 DrDoS_DNS flows. Exposes proxy-feature bias under unidirectional monitoring and highlights Random Forest as the top real-time detector (1.0 F1, ~10 µs latency). Features 22 reproducible pipelines and SMOTE imbalance handling.

# Executive Overview: DrDoS_DNS Attack Detection Benchmark Analysis

## Executive Overview
Evaluating 11 machine learning, unsupervised, and deep learning algorithms across a 33,925-flow network dataset, this study identifies a critical flaw in DrDoS_DNS attack benchmark evaluations. Headline detection performance across all models (macro F1 ≥ 0.9966) relies on a backward-traffic proxy feature unique to full-visibility bidirectional monitoring. Removing this proxy signal to simulate real-world unidirectional taps reveals that tree- and instance-based models retain perfect accuracy, while deep learning performance degrades and unsupervised clustering collapses to chance level (~0.49 macro F1).

## Key Focus Areas
* **Proxy-Feature Vulnerability Analysis:** Proves that standard high-performing benchmark scores stem from backward-direction flow artifacts caused by IP spoofing rather than robust attack signature recognition.
* **Algorithmic Resilience Benchmarking:** Demonstrates that Decision Trees, Random Forests, and K-Nearest Neighbors sustain flawless classification (1.0000 macro F1) without proxy signals, whereas linear, deep learning, and clustering models experience severe degradation.
* **Operational Feasibility & Latency Profiling:** Quantifies per-flow inference times across two orders of magnitude (0.13 µs to 46.26 µs), highlighting Random Forest as the superior real-time candidate balancing robust accuracy with minimal latency (10.74–14.33 µs/flow).
* **Class Imbalance & Pipeline Verification:** Addresses an extreme 29:1 attack-to-benign flow ratio via stratified splitting, redundancy filtering, and SMOTE oversampling while verifying complete artifact reproducibility across 22 saved pipelines.

## Purpose & Audience
Targeted at network security architects and intrusion detection researchers, this report enables data-driven decisions on model deployment by balancing real-time inference latency constraints against feature-availability constraints in operational network environments.
