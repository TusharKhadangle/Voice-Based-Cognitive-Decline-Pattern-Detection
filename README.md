# Voice-Based-Cognitive-Decline-Pattern-Detection

Project Overview
This project aims to detect early signs of cognitive decline using voice analysis. By analyzing speech patterns and acoustic features from audio clips, the pipeline identifies markers such as hesitations, pauses, and filler words that correlate with cognitive stress. The system uses unsupervised machine learning to flag high-risk samples, providing a non-invasive tool for preliminary screening.

Key Features Extracted
Linguistic Features

Filler Word Ratio: Frequency of disfluencies like "uh," "um," and "..." (strong indicator of cognitive effort).

Hesitation Count: Total interruptions in speech flow.

Word Recall Metrics: Repetitions, pronoun overuse, and vocabulary diversity (unique_word_ratio).

Acoustic Features

Pause Duration Ratio: Time spent in silence between words.

Spectral Centroid Variance: Measures pitch stability (abnormal fluctuations indicate stress).

Speech Rate: Words per second and sentence complexity.

Methodology
1. Audio Preprocessing
Noise Reduction: Librosa for audio normalization and background noise removal.

Transcription: OpenAI Whisper model to convert speech to text (supports hesitations like "uh/um").

2. Machine Learning Pipeline
Anomaly Detection:

Algorithm: Isolation Forest (unsupervised).

Why? Effective for small datasets; flags outliers without labeled training data.

Key Features: Weighted filler_word_ratio, hesitation_count, and pause_duration_ratio.

Clustering:

Algorithm: K-means (2 clusters).

Why? Separates fluent vs. disfluent speech patterns.

Visualization: PCA reduces features to 2D for interpretability.

3. Risk Scoring
Scores normalized to 0–100 (higher = higher risk).

Threshold: Samples scoring >70 flagged for clinical review.

Key Findings
High-Risk Sample: SteveLawrence_15.wav scored 100/100 due to 18 hesitations and prolonged pauses.

Cluster Analysis:

Cluster 0: Low hesitations, fluent speech (e.g., JackHanna_10.wav).

Cluster 1: Disfluent speech with frequent pauses (e.g., RobinWilliams_0.wav).

Critical Features: filler_word_ratio and pause_duration_ratio had the highest clinical relevance.
