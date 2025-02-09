# **User Guide: How to Convert Markdown to PDF Using Pandoc**
*A step-by-step guide to converting Markdown files to professional PDFs using Pandoc and LaTeX.*

## **Introduction**
Markdown is a lightweight markup language used for formatting text in a simple and structured way. When combined with Pandoc, Markdown can be converted into high-quality PDFs with custom formatting. This guide will walk you through the steps to install Pandoc, configure it for PDF conversion, and apply custom formatting.

## **Prerequisites**
Before starting, ensure you have the following installed on your system:

**Required Software**

- Pandoc (For converting Markdown files)
- MikTex or TeX Live (for LaTeX-based PDF generation)
- A Markdown Editor (such as Visual Studio Code)

\noindent\rule{\textwidth}{0.4pt}

### **Step 1: Install Pandoc**

1. Visit the [Pandoc website](https://pandoc.org/installing.html). 
2. Download and install the latest version for your operating system.
3. Verify installation by running the following comman in the terminal:

`pandoc -- version`

If installed correctly, it will display the installed Pandoc version. 

\noindent\rule{\textwidth}{0.4pt}

### **Step 2: Install LaTeX Distribution**

Pandoc relies on a LaTeX engine like MikTeX (Windows) or Tex Lie (Mac/Linux) to generate PDFs

- **Windows Users:** Install MikTeX from [miktex.org](https://miktex.org/)
- **Mac/Linux Users:** Install TeX Live using: 

`sudo apt install texlive texlive-latex-extra`

After installation, run:

`pdflatex --version`

to verify that LaTeX is installed correctly.

\noindent\rule{\textwidth}{0.4pt}

### **Step 3: Convert Markdown to PDF**

Once everything is installed, navigate to the folder containing your Markdown file and run:

`pandoc myfile.md -o myfile.pdf`

This will generate a simple PDF with default formatting.

\noindent\rule{\textwidth}{0.4pt}

### **Step 4: Apply Custom Formatting**

To enchance the PDF layout, you can specify font, margins, and headers using LaTeX options. Use the following command:

`pandoc myfile.md -o myfile.pdf --pdf-engine=xelatex -V mainfont="Arial" -V geometry:margin=1in`

To include a header and footer, create a file named `header-footer.tex` with the folowing content:


```\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhead[L]{Markdown to PDF Guide}
\fancyfoot[L]{Your Name}
\fancyfoot[C]{Page \thepage}
\fancyfoot[R]{February 2025}
```

Then run:

`pandoc myfile.md -o myfile.pdf --template=header-footer.tex`

\noindent\rule{\textwidth}{0.4pt}

### **Step 5. Troubleshooting**

If the conversion fails due to missing LaTeX packages, Pando may prompt you to install them. Allow the installation or manully install them using: 

`tlmgr install [package-name]`

For example, to install the unicode-math package:

`tlmgr install unicode-math`

\noindent\rule{\textwidth}{0.4pt}

### **Conclusion**
With Pandoc, you can efficiently convert Markdown to PDF while applying custom formatting. This method ensure your documents are well-structured, readable, and professional-looking.

