WAVESAGE: Wavelet and SHAP Empowered Explainable AI for EEG Micro-Event Localization
📌 Project Overview
WAVESAGE is an advanced Explainable AI (XAI) framework designed to bridge the gap between clinical neurological diagnosis and deep learning. The project achieved full paper acceptance at EMBC 2026. It provides a validated, clinically relevant explainability framework ready for Retrospective Clinical Decision Support, aligning with UN SDG 3 (Good Health and Well-Being) by democratizing transparent and accurate neurological diagnostics.

🏥 The Clinical Problem vs. The AI Black Box
The Clinical Need: Neurologists rely on identifying precise micro-events, which are transient spikes lasting less than 2 seconds, to formulate diagnoses.

The AI Limitation: While deep learning models offer accurate classifications for data windows, they act as "black boxes" and fail to provide the exact localization of these micro-events.

The Failure of Time-Series Explainability: Standard XAI methods treat time-series data like static pixels, assuming feature independence. Because neighboring time samples are highly correlated, this approach causes "temporal smearing," spreading importance across time and failing to isolate irregular, transient physiological events.

⚙️ System Architecture & Process Flow
The WAVESAGE pipeline processes data through six distinct stages to achieve accurate micro-event localization:

Stage 1 - Input EEG: Ingests raw EEG data utilizing 400 samples per 2-second window.

Stage 2 - Wavelet Decomposition: Applies a Daubechies 4 (db4) wavelet transformation at level 7.

Stage 3 - CNN Classifier: Utilizes Conv1D layers followed by Global Average Pooling for classification.

Stage 4 - SHAP Attribution: Generates feature attribution scores using SHAP.

Stage 5 - Reconstructed Signals: Reconstructs the signals focusing on the D7-D3 detail coefficients.

Stage 6 - Final Localization: Employs majority voting to pinpoint the final localization of the micro-event.

📊 Quantitative Performance
WAVESAGE was benchmarked against clinical ground truth data on the NMT-Events dataset and uniquely balances precision and recall. It achieved the highest overall scores compared to baseline models like Grad-CAM, standard SHAP, and SleepXAI:

Precision: 58.0%

Recall: 79.0%

IoU (Intersection over Union): 49.7%

F1-Score: 64.2%

🛠️ Toolchain & Development Effort
Primary Frameworks: Built using PyTorch, MNE-Python, SHAP, and Captum.

Benchmarking Setup: The team built and integrated 11 separate XAI baselines from scratch (including LIME, Integrated Gradients, Deep Taylor Decomposition, Smooth-Grad, RISE, and Layer-CAM) to thoroughly validate WAVESAGE on clinical data.


🚀 Installation & Usage
Please note that the WAVESAGE system consists of modular components. The specific terminal commands required to install dependencies and run this project are mentioned separately in the respective README files located within the Backend and Frontend directories. Navigate to those folders for detailed execution instructions.
