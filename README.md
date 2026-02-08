# Social Media Use & Mental Health – CIUS 2022 Analysis
## Capstone Project – Data Analytics
---


### Project Overview :
This capstone investigates how digital behavior, social media usage relate to mental health outcomes among Canadians.
Using the Canadian Internet Use Survey (CIUS 2022) Public Microdata File (PUMF), we:
- Cleaned and prepared a custom dataset (16 selected variables)
- Performed extensive Exploratory Data Analysis (EDA)
- Labeled and transformed categorical codes
- Built interactive Tableau dashboards


## Data Source

### 📌 Source
The analysis relies on data from the **Canadian Internet Use Survey (CIUS) – 2022**.

* **Provider:** Statistics Canada
* **File Used:** Public Use Microdata File (PUMF)

### 📌 Why CIUS? (Strategic Relevance)
The CIUS 2022 survey is uniquely suited for this capstone project because it contains variables directly related to all key areas of investigation:

* **Digital Behavior:** Time spent online and communication frequency.
* **AI Interaction:** Awareness and use of AI tools (e.g., chatbots, email automation).
* **Mental Health:** Comprehensive mental health and stress indicators.
* **Contextual Data:** Rich demographics including age, gender, province, income, and education, allowing for granular analysis.

---
| **Variable**            | **Meaning**                                                                  |
| ----------------------- | ---------------------------------------------------------------------------- |
| **Province**            | Canadian province (labeled from codebook)                                    |
| **Age**                 | Respondent’s age group (6 categories)                                        |
| **Gender**              | Male / Female                                                                |
| **Education**           | Highest level of education completed                                         |
| **Employment**          | Employment status at time of survey                                          |
| **Income_Group**        | Household income quintile (1–5)                                              |
| **Rel_Satisfaction**    | Satisfaction with personal relationships (1–5 scale)                         |
| **Online_Contact_Freq** | How often the person contacts friends online (daily/weekly/etc.)             |
| **SM_Interfere_Rel**    | Whether online activity interferes with relationships                        |
| **SM_Interfere_Life**   | Whether online activity interferes with daily functioning/life               |
| **SM_Anxious_Envious**  | Whether online use causes anxiety, envy, or depression                       |
| **SM_AI_Chatbot**       | Whether the respondent noticed AI in chatbots                                |
| **SM_AI_Email**         | Whether the respondent noticed AI in email filtering/sorting                 |
| **Household_Type**      | Household composition (family with children, without children, single, etc.) |
| **Online_Shopping**     | Whether the person spent ≥ $1 online                                         |
| **Weight (WTS_M)**      | Survey weight for proper population representation                           |

These variables were selected because they directly match the survey form we created, and they represent digital behavior + well-being.

### Data Cleaning & Preparation
Major cleaning steps included:

- [x] **Dropping invalid CIUS codes** (`7`, `8`, `9`, `96`, `97`, `98`, `99`)
- [x] **Label mapping** for all categorical variables
- [x] **Converting Yes/No codes** to boolean flags
- [x] **Creating derived variables** (e.g., `Daily Contact Flag`, `AI Awareness Flag`)
- [x] **Removing unused CIUS columns** (hundreds of irrelevant items)


# Exploratory Data Analysis (EDA)
**File:** `CIUS_Social_Media_EDA.ipynb`

### 🔹 Scope of Analysis
| Category | Variables & Methods |
| :--- | :--- |
| **Univariate** | • Province, Age, Gender, Education, Income<br>• Relationship satisfaction<br>• Social media & AI awareness<br>• Online shopping behavior |
| **Bivariate** | • Online contact frequency by Age<br>• Relationship satisfaction vs. Online contact<br>• Interference vs. Age<br>• Anxiety vs. Online behavior<br>• AI awareness vs. Demographics |
| **Visuals** | • Missing value heatmap<br>• Behavioral correlation heatmap<br>• Relationship satisfaction × Online Contact matrix |

---

### 🔹 Key Findings
* **Usage Patterns:** Younger adults contact friends online more frequently.
* **Mental Health:** Emotional impact is noticeably higher among middle-age groups.
* **Interference:** Most respondents report no interference, but the “Yes” segment is statistically significant.
* **AI Adoption:** AI awareness (specifically chatbots & emails) is rising across all age cohorts.
* **Social Correlation:** Relationship satisfaction **decreases** as online contact frequency increases.

## Tech Stack

| Category | Tools Used |
| :--- | :--- |
| **Languages** | Python (v3.x) |
| **Libraries** | Pandas, NumPy, Matplotlib, Seaborn |
| **IDE / Editor** | Jupyter Notebook |
| **Data Source** | Statistics Canada CIUS 2022 PUMF |
| **BI Tool** | Tableau Public |

