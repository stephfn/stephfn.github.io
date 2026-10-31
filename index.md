
---
layout: default
---

# Data Science Portfolio

Welcome! I'm Stephanie, and this portfolio brings together my work in applied data science, machine learning, and scientific data analysis.

My interests are centered on healthcare, life sciences, and using data to investigate complex problems, evaluate evidence, and support informed decisions.

[About](#about) | [Projects](#projects) | [Contact](#contact)

---

## About

My background in laboratory science has shaped how I approach data analysis. Working with scientific information requires attention to data quality, documentation, reproducibility, and the limitations of what results can tell us. These principles also guide my work in data science.

I am developing my technical skills in Python, SQL, statistical analysis, machine learning, and data visualization, with a particular interest in applications involving healthcare, biotechnology, and scientific research.

My projects include both traditional machine learning problems and domain-specific investigations involving medical imaging metadata, molecular structures, chemical information, and biological data. I am particularly interested in the challenges of transforming complex or inconsistently structured data into information that can be analyzed reliably.

Throughout my coursework and independent projects, I have worked with data preparation, exploratory analysis, feature engineering, model development, evaluation, and communicating results. I also explore generative AI and large language models, including their potential applications and limitations in scientific workflows.

My goal is to continue developing as a data scientist while applying my scientific background to practical problems in healthcare, life sciences, and related industries.

### Technical Skills

**Programming and Data Analysis:** Python, SQL, pandas, NumPy, data cleaning, exploratory data analysis, and data visualization.

**Machine Learning:** Classification, regression, recommendation systems, feature engineering, model evaluation, and hyperparameter tuning.

**Scientific and Domain Applications:** Medical imaging metadata, chemical informatics, molecular structure representation, biological data, and scientific data processing.

**Tools and Development:** Jupyter Notebook, Git, GitHub, GitHub Pages, and Python-based machine learning libraries.

---

## Projects

The following projects represent work completed through coursework, collaborative assignments, and independent exploration. They demonstrate different stages of the data science workflow, including data collection, preparation, analysis, modeling, evaluation, and interpretation.

### [DICOM CT Protocol Classification](https://github.com/stephfn/dicom-ct-protocol-classification)

**Focus:** Healthcare analytics, DICOM metadata, rule-based classification, and large language models.

Developed and evaluated rule-based and zero-shot LLM approaches to classify CT imaging protocols using metadata from the public LIDC-IDRI dataset. Of 1,018 CT series, 573 contained sufficient descriptive information for classification.

The rule-based classifier achieved 97.9% agreement with manually assigned reference labels, compared with 89.9% for the LLM. Error analysis revealed differences in how the approaches interpreted ambiguous protocol descriptions, highlighting challenges in reference-label consistency and automated classification.

**Limitations:** Reference labels were assigned by a single reviewer, and excluding records with insufficient metadata may limit generalizability. The project is an exploratory comparison rather than a clinically validated classification system.

### [Chemical Data Parsing Pipeline](https://github.com/stephfn/chemical-data-parsing-pipeline)

**Focus:** Chemical informatics, text parsing, data engineering, and entity resolution.

Developed a two-stage Python proof of concept for standardizing unstructured chemical specifications and resolving inconsistent vendor product names against a canonical chemical registry.

The first stage uses regular expressions to extract and validate CAS Registry Numbers and identify purity specifications, reagent grades, and GHS hazard and precautionary codes. Refining the purity extraction logic resolved parsing failures across four illustrative records.

The second stage applies character-level TF-IDF and cosine similarity to match vendor descriptions with canonical chemical records. Five known products were matched to their expected records, while an unlisted example was flagged as unmatched.

**Limitations:** The results are based on small demonstration datasets. Matching thresholds are heuristic, and chemical identity requires verification beyond text similarity.

### [MovieLens Movie Recommender](https://github.com/stephfn/movielens-movie-recommender)

**Focus:** Recommendation systems, collaborative filtering, sparse matrices, and similarity analysis.

Developed an item-based movie recommendation system using the MovieLens Latest Small dataset, containing 100,836 ratings from 610 users.

The project constructed a movie-user rating matrix and applied cosine similarity to identify movies with related rating patterns. The resulting matrix was 98.30% sparse, illustrating the challenges of limited user-rating coverage.

The recommendation function returns ranked movies based on similarity to a selected title. Exploratory results demonstrated relationships between movies with overlapping rating histories while revealing limitations involving popularity bias, unrated movies, and the absence of personalized user evaluation.

**Limitations:** The project demonstrates recommendation generation but does not establish predictive or ranking accuracy through held-out testing.

### [Movie Review Sentiment Analysis](https://github.com/stephfn/movie-review-sentiment-analysis)

**Focus:** Natural language processing, sentiment classification, text preprocessing, and model evaluation.

Compared TextBlob and VADER sentiment analyzers using 25,000 labeled movie reviews from the IMDb dataset. The project evaluated both methods against a balanced 50% baseline and examined class-specific classification errors.

TextBlob achieved 68.52% accuracy, while VADER achieved 69.36%. Although VADER performed slightly better overall, its confusion matrix revealed substantially stronger performance on positive reviews (85.3%) than negative reviews (53.5%).

The analysis also explored text preprocessing and generated bag-of-words and TF-IDF representations containing 89,468 features.

**Key finding:** Overall accuracy can conceal meaningful differences in class-level performance.

**Limitations:** The project evaluates existing sentiment analyzers rather than training a supervised classifier. Results are specific to the selected movie review dataset.

### [Honey Yield Predictive Modeling](https://github.com/stephfn/honey-yield-predictive-model)

**Focus:** Time-series forecasting, predictive modeling, environmental sensor data, and collaborative data science.

This group project explored whether historical beehive sensor measurements could be used to predict changes in hive weight. The analysis evolved over several milestones, incorporating different forecasting approaches, evaluation methods, and prediction horizons.

I developed the initial data processing and modeling pipeline, established much of the project's early analytical direction, and maintained the shared GitHub repository. As the project progressed, we collaborated on improving the methodology, with David contributing more advanced modeling and evaluation techniques.

The project was particularly valuable as an experience in iterative development. Our initial approach had limitations, and subsequent refinements demonstrated how much the choice of prediction horizon, baseline, and evaluation methodology can influence the interpretation of model performance.

**My contributions:** Initial pipeline development, data preparation, project coordination, repository management, and collaborative analysis.

**Key takeaway:** Building an initial working pipeline was only the beginning. Evaluating its limitations and incorporating improvements became an equally important part of the project.

### [Housing Price Regression](https://github.com/stephfn/housing-price-regression)

**Focus:** Regression modeling, dimensionality reduction, feature scaling, and model evaluation.

Explored how Principal Component Analysis (PCA) and feature selection affect linear regression models trained on housing data. The project used 1,460 observations and 229 encoded predictor features.

Revisiting the original notebook led me to investigate the relationship between feature scaling and PCA. The initial unscaled PCA approach performed poorly, while a later implementation using StandardScaler and PCA retained 127 components and achieved an R² of 0.841, compared with 0.648 for the baseline model.

The project also examined MinMaxScaler with variance threshold feature selection, demonstrating that different preprocessing methods serve different analytical purposes.

**Key takeaway:** Understanding the mathematical behavior of preprocessing methods is just as important as knowing how to implement them.

**Limitations:** Results are exploratory because some preprocessing steps occurred before the train/test split.

### [Pokémon Market Analytics](https://github.com/stephfn/pokemon-market-analytics)

**Focus:** API data collection, SQL, data cleaning, and market analysis.

Collected and analyzed Pokémon trading card data using an API, data preparation techniques, and SQL queries.

The project explored card characteristics and pricing information, demonstrating how external data sources can be collected, structured, and analyzed to investigate market-related questions.

It emphasizes data acquisition, organization, and querying as important parts of the analytical workflow.

### [Loan Prediction Pipeline](https://github.com/stephfn/loan-prediction-pipeline)

**Focus:** Classification, preprocessing pipelines, and hyperparameter tuning.

Developed a machine learning pipeline for loan prediction using data preprocessing, feature scaling, and a K-nearest neighbors classifier.

The project examined the importance of preparing data consistently and evaluating model configurations through hyperparameter tuning.

It demonstrates a structured approach to building and assessing a supervised classification workflow.

### [p53 Protein Structure Analysis](https://github.com/stephfn/protein-structure-folding-pipeline)

**Focus:** Structural biology, scientific computing, and molecular visualization.

Analyzed and visualized an existing p53 protein structure to explore structural characteristics such as residue distances, hydrophobicity, and spatial relationships.

The project applies computational analysis to biological structural data and demonstrates methods for investigating molecular features.

This is a structural analysis and visualization project rather than a system for predicting protein folding.

### [Classification and Feature Selection with Synthetic Data](https://github.com/stephfn/rna-seq-classification-pipeline)

**Focus:** Biological data simulation, classification, and feature selection.

Investigated machine learning classification and feature selection using a simulated gene-expression dataset.

The project compared modeling approaches and examined how selecting different features can influence classification performance.

The dataset is synthetic and does not represent actual patient RNA-seq measurements. The project is intended to demonstrate analytical methods relevant to high-dimensional biological data rather than make clinical or biological claims about real patients.

---

## Additional Work

My GitHub profile includes additional coursework, experiments, and ongoing projects related to data science, machine learning, and scientific computing.

[Browse all GitHub repositories](https://github.com/stephfn)

---

## Contact

I am interested in opportunities and collaborations involving applied data science, healthcare analytics, biotechnology, and scientific data.

You can explore my work and connect with me through the following platforms:

- [GitHub Profile](https://github.com/stephfn)
- LinkedIn: https://www.linkedin.com/in/stephanienord/

---

*Portfolio developed using GitHub Pages. Project descriptions reflect coursework, collaborative work, and independent technical exploration.*
