
 
FAST — NATIONAL UNIVERSITY OF
COMPUTER AND EMERGING SCIENCES
FAST School of Computing  ·  Karachi Campus
Department of Artificial Intelligence & Data Science
AL-2001  ·  PROGRAMMING FOR ARTIFICIAL INTELLIGENCE
Laboratory  ·  Fall 2026
PROJECT REPORT
«  GlucoGuide AI»
Semester Lab Project  ·  Weightage 2 marks

	Student Name	Roll Number	Section
Leader	 Syeda Haram Waqar	 25K-0116	 BAI-3A
Member 2	 none	 	 
Member 3	 none	 	 

Course	AL-2001 — Programming for Artificial Intelligence (Laboratory)
Programme / Semester	BS Artificial Intelligence  ·  3rd Semester
Session	Fall 2026
Lab Instructor	Khadeejah Ashraf
Specialisation Track	Track A — Text / NLP  ☐            
GitHub Repository	 https://github.com/25k-0116Haram/GlucoGuide-AI
Date of Submission	 Nov 23,2026

 
Table of Contents
Page numbers below match this blank template. Update them once your report is written — in Word this table can be regenerated from the headings via References ▸ Table of Contents.
Chapter	Title	Page
	Declaration and Contribution Statement	2
1	Introduction	3
2	Problem Statement and Requirements	4
3	System Design and Architecture	5
4	Implementation	8
5	Dataset	12
6	Results and Analysis	14
7	Testing, Error Handling and Ethics	18
8	Individual Contributions and Conclusion	19
	Appendix A — Setup and Execution	21

Declaration and Contribution Statement
We declare that the work presented in this report is our own, that all external sources — code, datasets, APIs, tutorials and AI assistance — have been acknowledged, and that each of us is able to explain the portion of the work attributed to us below.
Member	Roll Number	Principal contribution (one line)	Share	Signature
 SYEDA HARAM Waqar	 25k-0116	 Project design, Python implementation, NLP assistant, risk assessment, data visualization and documentation	100% 	 Haram 

Note: the shares stated here are read against the commit history of your repository and against the detailed table in Chapter 8. Marks are awarded individually.
 
1.  Introduction
1.1  Overview
GlucoGuide AI is a Python-based Diabetes Awareness and Risk Education System designed to provide basic information about diabetes and help users understand diabetes-related risk factors. The system is developed for individuals who want to learn about diabetes, its common symptoms, types, and prevention.
The system provides four main features: an NLP-based Health Assistant, Diabetes Risk Awareness, Health Information, and Data Visualization. The Health Assistant uses TF-IDF and Cosine Similarity to match users' questions with relevant answers from a predefined question-answer dataset. The Risk Awareness module collects the user's age and responses about common symptoms and reports the number of selected factors. The Health Information module provides educational content about diabetes, while the visualization module displays graphs related to diabetes class, age, and gender.
The project also uses the UCI Early Stage Diabetes Risk Prediction dataset to train and compare two machine learning models: Logistic Regression and Decision Tree. Overall, GlucoGuide AI aims to support diabetes awareness and education. It is an educational tool and does not provide medical diagnosis or treatment.




1.2  Objectives and Scope
#	Objective	Achieved?
1	 
	Develop an NLP-based Health Assistant using TF-IDF and Cosine Similarity to answer diabetes-related questions.
	yes
2	 
	Provide educational information about diabetes, including its types, common symptoms, and prevention.
	yes
3	 
	Develop a Diabetes Risk Awareness module that collects user age and symptom responses and displays the number of reported factors.
	yes
4	 
Analyze the UCI diabetes dataset through data visualization and train and compare Logistic Regression and Decision Tree models.
	yes

GlucoGuide AI does not provide medical diagnosis, prescribe treatment, or replace professional medical advice. Its risk awareness module only counts self-reported factors and is not a clinical risk score. The NLP assistant is limited to its predefined question-answer dataset, while machine learning results depend on the available dataset.


2.  Problem Statement and Requirements
Problem Statement
People who want to learn about diabetes may find it difficult to get basic information about its symptoms, types, and prevention from different sources. Searching for answers to simple questions can take time, and information may not always be easy to understand. People may also be unsure about which diabetes-related symptoms or factors they should pay attention to.
For example, a person experiencing frequent thirst or weakness may want to learn whether these are common diabetes-related symptoms and where to find basic information. Without a simple educational system, the person may need to search through multiple sources separately. GlucoGuide AI addresses this problem by providing a Health Assistant that matches questions with predefined answers, a Health Information section, and a Risk Awareness module that collects responses about selected symptoms and reports the number of factors. It also presents dataset visualizations and machine learning analysis for educational purposes.




Type	Requirement
Functional	 
he system shall allow users to ask diabetes-related questions and provide relevant answers using TF-IDF and Cosine Similarity.

Functional	 
The system shall provide diabetes health information, collect age and responses to seven listed symptoms or factors, and display the number of reported factors.

Non-functional	 
The system should provide a simple, menu-based interface with clear prompts and understandable outputs.

Non-functional	 
The system must clearly inform users that its risk awareness feature is educational and does not provide medical diagnosis or treatment.



3.  System Design and Architecture
3.1  Overall Architecture
GlucoGuide AI consists of different modules that work together to provide diabetes awareness and educational information. The system takes input from two main sources: the user and the diabetes dataset. The user can enter questions in the Health Assistant, provide age and symptom responses in the Risk Awareness module, or select an option from the Health Information menu. The dataset is loaded from a CSV file, cleaned, encoded, and prepared for machine learning. Logistic Regression and Decision Tree models are then trained and evaluated, while visualizations are generated to show dataset information. Each module processes its input separately and displays the relevant result, answer, assessment summary, or graph in the Jupyter Notebook. The system displays outputs in the notebook and does not store user responses in a database.



 





Figure 3.1  System architecture


3.2  Class Design

 





Figure 3.2  Class diagram

Class	Responsibility	Inherits from	Key methods
GlucoGuideAI	Controls the main application and connects its modules.	None	__init__(), health_information(), show_charts(), run()
HealthAssistant	Matches user questions with relevant predefined answers using NLP.	None	__init__(), ask_question()
RiskAssessment	Collects age and symptom responses and displays the number of reported factors.	None	assess()
DataVisualizer	Displays diabetes dataset graphs.	None	show_class_distribution(), show_age_distribution(), show_gender_distribution()
HealthModule	Defines an abstract method for displaying module information.	ABC	display_info()
HealthInfoModule	Displays information about the diabetes health information module.	HealthModule	display_info()
VisualizationModule	Displays information about the data visualization module.	HealthModule	display_info()
RiskInfoModule	Displays information about the risk awareness module.	HealthModule	display_info()

Where the OOP principles appear. Name the class and method that demonstrates each.
Principle	Where it is demonstrated in your code
Encapsulation	The HealthAssistant class groups related data (qa_data, questions, vectorizer) and the ask_question() method together.
Inheritance	HealthInfoModule, VisualizationModule, and RiskInfoModule inherit from the HealthModule abstract class.
Method overriding	Each child class (HealthInfoModule, VisualizationModule, and RiskInfoModule) provides its own implementation of the display_info() method.
Polymorphism	The display_info() method is called on different objects through the same module.display_info() statement inside a loop.
Abstraction (ABC)	The HealthModule class inherits from ABC and defines the abstract method display_info() using @abstractmethod.

3.3  Choice of Data Structures
Collection	What it holds	Structure chosen	Why this one
qa_data	Stores diabetes-related questions and their answers.	Dictionary	A dictionary stores each question as a key and its answer as a value, making lookup easy.
questions	Stores the questions extracted from qa_data.	List	A list keeps questions in order and allows access through indexing.
question_vectors	Stores TF-IDF numerical representations of the questions.	Sparse Matrix	A sparse matrix efficiently stores numerical text vectors while saving memory.
symptoms	Stores the seven symptoms and factors used in Risk Assessment.	List	A list keeps all symptoms together and allows the program to process them one by one.
df	Stores the original diabetes dataset loaded from the CSV file.	Pandas DataFrame	A DataFrame organizes data into rows and columns, making analysis easier.
df_encoded	Stores the dataset after converting categorical values into numerical values.	Pandas DataFrame	A DataFrame keeps the encoded features organized in tabular form.
X	Stores the input features used for machine learning.	Pandas DataFrame	A DataFrame keeps feature names and values organized for model training.
y	Stores the target class values for machine learning.	Pandas Series	A Series is suitable for storing a single target column.
y_pred_lr and y_pred_dt	Store predictions made by Logistic Regression and Decision Tree.	NumPy Arrays	Arrays efficiently store predicted values for model evaluation.
.
4.  Implementation
4.1  Module Overview
File	Responsibility	Author
src/GlucoGuide.ipynb	Complete project implementation, including data loading, preprocessing, machine learning models, data visualization, NLP Health Assistant, Risk Awareness, and Health Information modules.	Syeda Haram waqar
data/raw/diabetes_data.csv	Original diabetes dataset used in the project.	Syeda Haram waqar
data/processed/diabetes_cleaned.csv	Cleaned and preprocessed diabetes dataset.	Syeda Haram waqar
data/README.md	Information about the data directory and its contents.	Syeda Haram waqar
data/raw/README.md	Information about the raw dataset.	Syeda Haram waqar
data/processed/README.md	Information about the processed dataset.	Syeda Haram waqar
docs/Proposal.pdf	Project proposal in PDF format.	Syeda Haram waqar
docs/Proposal.md	Project proposal in Markdown format.	Syeda Haram waqar
docs/Final_Report.pdf	Final project report in PDF format (Uploaded).	Syeda Haram waqar
docs/Final_Report.md	Final project report in Markdown format (Uploaded).	Syeda Haram waqar
outputs/figures/	Three project visualizations: class distribution, age distribution by diabetes class, and gender distribution.	Syeda Haram waqar
outputs/figures/README.md	Information about the project visualization files.	Syeda Haram waqar
outputs/results/	Model accuracy results, confusion matrices, classification reports, and model comparison results.	Syeda Haram waqar
outputs/results/README.md	Information about model evaluation results.	Syeda Haram waqar
README.md	Project overview, setup instructions, and usage information.	Syeda Haram waqar
requirements.txt	Python libraries and dependencies required to run the project.	Syeda Haram waqar
.gitignore	Files and folders excluded from Git tracking.	Syeda Haram waqar
		

4.2  Lab Coverage — Where Each Concept Is Used
Lab	Concept	File and function where it appears
01–02	Core Python, control flow, comprehensions	Core Python and control flow: GlucoGuide.ipynb, cells 16, 18, 19, 21, 22, 25 and 29 (variables, conditions, loops and input handling). Comprehensions: Not used.
03	Lists, tuples, dictionaries, sets	Lists: cells 16, 18, 22, 25 and 29. Dictionaries: cell 16 (qa_data) and cells 12 and 31 (model results). Tuples and sets: Not used.
04	Functions, default arguments, lambda / map / filter	Functions: health_assistant() and run_health_assistant() (cell 16), risk_assessment() (cell 18), health_information() (cell 19), ask_question() (cell 21), assess() (cells 22 and 29), show_class_distribution(), show_age_distribution() and show_gender_distribution() (cell 24), and show_charts(), health_information() and run() (cell 25). Default arguments, lambda, map and filter: Not used.
05	Classes, inheritance, encapsulation, polymorphism, ABC	Classes: HealthAssistant (cell 21), RiskAssessment (cells 22 and 29), DataVisualizer (cell 24), GlucoGuideAI (cell 25), and HealthModule, HealthInfoModule, VisualizationModule and RiskInfoModule (cell 30). Inheritance, abstract methods and method overriding: cell 30. Objects and methods: cells 21–30. Separate access modifiers/private attributes: Not used.
06	File I/O (TXT / CSV / JSON), custom exception, try / except	CSV reading: pd.read_csv() in cells 0 and 35. CSV writing: df.to_csv() in cell 4. Try/except: cell 29, inside RiskAssessment.assess(). TXT/JSON handling and custom exceptions: Not used.
06	Web API with requests, status check, local cache	Not used. The project loads a CSV from a GitHub URL using pd.read_csv() in cell 0, but does not implement a requests-based Web API, status check or local API cache.
07	NumPy array, slicing / masking, broadcasting, axis aggregation	NumPy is imported in cell 0. Explicit NumPy array operations, slicing, masking, broadcasting and axis aggregation: Not used.
08	Pandas DataFrame — cleaning, filtering, groupby	DataFrame loading and exploration: cells 0–2. Data cleaning: cell 3 (strip(), drop_duplicates() and pd.to_numeric()). CSV export: cell 4. Encoding: cell 5 (pd.get_dummies()). Feature and target separation: cell 6. Model results DataFrames: cells 12 and 31. Groupby: Not used.
09	Matplotlib / Seaborn visualisations	Cells 13–15: class distribution, age distribution and gender distribution. DataVisualizer class and its show_class_distribution(), show_age_distribution() and show_gender_distribution() methods: cell 24.
10–11	Train/test split, model fitting, evaluation, model comparison	Train/test split: cell 7 (train_test_split()). Model fitting: cell 8 (LogisticRegression) and cell 9 (DecisionTreeClassifier). Training accuracy: cells 10 and 38. Classification reports: cells 11 and 41. Accuracy comparison: cell 12. Confusion matrix: cell 28. Accuracy, precision, recall and F1-score comparison: cell 31.
12/13	Chosen track — text features or image preprocessing	Text/NLP track: cell 16 (TfidfVectorizer and cosine_similarity) and HealthAssistant class, cell 21 (ask_question()). Image preprocessing: Not used.
14	Modularity, docstrings, README, ethical discussion	Modularity: functions and classes across cells 16–30. Docstrings: Not used. README: root README.md and folder-specific README files in the GitHub repository. Ethical discussion: cells 18, 22 and 29 (educational awareness, not medical diagnosis) and cell 37 (project conclusion).



4.3  Key Implementation Details
# Paste a short, representative excerpt here.
1. NLP-Based Health Assistant
The Health Assistant uses TF-IDF and Cosine Similarity to understand diabetes-related questions and find the most relevant predefined answer. First, the user's question is converted into a TF-IDF vector. Cosine Similarity compares it with the stored question vectors, and the system selects the question with the highest similarity score. A threshold of 0.15 is used to avoid returning unrelated answers.
Code Excerpt:
def ask_question(self, user_question):
    user_vector = self.vectorizer.transform([user_question])
    scores = cosine_similarity(user_vector, self.question_vectors)
    best_match = scores.argmax()

    if scores[0][best_match] < 0.15:
        return "Sorry, I don't have information about this question."

    return self.qa_data[self.questions[best_match]]
Explanation:
This approach was selected because it allows users to ask questions in their own words instead of requiring an exact match with stored questions. TF-IDF converts text into numerical features, while Cosine Similarity identifies the closest matching question. This makes the Health Assistant simple and suitable for a predefined diabetes-related question-answer dataset.
2. Machine Learning Model Training and Comparison
The project uses two machine learning algorithms, Logistic Regression and Decision Tree, to analyze the diabetes dataset. The dataset is divided into training and testing sets using an 80/20 split. Both models are trained using the training data and evaluated on the testing data.
Code Excerpt:
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

lr_model = LogisticRegression(max_iter=1000)
lr_model.fit(X_train, y_train)

dt_model = DecisionTreeClassifier(random_state=42)
dt_model.fit(X_train, y_train)
Explanation:
These two algorithms were selected to compare different classification approaches on the same dataset. Logistic Regression provides a linear classification approach, while Decision Tree uses decision rules to classify records. Both models are evaluated using the same testing data, allowing their performance to be compared fairly. This analysis is for educational purposes and does not provide medical diagnosis.


5.  Dataset
Give the exact source of your data. If it is public, the link is required. If the data is external, self-collected or generated, give the full details below instead so that the examiner can verify it.
Dataset name	 Early Stage Diabetes Risk Prediction Dataset

Link (required for a public dataset or API)	 https://archive.ics.uci.edu/dataset/529/early

Type	Public dataset 
Size	Records: 520 original records; 251 records after cleaning.
Files / size on disk: 1 CSV file (diabetes_data.csv). Local file size was not recorded.
Fields used	 Age, Gender, Polyuria, Polydipsia, sudden weight loss, weakness, Polyphagia, Genital thrush, visual blurring, Itching, Irritability, delayed healing, partial paresis, muscle stiffness, Alopecia, Obesity, and class
Licence / terms of use	 Creative Commons Attribution 4.0 International (CC BY 4.0). The dataset can be shared and adapted with appropriate attribution to the original source.
Cleaning applied	 Column names and text values were cleaned using strip(). Duplicate records were removed using drop_duplicates(), and the Age column was converted to numeric values using pd.to_numeric(). The original dataset contained 520 records, and 269 duplicate records were removed, leaving 251 records. No missing values were found after cleaning.
Offline caching	 The dataset is stored locally as diabetes_data.csv and loaded using Pandas pd.read_csv(). The project does not require an online API to access the dataset.


If your data is external or self-collected and has no link, describe below exactly how it was obtained — who collected it, when, by what method, how many records, and whether any permission was required. Attach or commit the raw files in data/raw/.
Not applicable. This project uses a publicly available dataset from the UCI Machine Learning Repository. According to the original source, the data was collected through direct questionnaires from patients at Sylhet Diabetes Hospital, Bangladesh, and approved by a doctor. The dataset was obtained from UCI for this project; it was not collected personally

6.  Results and Analysis
6.1  Program Output

[ Insert a screenshot of your program running ]
 




Figure 6.1  The application in use
6.2  Visualisation

 




                                                            Figure 6.2  «  Diabetes Class Distribution  »
This chart shows the distribution of diabetes classes (Positive and Negative) in the dataset. It helps us understand how the records are distributed between the two classes.


 

                       
               Figure 6.3  «  Age Distribution by Diabetes Class»


This chart shows the age distribution of the individuals in the dataset, separated by diabetes class. It helps us observe how the age values are distributed across Positive and Negative records.

 
                       Figure 6.4  «  Diabetes Distribution by Gender»
»

This chart shows the distribution of Positive and Negative diabetes records across genders. It helps us compare the class distribution between male and female individuals in the dataset.

6.3  Model Results
Report every model you tried, measured with the same metric on the same test split, then state which you selected and why
Model / Configuration	Metric	Training Score	Test Score	Notes
Logistic Regression (max_iter=1000)	Accuracy	92.5%	82.35%	Smaller gap between training and test accuracy.
Decision Tree (random_state=42)	Accuracy	100%	82.35%	Larger gap between training and test accuracy; possible overfitting.
.
Logistic Regression was selected as the preferred model because both models achieved the same test accuracy of 82.35%. However, Logistic Regression has a smaller difference between training and testing accuracy compared to Decision Tree. The Decision Tree achieved 100% training accuracy but only 82.35% testing accuracy, which indicates possible overfitting.
Therefore, Logistic Regression was preferred because it provides the same test accuracy with a smaller training-to-test gap.


7.  Testing, Error Handling and Ethics
7.1  Test Cases
Record what actually happened, not what you hoped would happen.
#	Test Case	Expected	Actual	Pass
1	Normal input – typical run	Notebook should run and display the main menu.	Notebook executed successfully and displayed the system options.	Yes
2	Dataset loading	CSV dataset should load successfully.	Dataset loaded successfully from diabetes_data.csv.	Yes
3	Data cleaning	Duplicate records should be removed and missing values checked.	Dataset was reduced to 251 rows, with 0 missing values and 0 duplicate rows.	Yes
4	NLP Health Assistant	User question should receive a relevant predefined answer.	The Health Assistant matched the question and displayed a relevant answer.	Yes
5	Machine Learning Models	Both models should train and display their test accuracy.	Logistic Regression and Decision Tree both achieved 82.35% test accuracy.	Yes

7.2  Exception Handling
Exception	Where it is caught	What the user sees
FileNotFoundError	No explicit exception handling is implemented for CSV loading.	The program may display a FileNotFoundError if diabetes_data.csv is missing.
ValueError	No explicit exception handling is implemented.	An error message may appear if an invalid value is processed.
requests.exceptions.…	Not applicable – the project does not use API calls or the requests library.	Not applicable.
Custom Exception	No custom exception is defined in the project.	Not applicable.

7.3  Ethical Considerations
GlucoGuide AI uses the publicly available UCI Early Stage Diabetes Risk Prediction dataset, which contains questionnaire data collected from patients at Sylhet Diabetes Hospital, Bangladesh. The project uses this existing dataset and does not collect patients' personal data directly. However, the dataset documentation available to this project does not clearly specify individual consent details. The model's output may be biased because the dataset represents a limited group of patients and may not reflect other populations. A wrong prediction could cause unnecessary worry or false reassurance. Therefore, users should not make medical decisions based on the system's results. GlucoGuide AI is designed for educational purposes only. It does not provide a medical diagnosis or treatment and cannot replace advice from a qualified healthcare professional.



8.  Individual Contributions and Conclusion
This chapter is read alongside your repository's commit history. Fill it in honestly — it is the basis on which individual marks are awarded.
Field	Details
Member	Syeda Haram Waqar
Modules / Files Owned	Complete GlucoGuide AI project, including src/GlucoGuide.ipynb, dataset files, project documentation, visualizations, and model evaluation results.
Specific Work Done		Designed and developed the complete GlucoGuide AI project. Implemented the NLP Health Assistant using TF-IDF and Cosine Similarity, Diabetes Risk Awareness module, Health Information module, data preprocessing, data visualizations, and Logistic Regression and Decision Tree model training and evaluation. Also prepared the project proposal, README files, and project report.

Commits	Project development and documentation commits are available in the GitHub repository's commit history.
Share	100%

8.1  Challenges Faced

1. Understanding Python and OOP Concepts
Since I had limited programming experience, understanding Python concepts and applying Object-Oriented Programming in the project was challenging. Organizing the code into classes and methods also required extra effort. I addressed these challenges by learning concepts step by step, practising examples, and gradually applying them to the project.
2. Dataset Preprocessing and Machine Learning
Preparing the diabetes dataset for machine learning was another challenge. I had to understand data cleaning, duplicate removal, categorical encoding, feature and target separation, and model training. I handled these tasks step by step and evaluated the performance of Logistic Regression and Decision Tree models using accuracy, precision, recall, F1-score, classification reports, and confusion matrices.
3. Implementing the NLP Health Assistant
Implementing the text-based Health Assistant was challenging because it required understanding how to convert questions into numerical features and compare them. I used TF-IDF Vectorization and Cosine Similarity to match user questions with predefined diabetes-related questions and return relevant answers.


8.2  Conclusion and Future Work
GlucoGuide AI successfully achieved its main objectives as a Python-based diabetes awareness and educational system. It provides an NLP-based Health Assistant using TF-IDF and Cosine Similarity, a Diabetes Risk Awareness module that counts user-reported factors, health information, and data visualizations.
The project also uses the UCI Early Stage Diabetes Risk Prediction dataset to train and compare Logistic Regression and Decision Tree models. Both models achieved 82.35% test accuracy on the selected test dataset. Their performance was further evaluated using precision, recall, F1-score, classification reports, and confusion matrices.
This project provided practical experience in Python programming, Object-Oriented Programming, data preprocessing, Natural Language Processing, data visualization, and machine learning.
Future Work:
•	Expand the Health Assistant's question-answer dataset.
•	Include more relevant and diverse diabetes-related data for further model evaluation.
•	Improve the Risk Awareness module with more comprehensive educational information.
•	Develop a user-friendly graphical interface instead of relying only on Jupyter Notebook.
•	Further evaluate and improve the machine learning models using additional data.

Appendix A — Setup and Execution
Repeat here, exactly, the steps from your README that make the project run from a clean clone. The examiner will follow these steps literally.
git clone <your-repository-url>          # 1. clone
cd <repository-name>
pip install -r requirements.txt          # 2. install
python src/main.py                       # 3. run
Add below anything else required: where to place a configuration file or key, how to obtain the dataset if it is not committed, and the Python version you developed against.
Steps to run the project:
# 1. Clone the repository
git clone <https://github.com/25k-0116Haram/GlucoGuide-AI >

# 2. Open the project folder
cd <GlucoGuide-AI>

# 3. Install required libraries
pip install pandas numpy matplotlib seaborn scikit-learn notebook

# 4. Start Jupyter Notebook
jupyter notebook

Additional Requirements:
1.	Open GlucoGuide.ipynb in Jupyter Notebook.
2.	Keep diabetes_data.csv in the same folder as the notebook.
3.	Run all notebook cells in order using Run All.
4.	No API key or configuration file is required because the project works offline.
5.	Python version: 3.13.17 (as recorded in the notebook metadata).Python version: Python 3.13.17 (64-bit).



End of Project Report
