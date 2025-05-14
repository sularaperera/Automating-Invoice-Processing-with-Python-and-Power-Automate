<img src="https://github.com/sularaperera/Automating-Invoice-Processing-with-Python-and-Power-Automate/blob/main/Images/Banner%20Full.png"></img>

# Automating Invoice Processing with Python and Power Automate

As a System Analyst, I constantly look for ways to streamline processes and improve efficiency. One of the biggest challenges we face is handling a large volume of supplier invoices.

## Problem Statement

We receive a large number of invoices from suppliers, which need to be verified against stock purchase orders in our inventory. This process is:

🔹 Currently, our team loads invoices, cross-checking the invoiced stock against the received stock in our inventory system.

🔹 This process involves opening each invoice, searching for the corresponding purchase order, and validating the details.

🔹 It's time-consuming, repetitive, and prone to human errors, leading to inefficiencies and potential mismatches.

## To solve this, I designed an automated invoice processing system. This system:

✅ Extracts invoice details from PDFs using OCR

✅ Matches invoices with purchase orders from inventory

✅ Formats the data for accounting systems like Xero

✅ Renames invoices using actual invoice numbers

## The Solution

Leveraging my programming, and accounting skills, I analyzed the entire process and developed an automation system that significantly reduces manual effort.


## How It Works

✅ Step 1: Automating Invoice Collection – A Power Automate Flow downloads all incoming invoice PDFs from emails into a designated folder.

✅ Step 2: Extracting Key Information – A Python script scans each invoice, extracting critical details like Invoice Number, PO Number, Invoice Date, and Total Amount using OCR and Regex.

✅ Step 3: Matching with Inventory – The script cross-references invoices with our inventory records, ensuring that the billed stock aligns with received stock.

✅ Step 4: Formatting for Xero – The extracted data is structured into a CSV file compatible with Xero, making it easy to import and process invoices.

✅ Step 5: Organizing Files – The script renames invoice PDFs using actual invoice numbers, improving file management.


## 1. Downloading Invoices from Email (Power Automate Flow)

A Power Automate Flow automatically downloads all incoming invoice PDFs and saves them in a designated folder

<img src="https://github.com/sularaperera/Automating-Invoice-Processing-with-Python-and-Power-Automate/blob/main/Images/Power_Automate.png"></img>


## 2️. Extracting Invoice Data (Python & PDF Parsing)

The Python script scans all PDF invoices in the folder and extracts key details using regex patterns:

- Invoice Number

- Purchase Order (PO) Number

- Invoice Date

- Subtotal Amount

## Key Technologies Used:

pdfplumber → Extracts text from PDFs

re (Regex) → Identifies invoice details

pandas → Stores extracted data in a structured format


## 3️. Matching Invoices with Inventory Data

The extracted invoice details are cross-referenced with a CSV file containing inventory records. This ensures that: 

✅ The invoice corresponds to a valid purchase order 

✅ The correct warehouse location is identified


## 4️. Formatting Data for Xero Accounting System

To simplify invoice entry into Xero, the script generates a structured CSV file in Xero’s required format. The output includes:

- Supplier Name

- Invoice Number

- Invoice Date

- Due Date

- Description

- Quantity

- Unit Price

- Tax Type

- Warehouse Location

## Key Process:

- The script maps warehouse codes (AKL, WLG, CHC) to full location names (Auckland, Wellington, Christchurch).

- The final CSV file is saved as {supplier}_to_xero.csv, ready for import into Xero.

## 5️. Renaming Invoices with Actual Invoice Numbers

To keep files organized, the script renames each invoice PDF based on the extracted invoice number.

Example: 📄 randomfile.pdf → 🏷️ 123456 - PO-78910.pdf


## Key Benefits of This Automation

- Eliminates manual data entry – Reducing human effort and freeing up valuable time.

- Enhances accuracy – Minimizing errors in stock reconciliation.

- Improves efficiency – Speeding up invoice processing and purchase order verification.

- Better file organization – Making invoices easy to track and retrieve.


## Invoice Processing Automation for Supplier PDFs

This project automates the extraction and transformation of key data from supplier invoice PDFs to streamline accounting workflows. The goal is to generate a CSV file ready for direct upload into Xero accounting software.

### Process Overview
For each invoice PDF, the script automatically extracts the following fields:

- Tax Invoice Number

- Invoice Date

- Order Number – A 5-digit number in the invoice, automatically prefixed with "PO-" to match the format used in our inventory system (e.g., PO-12345).

- Total Excluding GST

<img src="https://github.com/sularaperera/Automating-Invoice-Processing-with-Python-and-Power-Automate/blob/main/Images/sample_invoice_new.png"></img>
<img src="https://github.com/sularaperera/Automating-Invoice-Processing-with-Python-and-Power-Automate/blob/main/Images/python_code_v1_.png"></img>

### Refactored Version
Here’s a cleaned-up and modular version of the script

#### Key Improvements:
- Modular structure: Each part of the workflow is encapsulated in a function.
- Robustness: Added error handling and logging.
- Scalability: Easier to add new features (like new fields or formats).
- Readability: Organized flow from config to execution.
- Clean CSV and file renaming logic.

<img src="https://github.com/sularaperera/Automating-Invoice-Processing-with-Python-and-Power-Automate/blob/main/Images/python_code_v2_refactored_version.png"></img>

## Final Output

After processing all invoice PDFs, the script compiles the extracted and formatted data into a standardized CSV file that aligns with Xero's import requirements. This eliminates manual data entry, reduces errors, and ensures seamless integration with existing inventory and accounting systems.

<img src="https://github.com/sularaperera/Automating-Invoice-Processing-with-Python-and-Power-Automate/blob/main/Images/csv_file_upload_to_xero.png"></img>

<hr></hr>

# Project Conclusion
### Overview
This project automates the extraction, validation, and formatting of invoice data from PDF files and cross-references them with inventory records. By using Python, PDF parsing (pdfplumber), regular expressions, and pandas, it streamlines a previously manual and error-prone process into a fully automated workflow.

### Business Impact
Time Savings : Previously, staff spent 2 to 3 minutes per invoice reading, checking POs, and entering data into accounting software. Now, hundreds of invoices can be processed in seconds with a single script execution.

Reduced Errors : Ensures only valid purchase orders are processed, reducing the risk of incorrect stock reordering or accounting mismatches.

Regex validation: Eliminates inconsistencies from human error (typos, missing fields, date mismatches).

Improved Data Consistency : Uses a uniform format for all invoices going into the accounting system.

Clear PDF naming improves file organization.






