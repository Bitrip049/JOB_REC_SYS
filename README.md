Job Recommendation System (Job_REC_SYS)
=======================================

This project implements a Job Recommendation System for the AUTECHJOB platform. It uses a hybrid approach, combining content-based filtering and collaborative filtering, to recommend relevant job listings to users.

---

Features
--------
- Content-Based Filtering:
  - Extracts textual similarity using TF-IDF and cosine similarity based on job descriptions.
- Collaborative Filtering:
  - Uses user-job interactions and Singular Value Decomposition (SVD) to recommend jobs.
- Hybrid Recommendations:
  - Combines content-based and collaborative filtering with configurable weights for personalized recommendations.
- Data Cleaning:
  - Handles missing data, duplicate entries, and removes HTML tags from job descriptions.
- Evaluation:
  - Measures recommendation performance using Precision, Recall, and F1-Score.


---

Setup Instructions
------------------

### Prerequisites
1. Python 3.9 or higher.
2. MySQL installed and running with the `AU_TECH_JOBS` database.
3. Ensure you have the `pip` package manager installed.

---

Step-by-Step Setup
------------------
1. Clone the Repository:

git clone https://github.com/your-username/Job_REC_SYS.git cd Job_REC_SYS

2. Set Up the Environment:
- Create and activate a virtual environment:
  - On Linux/macOS:
    ```
    python3 -m venv venv
    source venv/bin/activate
    ```
  - On Windows:
    ```
    python -m venv venv
    venv\Scripts\activate
    ```
- Install required packages:
  ```
  pip install -r requirements.txt
  ```

3. Set Up MySQL Database:
- Create the `AU_TECH_JOBS` database and import the SQL dump:
  ```
  mysql -u root -p
  CREATE DATABASE AU_TECH_JOBS;
  exit
  mysql -u root -p AU_TECH_JOBS < data/au_tech_jobs.sql
  ```

4. Set Up Environment Variables:
- Copy the example `.env.example` file and fill in the required credentials:
  ```
  cp .env.example .env
  ```
- Example:
  ```
  MYSQL_HOST=localhost
  MYSQL_USER=root
  MYSQL_PASSWORD=root
  MYSQL_DATABASE=AU_TECH_JOBS
  ```

5. Run the Project:
- Execute the main script:
  ```
  python main_script.py
  ```

6. (Optional) Run Jupyter Notebook:
- Launch the notebook for testing or experimentation:
  ```
  jupyter notebook MAIN.ipynb
  ```

---

Usage
-----
- The system connects to a MySQL database, preprocesses job and user data, and generates personalized recommendations.
- Outputs:
- Cleaned data exported to:
 - `data/filtered_df_backup.csv`
 - `data/database_export.xlsx`
- Recommendations displayed in the terminal or notebook.
- Adjust weights for hybrid recommendations in the script (e.g., `alpha = 0.8`).

---

Technologies Used
-----------------
1. Python:
- Core programming language.
- Libraries: pandas, numpy, scikit-learn, beautifulsoup4, mysql-connector-python, python-dotenv.
2. MySQL:
- Stores job and user interaction data.
3. Jupyter Notebook:
- For experimentation and analysis.
4. TF-IDF:
- Text-based similarity measurement for content-based recommendations.
5. SVD:
- Collaborative filtering using matrix factorization.

---

Environment Variables
---------------------
Create a `.env` file in the root directory with the following values:
MYSQL_HOST=localhost MYSQL_USER=root MYSQL_PASSWORD=root MYSQL_DATABASE=AU_TECH_JOBS



---

Files to Note
-------------
1. `au_tech_jobs.sql`:
   - MySQL database schema and data dump.
2. `requirements.txt`:
   - Python dependencies required to run the project.
3. `MAIN.ipynb`:
   - Jupyter Notebook for recommendation system development and testing.

---

Future Enhancements
-------------------
1. Scale to handle larger datasets using PySpark.
2. Implement real-time recommendations with an API (e.g., Flask).
3. Add solutions for the cold-start problem:
   - Recommend popular jobs for new users.
   - Suggest jobs based on their categories or skills for new jobs.
4. Include advanced models like neural collaborative filtering.

---

Contact
-------
For queries or support:
- Author: Bitrip Pathak
- Email: Bitrip.Pathak@outlook.com
