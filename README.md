# Disaster Response Pipeline Project

I applied the data pipeline skills learned to analyze disaster data from Figure Eight to build a model for an API that classifies disaster messages. I built a machine learning pipeline to categorize emergency messages based on the needs communicated by the sender.

### Table of Contents

1.  [Project Overview](#ProjectOverview)
2.  [Importance and Impact](#ImportanceAndImpact)
3.  [Instructions](#instructions)
4. [File Descriptions](#files)
5. [Licensing, Authors, and Acknowledgements](#licensing)

# Project Overview
This project is designed to support emergency operators during disasters, such as earthquakes or tsunamis, by providing a web application that classifies disaster-related text messages into various categories. The application uses a machine learning (ML) model to automatically categorize incoming messages, ensuring that each message is directed to the appropriate response team or entity.

# Importance and Impact
During a disaster, communication channels are often overwhelmed with a high volume of distress messages. This application plays a crucial role in streamlining the response process by quickly and accurately categorizing messages based on the specific needs they communicate, such as requests for medical aid, search and rescue, or supplies. By automating this process, the application helps emergency responders prioritize tasks more efficiently, ensuring that critical resources are allocated where they are needed most.

For instance, in the aftermath of a natural disaster, the app can instantly classify messages from affected individuals, allowing response teams to immediately focus on life-saving operations. This not only speeds up the response time but also reduces the chances of human error in manual message sorting, potentially saving lives and reducing the impact of the disaster on the affected population.


### Instructions:<a name="instructions"></a>
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/

### File Descriptions:<a name="files"></a>

`process_data.py`: A ETL Pipeline that 
- loads the `messages` and `categories datasets`
- merges the two datasets
- cleans the data
- stores it in a SQLite database

`train_classifier.py`: A Machine Learning Pipeline that
- loads data from the SQLite database
- splits the dataset into training and test sets
- builds a text processing and machine learning pipeline
- trains and tunes a model using GridSearchCV
- outputs results on the test set
- exports the final model as a pickle file

`run.py`: A Flask Web App that visualizes the results
