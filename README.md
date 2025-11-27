Crime Reporting Assessment - Overview and Instructions
-----------------------------------------------------

Files included:
- crime_reports.db        : SQLite database (100 individuals, ~200 cars, 150 reports, 50 investigators)
- crime_assessment.ipynb  : Jupyter notebook with 10 analytical questions and SQL scripts using %%sql magic
- crime_assessment.zip    : This ZIP file containing the above files

Goal:
Students will explore a small crime reporting database (vehicle theft reports) and answer
analytical questions using SQL inside a Jupyter notebook. The notebook uses the %%sql cell magic
to run SQL queries directly against the provided SQLite database.

General Instructions:
1. Download and unzip the files so that crime_reports.db and crime_assessment.ipynb are in the same folder.
2. Launch Jupyter (or JupyterLab) in that folder.
3. Install the ipython-sql extension if not already installed:
   - In a notebook cell run: !pip install ipython-sql sqlalchemy
   - Then load the extension: %load_ext sql
4. The notebook cells use the cell magic like:
   %%sql sqlite:///crime_reports.db
   SELECT count(*) FROM individuals;
   This connects to the local SQLite DB file in the same directory as the notebook.
5. Work through each question in the notebook. Each question contains:
   - a short description
   - the SQL query (%%sql cell) that answers it
   - explanation of the result and expected learning outcomes
6. Save your changes in the notebook; NBGrader can be configured to grade SQL outputs
   produced by the %%sql cells if your NBGrader assignment is set to allow SQL cell outputs.

Notes:
- The database contains timestamps in 'created_at' and 'reported_at' columns.
- Some reports have no investigator assigned (investigator_id IS NULL) — status 'Not Assigned'.
- Use JOINs, GROUP BY, HAVING, subqueries, CTEs, and window functions (ROW_NUMBER) as requested.
- The notebook does not run the queries at creation time — it's prepared for students to run them in their environment.

Have students refer to the markdown comments inside the notebook for hints and grading expectations.
