# Clone and Fake App Detection

## Project Overview
The **Clone and Fake App Detection** project is a Python-based GUI application built to identify malicious, fake, or cloned Android applications (.apk files). By analyzing the inner structures of APK files, querying security databases, and examining permissions and certificates, the application gives users a straightforward verdict on the safety of the scanned application. 

**Dataset Link:** 
*N/A - This project conducts dynamic scanning of user-provided `.apk` files rather than training on a static dataset.*

## Features
- **APK Hashing:** Automatically generates a SHA-256 hash of the selected APK file.
- **Metadata Extraction:** Gathers critical APK data including Package Name, Version, Permissions, and Certificates.
- **VirusTotal Integration:** Cross-references the generated SHA-256 hash with the VirusTotal API database to check for previously identified malware.
- **Fake/Clone Indicators:** Checks for common indicators of malicious intent (e.g., suspicious permissions like `SEND_SMS` or missing valid certificates).
- **Data Logging:** Exports all scan results securely to a local CSV file (`appScan.csv`) for record-keeping and further analysis.

## Technologies Used
- **Python 3**
- **CustomTkinter:** Used for building a modern, dark-themed GUI.
- **Androguard:** Used for in-depth reverse engineering and metadata extraction of APK files.
- **Cryptography:** Used to process and decode DER-encoded X.509 certificates from the APK.
- **Requests:** Used for making API calls to VirusTotal.
- **Pillow (PIL):** Used for rendering UI images/assets.

## Setup and Installation Instructions

1. **Install Dependencies:**
   Ensure you have Python installed, then install the required libraries using the `requirements.txt` file:
   ```bash
   pip install -r requirements.txt
   ```

2. **API Key Setup:**
   The project uses the VirusTotal API. Ensure that the `VIRUSTOTAL_API_KEY` variable inside the `.ipynb` file or `key.py` configuration is populated with a valid API key. (A default key is currently provided in the code).

3. **Assets:**
   If you wish to use the aesthetic wallpaper in the GUI, ensure that a file named `wallpaper.jpg` is located in the same directory as the notebook/script. If missing, the app will safely ignore it and continue working.

## How to Run
1. Open the provided `.ipynb` file (`LokeshPoudyal_CloneAndFakeAppDetection.ipynb`) in Jupyter Notebook or JupyterLab.
2. Run all the cells sequentially. The final cell contains the execution command (`app.run()`), which will launch the Tkinter GUI.
3. In the GUI:
   - Enter a **Scan Name**.
   - Click **Browse APK** to select a `.apk` file from your local machine.
   - Click **Start Scan** to begin the analysis.
   - Review the results displayed in the text box. The output will also be saved to a `appScan.csv` file automatically.