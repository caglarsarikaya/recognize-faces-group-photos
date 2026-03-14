```markdown
# Face Detection and Recognition System

A Python-based system that identifies specific individuals in photos using reference face embeddings and deep learning models.

## Dataset Source

Test and training images are sourced from the [Friends Character Face Recognition Dataset](https://www.kaggle.com/datasets/amiralikalbasi/images-of-friends-character-for-face-recognition) on Kaggle.

---

## Project Architecture

The project uses a modular structure:

```text
face-detection/
├── main.py                # Main orchestration script
├── data_loader.py         # Handles data loading operations
├── face_processor.py      # Processes detection and recognition
├── output_manager.py      # Manages output file operations
├── face_detection/       # Face detection module (InsightFace)
├── embed_matcher/        # Embedding matching module
├── data/                  # Data storage
│   ├── photos/           # Photos to analyze
│   └── reference_faces/  # Reference faces for each person
└── output/                # Results organized by person

```

---

## Core Technology Stack

* **InsightFace**: Unified model for face detection and embedding generation.
* **OpenCV**: Image processing operations.
* **scikit-learn**: Cosine similarity calculations for matching.
* **NumPy**: Numerical and array operations.

---

## Process Flow

1. **Data Loading**: Creates embeddings from reference face images.
2. **Face Detection**: Identifies all faces within target photos.
3. **Embedding Generation**: Creates 512-dimensional feature vectors for detected faces.
4. **Similarity Matching**: Compares embeddings using cosine similarity.
5. **Result Organization**: Moves photos into folders based on recognized identities.

---

## Folder Structure

### Data Organization

* **data/photos/**: Input images for analysis (.jpg, .png, .bmp).
* **data/reference_faces/**: Subfolders named after individuals (e.g., `Joey/`) containing their reference photos.

### Output Structure

* **output/**: Photos are copied into subfolders corresponding to the recognized person. One photo may appear in multiple folders if several recognized individuals are present.

---

## Installation & Setup

1. **Clone the project**
```bash
git clone <repository-url>
cd face-recognition-group-photos

```


2. **Create and activate a virtual environment**
* **Windows:** `python -m venv venv` then `venv\Scripts\activate`
* **macOS/Linux:** `python -m venv venv` then `source venv/bin/activate`


3. **Install dependencies**
```bash
pip install -r requirements.txt

```



---

## How to Run

1. Add images to `data/photos/` and `data/reference_faces/[PersonName]/`.
2. Execute the system:
```bash
python main.py

```


3. View results in the `output/` folder.

---

## Configuration

The matching sensitivity can be adjusted in `main.py`:

```python
face_processor = FaceProcessor(reference_db, threshold=0.5)

```

* **Higher threshold (0.7-0.9)**: Stricter matching, fewer false positives.
* **Lower threshold (0.3-0.5)**: More lenient matching, higher match frequency.

---

## Troubleshooting

* **No faces detected**: Ensure reference images are clear and front-facing.
* **Low accuracy**: Increase the number of reference images per person.
* **Memory issues**: Reduce image resolution or process smaller batches.

```

Would you like me to create a summary of the required Python libraries for the `requirements.txt` file?

```
