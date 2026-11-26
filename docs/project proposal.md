AL-2001 Programming for AI Project Proposal Fall 2026 
AL-2001 · Fall 2026 · Khadeejah Ashraf  Page 1 of 7 
 
FAST — NATIONAL UNIVERSITY OF COMPUTER AND EMERGING SCIENCES 
FAST School of Computing Karachi Campus Department of Artificial Intelligence & Data Science 
AL-2001  Programming for Artificial Intelligence (Laboratory)  ·  Fall 2026 
 
 
PROJECT PROPOSAL 
Semester Lab Project Weightage 1 mark 
Instructions — delete this box before submitting. Complete every section below in three to four pages. Replace all 
italicised blue guidance text with your own writing, and delete any row or prompt you do not need. Submit this 
document in BOTH PDF and Markdown formats, placed in the docs/ folder of your GitHub repository, and have the 
group leader submit the repository link to Google Classroom. 
Group Information 
 Name Roll Number Section Role in the project 
Leader  Syeda Haram Waqar  25K-0116  BAI-3A  AI project Developer 
Member 2  None       
Member 3  None       
 
Project Title  GlucoGuide AI – Diabetes Awareness and Risk Education System 
Specialisation Track Track A — Text / NLP         
GitHub Repository 
URL   
Date of Submission  13th week 
 
1.  Project Title and Summary 
GlucoGuide AI is a Python-based system designed to spread awareness about diabetes. It 
answers users’ diabetes-related questions through a text-based health assistant. It also 
analyzes user-provided health information to explain possible risk factors for educational 
purposes. The system uses charts and visualizations to present health information clearly. It 
helps students and individuals understand diabetes and its risk factors, but it does not 
provide a medical diagnosis. 
 
 
 
2.  Problem Statement and Motivation 
 
AL-2001 Programming for AI Project Proposal Fall 2026 
AL-2001 · Fall 2026 · Khadeejah Ashraf  Page 2 of 7 
Many people lack clear and reliable information about diabetes, its risk factors, and 
prevention. Finding useful information online can be time-consuming because it is spread 
across different websites and often uses complicated medical terms. Students and individuals 
may struggle to understand diabetes-related information and interpret health data. Currently, 
people rely on internet searches, articles, or informal advice to learn about diabetes, which can 
sometimes cause confusion or misunderstandings. 
GlucoGuide AI aims to address this problem by providing a text-based assistant that answers 
diabetes-related questions, explains possible risk factors using user-provided information, and 
presents health information through simple charts. The system will provide educational 
guidance rather than medical diagnosis. Solving this problem is worthwhile because it can 
make diabetes awareness more accessible and encourage people to make informed decisions 
about seeking professional medical advice. 
 
 
 
 
3.  Proposed Solution 
 
GlucoGuide AI will provide a simple and interactive way for users to learn about diabetes. 
Users will be able to enter diabetes-related questions or provide basic health information, such 
as age and other relevant risk factors. The system will process their input and provide easy-to
understand educational responses. The health assistant will answer common questions about 
diabetes, while the risk assessment component will explain possible risk factors based on the 
information provided. The visualization component will display relevant health data through 
charts, helping users understand patterns and information more easily. The system will be 
developed in Python using a Jupyter Notebook environment. It will focus on health education 
and awareness rather than providing medical diagnoses or replacing professional medical 
advice. 
The main components of the project are: 
1. User Input Module: Collects users’ questions and basic health information. 
2. NLP Health Assistant: Processes text-based questions and provides diabetes-related 
educational answers. 
3. Risk Assessment Module: Examines the provided information and explains relevant 
risk factors. 
4. Data Visualization Module: Creates charts to present health information clearly. 
5. Output Module: Displays responses, risk-factor explanations, and visualizations in an 
understandable format. 
 
 
 
 
3.1 Planned Class Design 
 
AL-2001 Programming for AI Project Proposal Fall 2026 
AL-2001 · Fall 2026 · Khadeejah Ashraf  Page 3 of 7 
1. HealthAssistant 
 Attributes: knowledge_base, user_question 
 Methods: answer_question(), search_information() 
 Purpose: Answers users’ diabetes-related questions with educational information. 
2. RiskAssessment 
 Attributes: age, health_information, risk_factors 
 Methods: collect_information(), assess_risk_factors(), 
generate_explanation() 
 Purpose: Examines user-provided information and explains relevant diabetes risk 
factors for educational purposes. 
3. DataVisualizer 
 Attributes: health_data, chart_type 
 Methods: load_data(), create_chart(), display_visualization() 
 Purpose: Presents health-related data through charts and graphs. 
4. GlucoGuideAI 
 Attributes: assistant, risk_assessor, visualizer 
 Methods: run_system(), display_results() 
 Purpose: Coordinates the main components and displays the results to the user. 
Relationships: The GlucoGuideAI class coordinates the HealthAssistant, 
RiskAssessment, and DataVisualizer classes. Each class performs its own task, and the 
main class brings their functionality together into one system. 
 
 
 
 
4.  Scope 
In scope — the features you commit to delivering. List the features that must work for the project to be 
considered complete. 
# Feature Why it is essential 
1  Diabetes Q&A Assistant Allows users to ask diabetes-related questions and 
receive simple educational answers. 
2  Health Information Input  Collects basic user information needed for 
educational risk-factor assessment. 
3  Risk Factor Assessment  Explains possible diabetes risk factors based on the 
information provided by the user. 
4  Data Visualization  Displays health-related data through charts to make 
information easier to understand. 
AL-2001 Programming for AI Project Proposal Fall 2026 
AL-2001 · Fall 2026 · Khadeejah Ashraf  Page 4 of 7 
# Feature Why it is essential 
5  Results Display 
 Presents answers, risk-factor explanations, and 
charts in a clear and understandable format. 
 
 
Out of scope — deliberately excluded. Naming what you will not build is as important as naming what you will; 
it is how an examiner judges whether your scope is realistic. 
The project will not provide medical diagnoses, prescribe medicines, or recommend 
personalized treatments. It will not connect to hospitals, doctors, or electronic medical 
records. Real-time monitoring through wearable devices and mobile applications will not be 
included. The system will focus only on diabetes awareness, educational risk-factor 
assessment, and basic health data visualization. Advanced clinical prediction and professional 
medical decision-making are also outside the scope of this project. 
 
5.  Data Source 
Identify exactly where your data will come from, and confirm that you can actually obtain it. A project whose data 
source turns out to be unreachable in week 12 cannot be rescued. 
Source 
name and 
URL 
1.  Early Stage Diabetes Risk Prediction Dataset – UCI Machine Learning 
Repository: 
https://archive.ics.uci.edu/dataset/529/early+stage+diabetes+risk+prediction+
dataset 
2. CDC Diabetes Information:  
https://www.cdc.gov/diabetes/about/ 
 
Type Downloadable dataset  ,      Self-collected / generated (for Q and A) 
Access 
requiremen
ts 
No key needed        
Approximat
e size 
 The UCI dataset contains 520 records and 16 input features, with a small 
downloadable file of approximately 34 KB. The educational Q&A collection will be 
stored locally in a simple text or CSV file. 
Licence / 
terms of use 
 The UCI dataset is available under the Creative Commons Attribution 4.0 
International (CC BY 4.0) licence. The dataset source will be credited in the project. 
CDC educational information will be used with appropriate source attribution. 
Offline 
fallback 
 The downloaded UCI dataset will be saved locally in CSV format, and the 
educational Q&A collection will be stored in a local file. The program will read these 
files directly from the computer, allowing the risk-factor assessment, charts, and 
predefined educational answers to work without an internet connection. 
 
AL-2001 Programming for AI Project Proposal Fall 2026 
AL-2001 · Fall 2026 · Khadeejah Ashraf  Page 5 of 7 
Required: your program must still run when the network is unavailable, by reading a locally cached copy of the data. 
Describe your caching plan in the last row above. 
6.  Technologies and Lab Coverage 
For each row, state in one line how your project will use that concept. If you genuinely cannot see a use for one, write 
“to be identified” — but every row must be satisfied by the time the report is written. 
Lab Concept to be applied How your project will use it 
01–03 Core Python, control flow, data 
structures 
  
Python variables, conditions, loops, lists, and dictionaries 
will manage user inputs and diabetes-related information. 
 
04 Functions, lambda, map / filter 
  
Functions will process user information, while filtering will 
help select relevant records and risk factors. 
 
05 Classes, inheritance, encapsulation, 
polymorphism 
 
 Classes will organize the health assistant, risk assessment, 
and visualization components into reusable modules. 
 
06 Files (TXT / CSV / JSON), exceptions, 
web API 
  
The project will read local CSV datasets and text or JSON 
files, with exception handling for missing or invalid data. A 
live web API will not be required. 
 
07 NumPy arrays, broadcasting, 
vectorisation 
  
NumPy will perform efficient numerical operations on 
health-related data. 
 
08 Pandas — loading, cleaning, grouping 
  
Pandas will load the diabetes dataset, handle missing or 
duplicate records where applicable, and group data for 
analysis. 
 
09 Matplotlib / Seaborn visualisations 
  
Matplotlib and Seaborn will create charts showing patterns 
and distributions in the diabetes dataset. 
 
10–11 Machine learning, model comparison 
 
Suitable classification models will be trained and compared 
on the diabetes dataset for educational risk-pattern analysis. 
 
AL-2001 Programming for AI Project Proposal Fall 2026 
AL-2001 · Fall 2026 · Khadeejah Ashraf  Page 6 of 7 
Lab Concept to be applied How your project will use it 
12 or 
13 
Chosen track — NLP text features or 
image preprocessing 
  
NLP techniques will process users’ text questions and help 
the health assistant identify relevant diabetes-related 
information. 
 
14 Documentation, modularity, ethical 
considerations 
  
The project will use organized code, clear documentation, 
appropriate source attribution, and a disclaimer that it does 
not provide medical diagnoses. 
 
 
7.  Division of Work 
 
Member Modules / components owned Approximate 
share 
  
Individual Project 
Developer 
HARAM WAQAR 
  
Health Assistant, Risk Assessment, Data Visualization, Dataset 
Loading and Cleaning, NLP Implementation, Machine Learning 
Model Comparison, Testing, and Documentation 
 
100% 
  
      
      
 
8.  Milestones and Timeline 
 
# Milestone — what will be demonstrably working Target date Owner 
1  Dataset downloaded, loaded, and cleaned  29 Oct 2026  Haram 
2  NLP Health Assistant answers basic questions  02 Nov 2026  Haram 
3  Risk Assessment module works with user input  06 Nov 2026  Haram 
4  Charts and machine learning model comparison completed  10 Nov 2026  Haram 
5 Final integration, documentation and repository cleanup  14 Nov 2026  Haram 
 
9.  Expected Outcome and Risks 
 
AL-2001 Programming for AI Project Proposal Fall 2026 
AL-2001 · Fall 2026 · Khadeejah Ashraf  Page 7 of 7 
The final submission will be a working Python-based GlucoGuide AI system in Jupyter 
Notebook. The examiner will be able to ask diabetes-related questions, enter basic health 
information for educational risk-factor assessment, and view charts generated from the 
dataset. The project will demonstrate Python programming, NLP, data analysis, visualization, 
and basic machine learning model comparison. 
Risk 1: Dataset or data quality issues. If the dataset contains missing values or causes 
processing errors, I will clean the data and handle errors before analysis. 
Risk 2: Limited NLP accuracy. If the assistant cannot answer some questions correctly, I 
will improve its locally stored question-and-answer collection and provide clear fallback 
responses. 
 
 
 
 
For office use — Lab 
Instructor  
Proposal status Approved  ☐          Approved with changes  ☐          Revision required  ☐ 
Comments   
Signature and date   
 
End of Project Proposal 