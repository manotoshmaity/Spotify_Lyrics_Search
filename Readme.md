🎵 Spotify Lyric Search & Artist Prediction

This project uses machine learning and NLP to:

Predict the artist from a given lyrics snippet using a TensorFlow neural network

Predict the most likely song by that artist using TF-IDF cosine similarity

It is trained on a subset of the Spotify Million Song Dataset containing lyrics.

📌 Features

Artist classification using TensorFlow / Keras

Song retrieval using TF-IDF + Cosine Similarity

Handles large lyric datasets efficiently

Interactive lyrics input from the user

📂 Dataset

The notebook expects a CSV file with the following columns:

artist, song, text


Example dataset file:

Spotify Million Song Dataset_exported.csv


⚠️ Important
Update the dataset path if you are not using Google Colab:

df = pd.read_csv(
    "path/to/Spotify Million Song Dataset_exported.csv",
    usecols=["artist", "song", "text"]
)

🛠 Installation
1️⃣ Create a Virtual Environment (Recommended)
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows

2️⃣ Install Required Libraries
pip install pandas scikit-learn tensorflow


If you are using TensorFlow with GPU:

pip install tensorflow-gpu

📦 Dependencies
Library	Purpose
pandas	Data loading & preprocessing
scikit-learn	TF-IDF, cosine similarity, label encoding
tensorflow	Deep learning model
numpy	Numerical operations (TensorFlow dependency)
🚀 How It Works
🔹 Step 1: Data Preprocessing

Load lyrics dataset

Drop missing lyrics

Sample 50,000 songs for faster training

Encode artists using LabelEncoder

🔹 Step 2: Artist Prediction Model

Text vectorization using TextVectorization

Neural network with:

Embedding layer

Global average pooling

Dense layers

Output: Probability distribution over artists

🔹 Step 3: Song Prediction

TF-IDF vectorization of lyrics

Cosine similarity search within predicted artist songs

Returns the most similar song

▶️ Usage
Run the Notebook
jupyter notebook Spotify_Lyric_Search.ipynb

Predict Artist & Song

At the end of the notebook, run:

predict_artist_song()


Then enter a lyrics snippet:

Enter lyrics snippet: hello it's me I was wondering if after all these years...

Output Example
Predicted Artist: Adele
Predicted Song: Hello

⚙️ Training Configuration

Max tokens: 30,000

Sequence length: 200

Embedding size: 64

Epochs: 5

Batch size: 128

You can adjust these values in the notebook for better accuracy.

📈 Future Improvements

Save & load trained model

Add top-k song predictions

Web interface (Flask / Streamlit)

GPU optimization

Better lyric cleaning & tokenization

🧠 Author

Built for learning NLP + Deep Learning with real-world music data 🎶