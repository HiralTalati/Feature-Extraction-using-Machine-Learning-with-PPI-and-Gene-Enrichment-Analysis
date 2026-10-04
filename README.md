**Machine Learning Regression Modeling for Gene Expression Prediction and Protein- Protein Interaction along with Gene Enrichment Analysis**

This repository contains a Python-based bioinformatics and machine learning pipeline executed within a Jupyter Notebook environment. The workflow focuses on predicting key clinical/statistical metrics (such as logFC or B statistics) derived from differential expression analysis using a variety of machine learning regressors. It includes model evaluations, feature importance extraction, Protein-Protein Interaction (PPI) network mapping, and Functional Enrichment Analyses (Gene Ontology and KEGG Pathways).

📌 Features

• Multi-Model Regression Framework: Evaluates and compares five distinct machine learning regression architectures:
	
  • Linear Regression
  
	• Decision Tree Regressor
	
  • Random Forest Regressor
	
  • Gradient Boosting Regressor
	
  • K-Nearest Neighbors (KNN) Regressor

• Feature Importance Evaluation: Leverages Random Forest configurations to isolate and quantify the predictive weight of biological features (AveExpr, t, P.Value, adj.P.Val).

• Absolute Value Stratification: Dynamically isolates the top 50 unique gene nodes based on the absolute value of predicted regressions to pinpoint robust biomarker signatures.

• Programmatic PPI Network Generation: Interfaces with the STRING DB API using Python requests to map interactions, prune isolates, and scale network node structures based on normalized Degree Centrality.

• Functional Annotation & Enrichment: Integrates with the Enrichr API via gseapy to automate functional profiling across three core domains:
	
  • GO Biological Process (BP)
	
  • GO Molecular Function (MF)
	
  • GO Cellular Component (CC)
	
  • KEGG Human Pathways

🛠️ Tech Stack & Dependencies

The computational pipeline is written in Python 3 and optimized for execution in Jupyter Notebooks or Google Colab.

📂 Input Configurations & Schema

The script expects a structured differential expression matrix file containing symbol, Avgexpr, t value, P value, Adj P value and LogFC value

🚀 Execution Workflow

1. Model Calibration
   
Modify the target parameter string block in the script layout to swap between predicting logFC or B.

2. Feature Training
   
Data frames are partitioned using a 70/30 training/testing split configuration. Cross-validation performance is measured and printed via Mean Squared Error (MSE) and Coefficient of Determination (R² score).

3. Pipeline Run Execution

📊 Automated Output Assets

The notebook automatically outputs the following diagnostic plots and files directly into your runtime directory:

• top_50_unique_genes.csv: Target file containing the filtered multi-group entries for the top 50 unique identified gene signatures.

• genes_in_top_kegg_pathways.csv: Map cross-linking enriched unique gene nodes with their respective highly significant KEGG human pathways.

• ppi_network_high_res.png: Publication-ready, 300 DPI high-resolution spatial layout of the Protein-Protein Interaction network, color-coded by degree centrality.

• Functional Bar Plots: Automatically saves top enrichment terms such as top_go_biological_process_2023_terms.png.

📄 License

This analysis framework is open-source and distributed under the MIT License.
