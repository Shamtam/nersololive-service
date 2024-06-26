# About

Node script to monitor for live timing file changes and upload the parsed results for browsing.

# Requirements

-   Node
-   Azure Blob Storage account

# Day Of Event Instructions For Work/Run

1. In AxWare, save the Heat Assignments to the live timing drop folder.
2. Make sure it is named `heats.htm`.
3. This must be done prior to starting the live timing service.

# Timing laptop setup

1. Install node.js: https://nodejs.org/en/ (LTS)
2. Download/clone this repository
3. Open a Windows Explorer window to the `dist` directory.
4. Create a `.env` file with the contents listed under the Local Development section
    - The `RESULTS_FILE_LOCATION` should be the live timing results output path from AxWare.
    - The `RUN_WORK_FILE_LOCATION` should be the heat assignments output path from AxWare.
    - The `CLASSDEFS_FILE_LOCATION` should be the class definitions text file path used by AxWare.
    - Use forward slashes `/` in the filepaths.
    - Ensure all paths are absolute paths.
5. Open a command prompt in the `dist` directory.
6. Run the script with `node index.js`

# Local Development

1. Run `npm install`
2. Create a .env file with the following content:

```
RESULTS_FILE_LOCATION="test-data/results_live.html"
RUN_WORK_FILE_LOCATION="test-data/heats.htm"
CLASSDEFS_FILE_LOCATION="test-data/classes.txt"
AZURE_STORAGE_CONNECTION_STRING="<azure blob storage connection string>"
AZURE_STORAGE_CONTAINER_NAME="<azure blob storage container name>"
CLASS_RESULTS_UPLOAD_NAME="class.json"
PAX_RESULTS_UPLOAD_NAME="pax.json"
RECENT_RESULTS_UPLOAD_NAME="recent.json"
RUN_WORK_RESULTS_UPLOAD_NAME="runwork.json"
```

3. To start a local server, run `npm run buildAndRun`
