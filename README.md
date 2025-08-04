__Performance Evaluation of 16 Machine Learning Models__

__Using the Dry Bean Dataset__

__Overview__

This GitHub repository contains the final report and supporting Python modules for the analysis and comparison of 16 machine learning models applied to the Dry Bean dataset, which contains 13,611 records\.  This project focused on a supervised classification task and pursued two objectives: 

- Measure how accurately each model classifies unseen bean samples
- Determine each model’s runtime for its classification training and testing process\.

The project’s final report documents Dry Bean dataset characteristics, including standard summary statistics, feature\-level diagnostics such as the Confusion Susceptibility Score \(CSS\),  and feature correlation and redundancy analysis\.  The report also describes the tuning performed of selected hyperparameters for each model\. It presents model\-specific accuracy and runtime results, and it explores tradeoffs between performance and efficiency\.  The report concludes with a summary of model performances and feature\-level insights\.

__Project File Structure__

 ml\_benchmark/

- LICENSE
- Dry\_Bean\_Benchmark\_Final\_Report\.pdf
- README\.md   – Project documentation
- requirements\.txt   – Python package dependencies
- config\.py   – Centralized directory and file paths for project modules
- datasets/   – Raw Dry Bean dataset
- notebooks/   – Jupyter notebooks for each pipeline stage
- outputs/   – All output files from the pipeline
	- baseline\_results/   – Results for baseline models without hyperparameter tuning
	- clean\_data/   – Preprocessing outputs
	- curated\_data/   – Final model\-ready datasets
	- feature\_subsets/   – Feature analysis outputs
	- figures/   – Visualizations and plots
	- results/   – Benchmark results for tuned models
	- summary/   – Consolidated pipeline summaries
	- tuned\_models/   – Serialized tuned model objects
	- tuning/   – Hyperparameter tuning logs

__Key Features__

- Feature diagnosis and exploratory analyses, including feature importance and correlation and redundancy assessments
- Evaluation of 16 classification models, spanning seven algorithm families
- Stratified 5\-fold cross\-validation training and testing of each model
- Accuracy and runtime results, before and after tuning hyperparameters
- Accuracy of each model at predicting each bean type, and potential causes for performance anomalies
- Accuracy vs\. runtime tradeoff analysis
- Potential reasons for accuracy and runtime results for specific machine learning models
- Summary of tuning effects on model performance
- Model performance evaluation and feature relevance summaries\.

__Understanding the Code__

The project uses one central configuration model and ten Jupyter notebooks:

- config\.py: centralizes and defines all directory and file paths, ensuring consistent, portable, and maintainable path management across all project modules
- 01\_load\_and\_explore\.ipynb: Loads the Dry Bean dataset and performs initial data exploration and visualization
- 02\_diagnose\_feature\_quality\.ipynb: Analyzes feature distributions, missing values, and correlations to assess feature quality
- 03\_select\_feature\_subset\.ipynb: Select the feature subsets for analyses \(this project selected all 16 features\)
- 04\_curate\_and\_export\.ipynb: Scales the 16 numeric features, encodes the single class \(bean type\), and exports the curated dataset for subsequent modeling
- 04b\_baseline\_compare\_models\.ipynb: Benchmarks baseline performance of a selected model on the curated dataset without hyperparameter tuning, and stores the selected model’s results in an Excel file
- 05\_tune\_hyperparameters\.ipynb: Performs model\-specific hyperparameter tuning using GridSearchCV
- 06\_build\_model\_dict\.ipynb: Dynamically builds and saves a dictionary of trained model instances with their optimal hyperparameters
- 07\_compare\_models\.ipynb: Evaluates the performance of a single tuned model selected by the user across 137 combinations of dry bean features, including a runtime measurement approach designed to mitigate Windows management interruptions, populates an Excel file for the selected model, and adds the model’s confusion matrix to an Excel file that accumulates all models’ confusion matrices
- 08\_consolidate\_model\_comparison\_results\.ipynb: Merges results from all models into a single summary Excel file
- 09\_display\_results\.ipynb: Presents results and key findings all models into several combined summary charts and tables\.

__Running the Code__

To run the pipeline:

- Download the Dry Bean dataset from the source cited below, in either \.csv or \.xlsx format\.
- Clone or download this repository from GitHub\.
- Ensure Python 3\.10\+ and pip are installed\.
- \(Optional but recommended\) Create and activate a virtual environment\.
- Run “pip install \-r requirements\.txt” from the project root directory, to install all required packages\.
- Open a terminal and navigate to the project directory \(e\.g\., cd C:/Misc/ml\_benchmark\)\.
- Launch JupyterLab or Jupyter Notebook\.
- In the Jupyter interface, open the [notebooks](vscode-file://vscode-app/c:/Users/Ed's%20HP%20Envy/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) folder\.
- Update the PROJECT\_BASE variable in config\.py to match your machine’s file path \(e\.g\., Path\("C:/Your/Path/ml\_benchmark"\)\)\.
- Ensure the expected subfolders exist \(e\.g\., for the Dry Bean dataset, 10 \.ipynb files \(i\.e\., the notebooks\)\) or create them\.
- Run the notebooks in order, starting with 01\_load\_and\_explore\.ipynb and proceeding through 09\_display\_results\.ipynb\.
- In each notebook:
	- Read the introductory markdown cell\(s\) for context and instructions\.
	- Run all code cells sequentially from top to bottom \(use "Run All" or "Run All Above/Below" as needed\)\.
	- Confirm that dependencies from earlier stages have executed successfully \(most notebooks depend on outputs from a previous stage\)\.
- Review the outputs, figures, and exported files in the [outputs](vscode-file://vscode-app/c:/Users/Ed's%20HP%20Envy/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) directory as you progress\.
- If making changes to [config\.py](vscode-file://vscode-app/c:/Users/Ed's%20HP%20Envy/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html), restart the notebook kernel and re\-import the config module to ensure path changes take effect\.
- For troubleshooting, consult the README or review error messages in the notebook output cells\.

__Citation__

Dataset Source: University of California, Irvine \(UCI\) Machine Learning Repository: [https://doi\.org/10\.24432/C50S4B](https://doi.org/10.24432/C50S4B) \.

Reference Study: KOKLU, M\. and OZKAN, I\.A\., \(2020\), “Multiclass Classification of Dry Beans Using Computer Vision and Machine Learning Techniques\.” Computers and Electronics in Agriculture, 174, 105507\. DOI: [https://doi\.org/10\.1016/j\.compag\.2020\.105507](https://doi.org/10.1016/j.compag.2020.105507) \.

Note: Dry bean abbreviations used by this benchmarking project follow the naming conventions established by Koklu and Ozkan\.

__License__

This project is licensed under the MIT License\.  Refer to the “LICENSE” file for details\.

__Contact Information__

For questions or suggestions, feel free to contact:

- Name: Ed Kaempf
- Email: [edkaempf@gmail\.com](mailto:edkaempf@gmail.com) 
- GitHub: github\.com/EofK 
- Linkedin: [https://www\.linkedin\.com/in/ed\-kaempf\-4887839b/](https://www.linkedin.com/in/ed-kaempf-4887839b/) 

