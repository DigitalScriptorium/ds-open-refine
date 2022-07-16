# Instructions for installing and running FAST reconciliation service in OpenRefine

## Download GitHub repository for FAST reconciliation service

https://github.com/cmharlow/fast-reconcile

## Download and install Python version 2.7.18

https://www.python.org/downloads/release/python-2718/

*Although the documentation explains the reconciliation service will work with Python 3, the DS team found that the service would only work with a 2.x version.*

## Follow instructions (found through the above GitHub repository for running FAST reconciliation service through OpenRefine)

1. Open command line interface
2. Navigate to file directory location for the `fast-reconcile` repository files on your local machine: `cd c:\path\to\fast-reconcile`
3. Install requirements: `pip2.7 install -r requirements.txt`
4. Run and debug reconcile.py: `python reconcile.py --debug`
5. Open/Run OpenRefine
6. Click on down arrow of column to be reconciled
7. From drop-down menu, choose `Reconcile` -> `Start reconciling`
8. In the reconciliation service pop-up window, click the `Add Standard Service...` button
9. Enter URL for the reconciliation service running locally (should run at `http://0.0.0.0:5000/`)
11. Select `Fast Reconciliation Service` from options in the left-hand `Services` column of pop-up window
12. Select reconciliation parameters and preferences (e.g., entity types, details from other columns)
13. Click `Start Reconciling...` button to begin reconciliation
