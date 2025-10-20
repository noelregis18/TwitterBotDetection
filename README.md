# Twitter Bot Detection

## Overview
This project aims to detect and distinguish between human and bot Twitter accounts using machine learning techniques. By analyzing various features extracted from Twitter data, the model can classify accounts with high accuracy.

## Dataset
The training data is sourced from the Botometer repository:
- [Botometer Bot Repository Datasets](https://botometer.iuni.iu.edu/bot-repository/datasets.html)

Additional data used in this project includes:
- Twitter User Object data: [Twitter User Object Documentation](https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/user-object)
- Twitter Tweet Object data: [Twitter Tweet Object Documentation](https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/tweet-object)
- Cresci-rtbust-2019 dataset for bot detection

## Project Structure

### Data Files
- **Raw_data_Files/**
  - `Tweet_Data.csv` - Raw tweet data
  - `User_names.csv` - Twitter usernames
  - `myInput.csv` - Input data
  - `output_got.csv` - Output data from Twitter API

- **Training_Data_Files/**
  - `Content_Data.csv` - Features extracted from tweet content
  - `Graph_Data.csv` - Features extracted from user graph relationships
  - `TrainingData.csv` - Final merged features used for model training

- **cresci-rtbust-2019/**
  - Dataset files for bot detection research

### Code Files
- **Python_Files/**
  - `MergingTrainingData.ipynb` - Notebook for merging content and graph features
  - `RVMTrainingModel.ipynb` - Notebook for training and evaluating the bot detection model

## Features
The model uses a combination of features extracted from:

1. **Content Features**:
   - Number of tweets
   - URL ratio in tweets
   - User mention ratio

2. **Graph Features**:
   - Follower/Following relationships
   - Account verification status
   - Account activity metrics (favorites, listed count)
   - Account age

## Model Implementation
After experimenting with several machine learning algorithms, the Relevance Vector Machine (RVM) with a linear kernel was selected as the best performing model:

- **Algorithm**: Relevance Vector Machine (RVM)
- **Kernel**: Linear
- **Testing Accuracy**: 81.25%

The implementation uses the `sklearn_rvm` library and follows these steps:
1. Data preprocessing and normalization
2. Feature selection
3. Model training with RVM
4. Performance evaluation

## Results
The RVM model achieved 81.25% accuracy in distinguishing between human and bot accounts, outperforming other tested algorithms including:
- Naive Bayes
- Support Vector Machines
- Decision Trees

## Usage

### Requirements
- Python 3.x
- pandas
- numpy
- scikit-learn
- sklearn_rvm

### Running the Model
1. Ensure all required data files are in the appropriate directories
2. Run the `MergingTrainingData.ipynb` notebook to prepare the training data
3. Run the `RVMTrainingModel.ipynb` notebook to train and evaluate the model

## Future Work
- Incorporate more sophisticated features from tweet text analysis
- Experiment with deep learning approaches
- Develop a real-time bot detection system

## License
This project is available for academic and research purposes.



