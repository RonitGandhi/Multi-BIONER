Project Title: Multi-Task Learning for Biomedical Named Entity Recognition (BioNER)
with Cross-Sharing Knowledge
Project Description
Biomedical Named Entity Recognition (BioNER) is a crucial NLP task focused on identifying
and categorizing biomedical entities—such as proteins, diseases, drugs, and chemicals—in
scientific literature. Accurate BioNER is essential for enhancing information retrieval,
supporting clinical decision-making, and advancing biomedical research. However, BioNER
is challenging due to the diversity and overlap of biomedical entities, as well as the
complexity of the language used in biomedical texts.
Traditional single-task models often struggle to generalize across diTerent entity types, as
they cannot leverage knowledge shared between tasks. This limitation can lead to lower
performance, especially when handling overlapping domains within biomedical text.
This project proposes a multi-task learning approach to improve BioNER by enabling crosssharing
of knowledge between entity types. Multi-task learning allows for a single model to
learn multiple tasks simultaneously by using a shared encoder, which captures general
features, along with task-specific layers for recognizing each entity type. This approach is
inspired by the research paper "Multitask Learning for Biomedical Named Entity Recognition
with Cross-Sharing Structure," which explores the benefits of shared representations in
BioNER.
By applying multi-task learning with shared and task-specific layers, this project aims to
build a model that achieves greater accuracy across diverse biomedical entities. The
expected outcome is a BioNER model that more eTectively handles the complexities of
biomedical language, enabling reliable information extraction for use in clinical and research
applications.
NLP Task: The primary NLP task is named entity recognition (NER) with a multi-task learning
framework. By defining distinct but related tasks (e.g., recognizing proteins, diseases,
drugs), the model can benefit from shared knowledge representations that improve
accuracy across all entity types.
Dataset(s):
- Primary Datasets: The project will use biomedical datasets such as BioCreative (for
gene/protein mentions), NCBI Disease Corpus (for disease names), BC5CDR (for
chemicals and diseases), and GENIA (for proteins, cells, and DNA). These datasets provide
labeled examples of various biomedical entities, which will be mapped to a standardized
format (BIO tagging) to ensure consistency.
- Data Preprocessing : The datasets will be tokenized, and labels aligned with tokens to
ensure compatibility with transformer-based models. Additionally, we’ll standardize entity
tags across datasets for consistent multi-task learning.
Prospective Models:
- Baseline Model : A single-task BioBERT or BERT model trained on each entity type
separately, serving as a performance benchmark.
- Proposed Multi-Task Model : The core architecture will consist of a shared transformerbased
encoder (e.g., BioBERT or BERT) with task-specific heads for each entity type (e.g.,
proteins, diseases, chemicals). Each task head is a linear classifier that predicts entity tags
specific to that biomedical entity type.
Plan for Training Models:
- Training Approach : The multi-task model will be fine-tuned with a shared encoder and
individual task heads, using cross-entropy loss for each head. The model will be trained on
labeled data from all tasks simultaneously, shuTling between batches from each dataset to
train each task head iteratively. The loss function will be a weighted sum of task-specific
losses, with hyperparameter tuning to balance these losses.
- Size of Test Set : A 10-15% split from each dataset will be reserved for the test set, ensuring
robust evaluation.
- Training Method : Fine-tuning will be performed using PyTorch and the Hugging Face
Transformers library, starting with BioBERT or BERT weights.
Team Number: 17 Team Members: Ronit Gandhi (rg1225), Vanshika Gurbani (vg460)
Metric for Measuring Quality of Model:
- Evaluation Metrics : Precision, Recall, and F1-score will be computed for each entity type
to assess model performance. These metrics will allow us to measure how well the model
generalizes across entity types and to observe improvements from the multi-task learning
approach.
- Comparison : We will compare the multi-task model’s performance against the singletask
baseline to determine if cross-task knowledge sharing improves BioNER.
