# Multi-modal Context-based Sarcasm Detection Using AI

## Project Overview
This project aims to explore the potential of AI in detecting sarcasm, which is a complex form of verbal irony. Sarcasm is often characterized by statements that convey the opposite of their literal meaning, commonly used for humor or passive aggression. The research introduces an innovative framework that combines ensemble methods with early and late fusion techniques to detect sarcasm using multi-modal data inputs including text, audio, and visual data.

## Objectives
- To develop a framework that can accurately detect sarcasm using multi-modal data.
- To enhance the detection accuracy by employing ensemble techniques combined with advanced feature extraction models.
- To investigate whether sarcasm is a speaker-dependent or speaker-independent phenomenon.

## Key Contributions
- **VGGish Transfer Learning for Audio Data**: Utilizes advanced audio feature extraction techniques, leveraging the VGGish model to generate audio embeddings that significantly outperform traditional methods.
- **State-of-the-Art Facial Expression Recognition**: Employs a top-performing model trained on the Facial Expression Recognition (FER) dataset to extract subtle emotional cues from visual data.
- **Multimodal Fusion Ensemble Framework (MFEF)**: A novel architecture that integrates ensemble models with fusion techniques to improve sarcasm detection.

## Framework
The proposed architecture integrates textual, audio, and visual inputs to detect sarcasm in conversational data. The framework includes:
1. **Textual Model**: Utilizes a case-sensitive BERT model to generate text embeddings, which capture contextual information and speaker nuances.
2. **Audio Model**: Uses the VGGish model to extract robust audio features, capturing the tonal complexities associated with sarcasm.
3. **Visual Model**: Extracts facial embeddings using a VGG-FER model, focusing on expressions that typically accompany sarcastic utterances.
4. **Early Fusion Model**: Concatenates embeddings from the textual, audio, and visual models to create a comprehensive feature set for sarcasm detection.
5. **Late Fusion Model**: Combines predictions from individual modalities using a logistic regression model.
6. **Ensemble Model**: Averages probabilities from the Early and Late Fusion models, enhancing the overall performance.

## Experimental Results
The framework was tested under two experimental setups: speaker-dependent and speaker-independent sarcasm detection. The Ensemble model achieved the highest performance, demonstrating a 10% improvement over existing methods in sarcasm detection.

| Model          | Speaker-Dependent F1 Score | Speaker-Independent F1 Score |
|----------------|----------------------------|-----------------------------|
| Textual        | 0.81                       | 0.75                        |
| Audio          | 0.73                       | 0.70                        |
| Visual         | 0.57                       | 0.58                        |
| Early Fusion   | 0.87                       | 0.85                        |
| Late Fusion    | 0.83                       | 0.75                        |
| Ensemble       | 0.89                       | 0.85                        |

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Vijeth-Rai/multimodal-sarcasm-detection.git
   cd multimodal-sarcasm-detection
   ```

2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Data Preparation**: Place your text, audio, and video data in the appropriate directories as specified in the configuration file.

2. **Training the Models**: Run the training scripts for each modality:
   ```bash
   python train_text_model.py
   python train_audio_model.py
   python train_visual_model.py
   ```

3. **Fusion and Ensemble**: Combine the modality outputs and run the ensemble model:
   ```bash
   python run_ensemble.py
   ```

4. **Evaluation**: Use the evaluation scripts to measure the performance:
   ```bash
   python evaluate.py
   ```

## Datasets
This research utilizes the MUStARD++ dataset, a multimodal dataset designed for sarcasm detection. The dataset includes text, audio, and visual data, providing a comprehensive foundation for training and evaluating the models.

## Future Work
- Expanding the dataset to reduce the margin of error and improve model robustness.
- Exploring real-time sarcasm detection capabilities.
- Investigating new multi-modal transfer learning models trained on larger classification datasets.

## Citation
If you use this code or dataset, please cite:
```
@article{rai2024multimodal,
  title={When words are not enough: Multi-modal context-based sarcasm detection using AI},
  author={Vijeth Rai},
  journal={MSc Data Science and Artificial Intelligence},
  year={2024}
}
```

## Contact
For questions or feedback, please contact Vijeth Rai at [vijethrai98@gmail.com].

---

This README provides a comprehensive overview of the project, installation instructions, and usage guidelines to help you get started with multi-modal sarcasm detection using AI.
