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

Explored how Principal Component Analysis (PCA) and feature selection affect linear regression models using the Ames housing dataset. The analysis used 1,460 observations and produced 227 encoded predictors after preprocessing.

Revisiting the original notebook led to corrections in the preprocessing workflow and a closer examination of how feature scaling affects PCA. The baseline linear regression achieved an R² of 0.8786, while StandardScaler followed by PCA retained 127 components and achieved an R² of 0.8409.

The project also compared unscaled PCA and MinMaxScaler with variance threshold feature selection. Both reduced dimensionality substantially but performed worse than the baseline.

**Key takeaway:** Dimensionality reduction does not necessarily improve predictive performance, and understanding how preprocessing methods work is essential when interpreting model results.

**Limitations:** Results are based on a single train/test split without cross-validation or hyperparameter optimization.

### [Pokémon Market Analytics](https://github.com/stephfn/pokemon-market-analytics)

**Focus:** API integration, web data extraction, SQLite, SQL joins, and exploratory market analysis.

Developed a multi-source data analysis workflow combining Pokémon battle statistics, PokéAPI attributes, and trading card marketplace pricing information. The project used Python for data cleaning and standardization, SQLite for relational data integration, and SQL joins to construct a consolidated analytical dataset.

The final integrated dataset contained 60 records and nine variables. Exploratory visualizations examined average card prices by Pokémon type, rarity classification, and seller country, as well as the relationship between battle statistics and marketplace pricing.

**Key takeaway:** Integrating datasets from different sources requires consistent identifiers and careful interpretation of analytical results.

**Limitations:** The analysis uses a limited sample of marketplace records and does not establish causal relationships between Pokémon characteristics and card values. Two required source CSV files are not included in the repository.

### [Loan Prediction Pipeline](https://github.com/stephfn/loan-prediction-pipeline)

**Focus:** Classification, preprocessing pipelines, hyperparameter tuning, and model comparison.

Developed scikit-learn classification pipelines to predict loan approval outcomes using applicant and financial information. The project initially evaluated K-Nearest Neighbors (KNN), then expanded to compare KNN, Logistic Regression, and Random Forest using five-fold cross-validation.

The default KNN classifier achieved 78.12% accuracy, increasing to 79.17% after tuning. The expanded model search selected Logistic Regression with a regularization parameter of C = 10, achieving 82.29% test accuracy.

**Key finding:** Expanding the comparison beyond a single algorithm produced a greater observed improvement than tuning KNN alone.

**Limitations:** Results are based on one train/test split, complete-case data, and accuracy as the primary evaluation metric. Additional class-level and fairness evaluation would be necessary for a real lending application.

### [p53 Protein Structure Analysis](https://github.com/stephfn/protein-structure-folding-pipeline)

Analyzed the experimentally determined p53 DNA-binding domain (PDB 1TUP) using Python and Biopython. Developed interactive 3D visualizations, residue-distance matrices, nonlocal spatial contact analysis, and sequence-based biophysical profiles. The project demonstrates computational protein structure characterization rather than protein folding prediction.

### [Classification and Feature Selection with Synthetic Data](https://github.com/stephfn/rna-seq-classification-pipeline)

**Focus:** Synthetic biological data, supervised classification, ANOVA feature selection, and model evaluation.

Explored how feature selection affects classification performance using a synthetic dataset containing 500 observations, 100 gene-labeled numerical features, and three target classes.

The project compared Gaussian Naive Bayes, L1- and L2-regularized Logistic Regression, and Gradient Boosting. ANOVA F-test feature selection reduced the predictor space from 100 to 20 features. After selection, Gaussian Naive Bayes accuracy increased from 61% to 64%, while Gradient Boosting improved from 63% to 66%.

**Key finding:** Feature selection produced modest improvements for both evaluated classifiers, demonstrating the tradeoff between reducing dimensionality and preserving predictive information.

**Limitations:** The data were generated using scikit-learn rather than obtained from actual RNA-seq experiments. Results are based on one train/test split and do not establish biological relevance or generalizability to real gene-expression datasets.

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
