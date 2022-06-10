Voter Categorization Model (VCM) uses n-grams to extract most frequent phrases and a key-word search to categorize unlabeled voters. 

The model can run on either a pre-established rule file (use 1a and 2a) or it can extract N-Grams from data (use 1b and 2b). The output files from the two algorithms are then inputted into the VCM model (3) and the rules combined. The VCM results are compared against Rupali's ML data in Model Comparison (4).


## **Files**
- (1a) Rule Training.ipynb
  - analyzes rules and determines % accuracy from labeled data training
  - **input** -- Affiliation Rules.csv, Labeled.csv
  - **output** -- Rule Analysis.csv
- (2a) Rule Analysis.ipynb
  - analyzes rule data using VCM on labeled data
  - parameters (2) : rule certainty, model categorization certainty
  - **input** -- Rule Analysis.csv, Labeled.csv
  
- (1b) N-Grams Creation.ipynb
  - extracts and counts the frequency of phrases found in the input data
  - parameter : frequency cutoff for n-gram to be a valid rule
  - **input** -- Unlabeled Data.csv
  - **output** -- N-Grams Data.csv
- (2b) N-Grams Training + Analysis.ipynb
  - analyzes n-gram data and determines % accuracy from labeled data training
  - **input** -- N-Grams Data.csv, Labeled.csv
  - **output** -- N-Gram Analysis.csv
  
- (3) Voter Categorization Model.ipynb
  - classifies unlabeled users using both rule analysis and n-gram analysis data (consolidates both datasets)
  - parameters (2) : rule certainty, model categorization certainty
  - **input** -- N-Gram Analysis.csv, Rule Analysis.csv, Unlabeled Data.csv
  - **output** -- VCM Categorization Data.csv
- (4) Model Comparison.ipynb
  - compares results of VCM model and Rupali's ML models on unlabeled user data
  - validates users labeled the same by both models
  - **input** -- VCM Categorization Data.csv, Rupali ML Data.csv
  - **output** -- Model Comparison Voter Data.csv
