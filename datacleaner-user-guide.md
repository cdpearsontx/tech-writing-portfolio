# DataCleaner User Guide 

## Key Features:
- Removes duplicate entries
- Formates data into reable tables
- Detects and fixes commons errors in CSV files
 
---

## Installation 
To install **DataCleaner**, run the following command in your terminal:

```bash
pip install datacleaner
```
To verify the installation, type:

```
datacleaner --version
```

---
## Usage
To clean a CSV, use:
```bash
  datacleaner clean myfile.csv
```
This will:
 - Remove duplicate rows
 - Fix missing values
 - Standardized column formatting

For help, type:

```
datacleaner --help
```
| Command | Description |
| ----------- | ----------- |
| datacleaner --remove-duplicates | Removes all duplicate rows|
| datacleaner --fix-errors | Fixes common formatting errors |
| datacleaner --export newfile.csv| Saves cleaned data to a new file |

---
## FAQ
 **1. What file types does DataCleaner support?**

Currenly, DataCleaner supports:
- CSV files
- TSV (Tab-Seperated Values) files
- Excel files (Beta feature)

## **2. How do I uninstall DataCleaner?**
Use the following command:
```bash
pip uninstall datacleaner
```
### **Conclusion**
**DataCleaner** is a simple yet powerful tool for handling messy CSV files. Try it today and streamline your data workflow!


For more detail, visit our [official documentation](https://https://cdpearsonwrites.wordpress.com/). 
