# AI-Powered Ultrasound Image Analysis (DETR + Hugging Face)

This repository contains a code-along tutorial and supporting files for applying object detection to fetal ultrasound images using Hugging Face's object detection models. The main notebook is an educational walkthrough that downloads a pretrained DETR detector model, prepares a small ultrasound dataset, fine-tunes the detector, and visualizes predictions vs. ground truth.

Resources
- DataCamp code-along tutorial: https://www.datacamp.com/code-along/analyzing-ultrasound-data-with-hugging-face 
- Dataset (Zenodo): Maternal fetal ultrasound planes from low-resource imaging settings in five African countries — https://doi.org/10.5281/zenodo.7540448

Dataset citation
Carla Sendra-Balcells, Víctor M. Campello, Jordina Torrents-Barrena, Yahya Ali Ahmed, Mustafa Elattar, Benard Ohene-Botwe, Pempho Nyangulu, William Stones, Mohammed Ammar, Lamya Nawal Benamer, Harriet Nalubega Kisembo, Senai Goitom Sereke, Sikolia Z. Wanyonyi, Marleen Temmerman, Eduard Gratacós, Elisenda Bonet, Elisenda Eixarch, Kamil Mikolaj, Martin Grønnebæk Tolsgaard, & Karim Lekadir. (2023). Maternal fetal ultrasound planes from low-resource imaging settings in five African countries (v1.0) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.7540448

License & attribution
- The dataset on Zenodo is published under the Creative Commons Attribution 4.0 International (CC BY 4.0) license — please follow the dataset license when publishing results.

Getting started
1. Create a Python environment (recommended: Python 3.8+). Example using venv:

```bash
python -m venv .venv
source .venv/bin/activate  # or .venv\\Scripts\\activate on Windows
pip install -r requirements.txt  # or run the pip command shown below
```

2. Install minimal dependencies used in the notebook:

```bash
pip install transformers datasets torchvision pycocotools matplotlib scipy pillow
```

3. Open the notebook `huggingface_ultrasound_tutorial_final.ipynb` and follow the cells.

Dataset layout
- This repository keeps the annotation JSON files in `dataset/train_dataset/` and `dataset/test_dataset/`.
- The PNG image files are not committed to git to keep the repo lightweight.
- To run the notebook, download the dataset from Zenodo, then reconstruct the expected folder structure locally by using the `image_filename` values from the JSON annotations to place the image files under `dataset/train_dataset/` and `dataset/test_dataset/`.
- The notebook reads each annotation file, matches the `image_filename` field to the corresponding local `.png` image, and then loads the sample for visualization and training.

A CSV `African_planes_database.csv` is included in this repository for convenience.

Notes for instructors and students
- This repo is intended for educational use and demonstrates the end-to-end flow for fine-tuning an object detector on a small medical imaging dataset. It is not intended to be a production training pipeline.
- Check the dataset terms and respect patient privacy and licensing requirements when sharing or publishing results.


