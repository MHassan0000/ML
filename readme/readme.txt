ML LAB: QUICK STEPS

The lab PC already has Python and Jupyter Notebook. No JupyterLab or virtual
environment is needed. Use prepared code only if your instructor permits it.
Run terminal commands in Command Prompt or PowerShell, not notebook code cells.

WHILE INTERNET IS AVAILABLE

1. Download the workspace:

   git clone https://github.com/MHassan0000/ML.git
   cd ML

   If Git is unavailable, use GitHub > Code > Download ZIP, extract it, and open
   a terminal inside the extracted folder. If already downloaded, use that folder.

2. Install dependencies once, before internet is disconnected:

   python -m pip install -r requirements.txt

   Or install the packages directly instead:

   python -m pip install numpy pandas "scikit-learn>=1.3,<2" joblib nbconvert

   These install the libraries, not JupyterLab. Use Python 3.10 or newer.

3. Start Jupyter Notebook from the workspace root:

   jupyter notebook

   Keep this terminal open while working in the browser.
   If Notebook is already open in the browser, no launch command is needed.
   Run a notebook with the bundled practice data to check installation NOW.
   If imports fail despite installation, the kernel may use another Python.
   While still online, run this once in a temporary notebook code cell:

   %pip install numpy pandas "scikit-learn>=1.3,<2" joblib nbconvert

   Restart the kernel afterward and remove that installation cell so it does
   not run during the offline exam. No downloads should be needed after setup.

DURING THE EXAM

4. Read your allocation: algorithm(s), input columns, target column, and K.
   One algorithm: open its folder's notebook, e.g. decision_tree/decision_tree.ipynb.
   Multiple algorithms: open comparison/comparison.ipynb. Change its classifier
   imports and classifiers dictionary to your allocation. Copy the required
   import and classifier constructor from each assigned algorithm's notebook.
   Keep the general imports for pandas, preprocessing, evaluation, and saving.
   The comparison notebook starts with decision tree, AdaBoost, and LDA.

5. Put the actual exam CSV in the chosen folder's data subfolder.
   Example: decision_tree/data/patients.csv.
   For multiple algorithms, use comparison/data/patients.csv.

6. Edit the second code cell. Example for the sample paper:

   CSV_FILE = "data/patients.csv"
   TARGET = "stroke"
   FEATURES = ["age", "heart_disease", "bmi", "smoking_status"]
   FOLDS = 10
   NEW_DATA_FILE = "data/new_patients.csv"

   Replace these values with YOUR paper's exact names and allocation.
   Leave CATEGORICAL_COLUMNS empty for the paper's already encoded numbers.
   Text categories are handled automatically. Change CSV_OPTIONS only if needed.
   The classifier is already selected in each individual algorithm's notebook.

7. Put the two genuinely new instances in data/new_patients.csv.
   Include a header with all selected input names; no target column is needed.
   Use the same units and category codes as training.
   If new instances have not been supplied yet, set NEW_DATA_FILE = None.

8. At the top of the open notebook, click Kernel > Restart & Run All and confirm.
   It may be called Restart Kernel and Run All Cells in newer versions.
   If unavailable, use Kernel > Restart, then Cell > Run All or Run > Run All Cells.
   Wait for every cell to finish. No separate training command is needed.
   Check for errors. Each target class needs at least FOLDS examples.
   Do not change the assigned K or algorithm just to bypass an error.

9. Check the answers against the questions:
   Q1: Shape, first five rows, missing values, class counts.
   Q2: Every fold's accuracy for each assigned algorithm.
   Q3: Confusion matrices from held-out predictions.
   Q4: Average accuracy; the comparison notebook ranks the assigned algorithms.
   Q5: Full-data fit, saved/reloaded pipeline, and predictions for the new rows.

   The chosen folder's results directory contains best_model.pkl and result CSVs.
   Add your own interpretation wherever the question asks for an explanation.

10. Save the executed notebook with your required registration/name using Ctrl+S.
    If PDF is required, open a SECOND terminal in the workspace root and run:

    jupyter nbconvert --to html "decision_tree/FA24-BSE-082.ipynb"

    Replace the path with your saved notebook's actual path.
    Open the HTML in a browser, then Print > Save as PDF. Check the tables.
    Submit exactly the files requested by your instructor.

These notebooks are for tabular classification, not continuous-price regression.
CSV size is limited by the lab PC's memory and training time, not a fixed row count.
The bundled stroke CSVs are artificial practice data, not the real exam dataset.
