ML LAB: QUICK STEPS

Use Jupyter Notebook, not JupyterLab. The existing notebooks work unchanged.
Run the commands below in a Windows terminal, not in notebook code cells.

BEFORE THE EXAM

1. Prepare the workspace before internet access is unavailable.
   Only use prepared code if your instructor permits it.
   On another machine, clone after these files have been pushed to GitHub:

   git clone https://github.com/MHassan0000/ML.git
   cd ML

   If you already have this workspace, open a terminal in its root folder.

2. Install once, using Python 3.10 or newer. Skip this if everything is provided:

   python -m venv .venv
   .\.venv\Scripts\python.exe -m pip install notebook numpy pandas "scikit-learn>=1.3,<2" joblib nbconvert

3. Start Jupyter Notebook and practise running a notebook:

   .\.venv\Scripts\python.exe -m notebook

   Keep the terminal open. If the exam computer provides its own installation,
   use this command instead:

   jupyter notebook

   If Notebook is already open in the browser, no launch command is needed.
   Do not rely on cloning or installing packages during an offline exam.

DURING THE EXAM

4. Read your allocation: algorithm(s), input columns, target column, and K.
   One algorithm: open its folder's notebook, e.g. decision_tree/decision_tree.ipynb.
   Multiple algorithms: open comparison/comparison.ipynb. Change its classifier
   imports and classifiers dictionary to your allocation; README.md lists choices.
   Keep the general imports for pandas, preprocessing, evaluation, and saving.

5. Put the actual exam CSV in the chosen folder's data subfolder.
   Example: decision_tree/data/patients.csv.
   The bundled stroke CSVs are artificial practice data, not your exam dataset.

6. Edit the second code cell. Example for the sample paper:

   CSV_FILE = "data/patients.csv"
   TARGET = "stroke"
   FEATURES = ["age", "heart_disease", "bmi", "smoking_status"]
   FOLDS = 10
   NEW_DATA_FILE = "data/new_patients.csv"

   Replace these values with YOUR paper's exact names and allocation.
   Leave CATEGORICAL_COLUMNS empty for the paper's already encoded numbers.
   Text categories are handled automatically. Change CSV_OPTIONS only if needed.

7. Put the two genuinely new instances in data/new_patients.csv.
   Include a header with all selected input names; no target column is needed.
   Use the same units and category codes as training.
   If new instances have not been supplied yet, set NEW_DATA_FILE = None.

8. Select Kernel > Restart & Run All (wording varies by Notebook version).
   Wait for every cell to finish. No separate training command is needed.
   Check for errors. Each target class needs at least FOLDS examples.
   Do not change the assigned K or algorithm just to bypass an error.

9. Check the answers against the questions:
   Q1: Shape, first five rows, missing values, class counts.
   Q2: Every fold's accuracy for each assigned algorithm.
   Q3: Confusion matrices from held-out predictions.
   Q4: Average accuracy; comparison table if multiple algorithms are assigned.
   Q5: Full-data fit, saved/reloaded pipeline, and predictions for the new rows.

   The chosen folder's results directory contains best_model.pkl and result CSVs.
   Add your own interpretation wherever the question asks for an explanation.

10. Save the executed notebook with your required registration/name using Ctrl+S.
    If PDF is required, export HTML from a terminal in the workspace root:

    jupyter nbconvert --to html "decision_tree/FA24-BSE-082.ipynb"

    Replace the path with your saved notebook's actual path. If using the local
    .venv installation instead of the provided exam environment, run:

    .\.venv\Scripts\python.exe -m nbconvert --to html "decision_tree/FA24-BSE-082.ipynb"

    Open the HTML in a browser, then Print > Save as PDF. Check the tables.
    Submit exactly the files requested by your instructor.

These notebooks are for tabular classification, not continuous-price regression.
