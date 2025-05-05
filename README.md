# Movie Recommendation System

## Overview
The **Movie Recommendation System** is a project designed to suggest movies to users based on their preferences. It uses a precomputed similarity matrix and a dataset of movies to provide personalized recommendations through an interactive web interface built with Streamlit. Additionally, the project includes a Jupyter Notebook for data preprocessing and model creation.

## Features
- **Personalized Recommendations**: Suggests movies similar to the one selected by the user.
- **Interactive Interface**: Users can select a movie from a dropdown and get recommendations instantly.
- **Streamlit Integration**: A lightweight and user-friendly web application framework.
- **Data Preprocessing Notebook**: A detailed Jupyter Notebook for merging, cleaning, and preparing the dataset for recommendations.

## Technologies Used
- **Programming Language**: Python
- **Libraries**: 
  - Streamlit
  - Pandas
  - NumPy
  - Scikit-learn
  - NLTK
  - Pickle
- **Data**: TMDB 5000 Movies and Credits datasets.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Movie_Recommendation_System.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Movie_Recommendation_System
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
### Streamlit Application
1. Ensure the required `.pkl` files (`movie_dict.pkl` and `similarity.pkl`) are present in the project directory.
2. Run the application:
   ```bash
   streamlit run 1.py
   ```
3. Open your browser and navigate to the URL provided by Streamlit (e.g., `http://localhost:8501`).
4. Select a movie from the dropdown menu and click the "Recommend" button to see the recommendations.

### Jupyter Notebook
1. Open the `Movie_Recomendation_System.ipynb` file in Jupyter Notebook or JupyterLab.
2. Follow the steps in the notebook to:
   - Load and preprocess the TMDB datasets.
   - Merge, clean, and transform the data.
   - Create a similarity matrix using cosine similarity.
   - Save the processed data and similarity matrix as `.pkl` files.

## Project Structure
```
Movie_Recommendation_System/
│
├── 1.py                             # Main Streamlit application file
├── Movie_Recomendation_System.ipynb # Jupyter Notebook for data preprocessing
├── tmdb_5000_movies.csv             # Movies dataset
├── tmdb_5000_credits.csv            # Credits dataset
├── movie_dict.pkl                   # Preprocessed movie dataset (dictionary format)
├── similarity.pkl                   # Precomputed similarity matrix
├── requirements.txt                 # Python dependencies
└── README.md                        # Project documentation
```

## How It Works
### Data Preprocessing
1. **Dataset Loading**: The TMDB 5000 Movies and Credits datasets are loaded into Pandas DataFrames.
2. **Data Cleaning**: Unnecessary columns are removed, missing values are handled, and duplicate entries are dropped.
3. **Feature Engineering**: 
   - Columns like `genres`, `keywords`, `cast`, and `crew` are transformed into a unified format.
   - A new `tags` column is created by combining relevant features.
4. **Vectorization**: The `tags` column is vectorized using CountVectorizer to create numerical representations.
5. **Similarity Matrix**: Cosine similarity is computed between movie vectors to identify similar movies.

### Recommendation Logic
1. When a user selects a movie, its index is retrieved from the dataset.
2. The similarity scores for the selected movie are sorted to find the top 5 most similar movies.
3. The recommendations are displayed in the Streamlit interface.

## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add feature-name"
   ```
4. Push to the branch:
   ```bash
   git push origin feature-name
   ```
5. Open a pull request.

## License
This project is licensed under the [MIT License](LICENSE).

## Acknowledgments
- Thanks to the open-source community for providing useful libraries and tools.
- TMDB for providing the datasets used in this project.
- Inspiration from popular recommendation systems like Netflix and Amazon.