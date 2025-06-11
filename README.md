# HrFlow - Technical Test: Job Crawler

This project was developed as part of a **technical test for the company HrFlow**.

The objective is to design a crawler capable of scraping job offers from the **France Travail platform (formerly Pôle Emploi)** and automatically injecting them into a HrFlow board via their API.

## 📄 Description

The project is structured as a Jupyter Notebook:  
- `crawler.ipynb`

The script performs the following steps:

1. **HrFlow API Connection**
   - Uses the HrFlow SDK to interact with the job storage API.
   - Loads API keys from a local `.env` file.

2. **Dynamic Web Scraping with Selenium**
   - Automatically opens the France Travail website.
   - Navigates through the different job categories.
   - Extracts complete job offer information:
     - Title, description, responsibilities, requirements, skills, company, contract type, working hours, salary, etc.

3. **Geocoding with Geopy**
   - Retrieves geographic coordinates from extracted addresses.

4. **Injection into HrFlow**
   - Transforms the extracted data into JSON formatted according to HrFlow specifications.
   - Uploads the offers to a HrFlow board using `job.storing.add_json()`.

## 🔧 Technologies Used

- Python 3.x
- Jupyter Notebook
- HrFlow Python SDK (`hrflow`)
- Selenium
- Geopy
- Dotenv
