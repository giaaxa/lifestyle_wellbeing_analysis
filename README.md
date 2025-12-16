# Lifestyle & Wellbeing Analytics Project

Lifestyle & Wellbeing Analytics is a data analysis project that explores how everyday activities (such as sleep, exercise, screen time, social interaction, and work hours) relate to self-reported stress and wellbeing.

Using Python for data preparation, analysis, and visualisation, the project demonstrates how basic analytics can support **evidence-based decisions** for wellbeing programmes, HR policies, and digital health products.

---

## CI Logo

![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

---

## Dataset Content

The project uses a public survey dataset from Kaggle:

- **Dataset name:** Lifestyle and Wellbeing Data  
- **Source:** Kaggle (Yash Dalvi)  
- **File format:** CSV  
- **Approx. size:** ~16k rows, ~20–30 columns  

### Key Variable Types

- **Lifestyle / Activity variables** (example names; actual names documented in the Notebook):
  - Sleep duration (hours per night)
  - Exercise / physical activity frequency
  - Daily screen time / device usage
  - Social interaction (frequency/time spent)
  - Work / study hours

- **Outcome variables:**
  - Self-reported stress level
  - Self-reported wellbeing / happiness / life satisfaction score

- **Optional demographics (depending on dataset fields):**
  - Age
  - Gender
  - Region or country

All data is anonymised, with no personally identifiable information.

---

## Business Requirements

The project is framed around a realistic business case:

> Organisations building wellbeing programmes (e.g. HR teams, student services, wellness apps) want to know which lifestyle factors are most strongly associated with stress and wellbeing, so they can prioritise interventions and communication.

From this, the key **business requirements** are:

1. **BR1 – Identify key lifestyle drivers of stress and wellbeing**  
   Determine which activities (sleep, exercise, screen time, social time, work hours) are most strongly associated with lower stress and higher wellbeing.

2. **BR2 – Provide clear, visual insights for non-technical stakeholders**  
   Deliver intuitive visualisations that communicate the relationships between lifestyle habits and wellbeing outcomes for decision-makers who are not data scientists.

3. **BR3 – Build a simple, interpretable predictive prototype**  
   Create a basic model that estimates stress (or wellbeing) from lifestyle variables, to demonstrate how analytics can support evidence-based decisions.

4. **BR4 – Document an end-to-end ETL & analysis workflow**  
   Show a transparent Python-based pipeline for extracting, cleaning, transforming, analysing, and visualising data, designed to be reproducible and extendable.

---

## Hypothesis and How to Validate

### Primary Hypothesis

> **H1:** Individuals who engage in more health-promoting activities (adequate sleep, regular exercise, balanced social interaction) will report **higher wellbeing** and **lower stress** compared to those with poorer lifestyle habits.

### Secondary Hypotheses

- **H2:** Higher daily **screen time** is associated with **higher stress** and/or **lower wellbeing** scores.  
- **H3:** The combination of **long work/study hours** and **short sleep duration** is associated with **higher stress** than either factor alone.  
- **H4:** After adjusting for basic demographics (where available), **exercise frequency** remains a significant predictor of **better wellbeing**.

### Validation Approach

The hypotheses are validated using:

1. **Descriptive analytics**
   - Compare distributions of lifestyle variables and outcome scores.
   - Look for clear trends (e.g. “short sleepers” vs “normal sleepers”).

2. **Correlation analysis**
   - Compute correlations between lifestyle variables and stress/wellbeing outcomes.
   - Check if directions and magnitudes align with H1–H4.

3. **Group comparisons**
   - Create categories (e.g. low/medium/high exercise, short/normal/long sleep).
   - Compare mean stress/wellbeing across groups (using t-tests/ANOVA where appropriate).

4. **Regression modelling**
   - Build a simple linear regression (or logistic regression if outcomes are binned).
   - Inspect coefficients for lifestyle variables to see:
     - Which remain significant predictors.
     - Whether signs (positive/negative) match the hypotheses.

Results and conclusions for each hypothesis are summarised in the Notebook and briefly synthesised in the README.

---

## Project Plan

### High-Level Steps

1. **Project definition**
   - Select dataset and domain (lifestyle & wellbeing).
   - Formulate business requirements and hypotheses.

2. **Environment setup**
   - Create project structure and virtual environment in VS Code.
   - Install necessary Python libraries.

3. **ETL pipeline**
   - **Extract:** Load CSV from `data/v1/raw/`.  
   - **Transform:** Clean and preprocess data (handle missing values, convert data types, create derived features and categories).  
   - **Load:** Save cleaned dataset to `data/v1/processed/` and use it for analysis.

4. **Exploratory Data Analysis (EDA)**
   - Descriptive statistics, initial visualisations of key variables.
   - Check distributions, outliers, and basic relationships.

5. **Hypothesis-driven analysis**
   - Correlation matrix and visualisations mapped directly to business requirements.
   - Group comparisons and simple statistical tests.

6. **Modelling**
   - Build a basic regression model to predict stress or wellbeing from lifestyle variables.
   - Evaluate model performance (R², MAE) and interpret coefficients.

7. **Dashboard / visual reporting**
   - Create a Notebook-based “dashboard” section with clearly labelled visualisations tied to each business requirement.
   - Optionally add interactive components with Plotly (e.g. sliders/dropdowns).

8. **Interpretation, limitations, and recommendations**
   - Summarise findings in clear language.
   - Highlight practical implications for wellbeing programmes.
   - Discuss limitations, ethical considerations, and possible extensions.

### Data Management

- **Collection:** Dataset downloaded from Kaggle and stored in a dedicated `data/v1/raw/` folder.  
- **Processing:** All data cleaning steps are performed in the Notebook and clearly documented.  
- **Storage:** Cleaned data saved into `data/v1/processed/` to separate raw vs processed data.  
- **Versioning:** Folder version (`v1`) and git commit history are used to track evolution of the project.

### Methodology Rationale

- A **survey dataset** was chosen because it directly reflects individual lifestyle behaviours and perceived wellbeing, aligning with the project’s goals.
- Descriptive, correlational, and regression analyses offer **interpretable, business-friendly** insights rather than black-box models.
- The methodology maps neatly to the assessment focus on:
  - ETL,
  - visualisation,
  - hypothesis testing,
  - storytelling with data.

---

## Rationale to Map Business Requirements to Data Visualisations

| Business Requirement                                       | Visualisation(s) Used                                              | Rationale                                                                                                                                                                        |
| ---------------------------------------------------------- | ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BR1 – Identify key lifestyle drivers of stress & wellbeing | Correlation heatmap, boxplots, scatter plots with regression lines | Heatmaps give an at-a-glance overview of relationships. Boxplots and scatter plots show how stress/wellbeing change across lifestyle levels and support the hypotheses visually. |
| BR2 – Visual insights for non-technical stakeholders       | Histograms/KDE plots, annotated figures, clear titles and notes    | Distribution plots help people understand the sample (e.g. “most people sleep X hours”). Annotations and plain-language labels make plots accessible.                            |
| BR3 – Simple predictive prototype                          | Coefficient bar chart (optional), numeric model summary            | Plotting feature coefficients or showing a simple table of feature importance helps stakeholders see which lifestyle factors matter most in the model.                           |
| BR4 – ETL & workflow documentation                         | Markdown sections, code comments, diagrams (if used)               | Clear structure and explanation of each step demonstrate the pipeline and make it reusable by technical teams.                                                                   |

Each visual in the Notebook is explicitly linked to one or more business requirements in its markdown explanation.

---

## Analysis Techniques Used

### Techniques

- **Descriptive statistics**
  - Mean, median, standard deviation, distribution checks for key variables.

- **Exploratory Data Analysis (EDA)**
  - Histograms and KDE plots for lifestyle behaviours and wellbeing scores.
  - Boxplots for group comparisons (e.g. sleep categories vs stress).

- **Correlation analysis**
  - Pearson or Spearman correlation matrix (depending on distributions).
  - Heatmap visualisation to summarise relationships.

- **Group comparisons / hypothesis testing**
  - Comparisons of means between groups (e.g. low vs high exercise), using t-tests or similar methods to support or challenge the hypotheses.

- **Regression modelling**
  - Linear regression predicting stress (or wellbeing) from lifestyle variables.
  - Optional logistic regression if outcomes are binned into categories.

### Limitations & Alternative Approaches

- The dataset is **cross-sectional**, so causal statements cannot be made; a longitudinal design would be needed for causal inference.
- Self-report data introduces bias; pairing lifestyle logs with objective measures (e.g. wearable data) would strengthen conclusions.
- More advanced models (Random Forest, Gradient Boosting) or regularisation techniques (Lasso/Ridge) could offer better predictive performance but were deprioritised in favour of interpretability for non-technical audiences.
- If demographics are limited, controlling for confounders is constrained; richer demographic data would allow more robust modelling.

### Use of Generative AI Tools

Generative AI tools (Copilot in VS Code) were used for:

- **Ideation and design thinking:**
  - Refining business requirements.
  - Structuring the README and Notebook layout.
- **Code optimisation and patterns:**
  - Suggesting idiomatic pandas and plotting patterns.
  - Providing template examples for regression and plotting, which were then adapted and verified.
- **Narrative support:**
  - Drafting initial explanations and summaries, later edited by the learner.

All AI-assisted content was reviewed, tested, and, where necessary, modified. AI tools were treated as helpers, not as sources of final, unedited code.

---

## Ethical Considerations

### Data Privacy

- The dataset is anonymised and does not include direct identifiers.
- No attempt was made to re-identify individuals, and analysis focuses on aggregate patterns.

### Bias & Fairness

- The sample may not be demographically representative (e.g. skewed towards certain age groups, countries, or socioeconomic status).
- This can bias the relationships observed, so conclusions are presented cautiously and framed as **pattern insights**, not universal truths.

### Legal & Societal Issues

- The data is used under the terms of its public release on Kaggle, within an educational context.
- Results are not used for any decisions affecting real individuals and are explicitly labelled as exploratory.
- The project avoids prescriptive or moralising claims about “correct” lifestyles and instead focuses on statistically observable associations.

---

## Dashboard Design

Although the primary implementation is a **Jupyter Notebook**, the analysis is structured to function like a simple analytics dashboard, and could be transferred to Plotly Dash or Streamlit.

### Planned Dashboard Pages / Sections

1. **Overview**
   - Project summary, dataset overview.
   - Key high-level statistics (e.g. average sleep, stress, wellbeing).

2. **Lifestyle Distributions**
   - Histograms/KDE plots for sleep, exercise, screen time, social time, work hours.
   - Quick understanding of how the sample actually lives.

3. **Lifestyle vs Stress**
   - Boxplots and scatter plots (with regression lines) exploring:
     - Sleep vs stress
     - Exercise vs stress
     - Screen time vs stress

4. **Lifestyle vs Wellbeing**
   - Similar plots showing lifestyle vs wellbeing/happiness scores.
   - Focus on positive outcomes and protective factors.

5. **Correlation & Modelling**
   - Correlation heatmap between lifestyle variables and outcomes.
   - Simple model summary (e.g. list of top predictors) with a brief explanation.

### Communicating Insights to Different Audiences

- **Non-technical stakeholders:**
  - Clear titles, legends, and annotations.
  - Plain-language explanations under each visual.
  - Focus on “what this means in real life” rather than technical jargon.

- **Technical audiences:**
  - Access to full code in the Notebook.
  - Model metrics and assumptions documented.
  - Details of cleaning and feature engineering steps.

---

## Unfixed Bugs


---

## Development Roadmap

### Challenges and Strategies

- **Challenge:** Understanding which variables to prioritise from a relatively wide dataset.  
  **Strategy:** Start with domain intuition (sleep, exercise, screen time) and then use correlations and EDA to refine focus.

- **Challenge:** Balancing technical detail with readability for non-technical users.  
  **Strategy:** Keep the core model simple and invest more in clear visualisations and explanations.

- **Challenge:** Ensuring ETL and visualisation steps are reproducible.  
  **Strategy:** Use a clear folder structure, versioned data directory, and consistent Notebook layout.

### Future Enhancements

- Extend the Notebook into a full **interactive dashboard** using Plotly Dash or Streamlit.
- Incorporate **demographic stratification** (e.g. insights per age group).
- Explore **time-based data** (if available in future datasets) to move from cross-sectional to trend analysis.
- Experiment with more advanced models and regularisation to see if predictive performance can be improved without losing interpretability.

---

## Deployment

This project is primarily delivered as a **Jupyter Notebook** and is on GitHub.

For the purposes of this capstone:

- The core “dashboard” experience is provided inside the Notebook itself.
- No Heroku deployment.


---

## Main Data Analysis Libraries

The project uses the following key libraries:

- **pandas**
  - Data loading, cleaning, transformation.
  - Example: handling missing values, creating new derived columns.

- **numpy**
  - Numerical operations and array handling used under the hood with pandas.

- **matplotlib**
  - Base plotting library for fundamental charts and fine-tuning.

- **seaborn**
  - High-level statistical visualisations: histograms, boxplots, scatter plots, correlation heatmaps.

- **scikit-learn**
  - Train/test split, linear regression model, performance metrics (R², MAE).

- **scipy / statsmodels** (if used)
  - Statistical tests such as t-tests, ANOVA, or regression diagnostics.

All libraries are listed in `requirements.txt` and imported in the Notebook with clear usage examples.

---

## Credits

### Content & Data

- **Dataset:**
  - *Lifestyle and Wellbeing Data* – Kaggle dataset by Yash Dalvi.
- **General guidance:**
  - Code Institute course material for Data Analytics and Python for Data Preparation.

### Code & Tutorials

- Official documentation for:
  - pandas
  - seaborn
  - matplotlib
  - scikit-learn
- Stack Overflow and library examples for specific syntax questions (e.g. plot customisation, regression usage), referenced in comments where code patterns were adapted.

### Generative AI

- ChatGPT and/or GitHub Copilot were used to:
  - Refine project structure and README text.
  - Suggest code snippets and patterns, later reviewed and adapted by the learner.

---

## Acknowledgements (Optional)

- Code Institute facilitators, mentors, and peers for feedback and guidance.
- Friends and colleagues who provided informal feedback on the clarity of visualisations and explanations.
