# PDF MEDICAL CHARTS ANALYZER

***

## Description :-

This tool can be used to read PDF medical charts and search for pre-defined diagnoses codes and their descriptions.
The tool outputs an index file per medical chart, with the page number and line number where probable matches are found. 
Although the output needs to analyzed by a human, the tool drastically reduces the time required to manually read 
through charts which could take hours. The output also helps prioritize certain diagnoses codes over others depending 
on what needs to be analyzed. Further enhancements are possible to curtail output depending on what filters one needs.

***

## Setup :-

### (1) Create a virtual environment :- (skip if one of interest already exists)
```commandline
cd ~/
mkdir  my_dir_for_venvs
cd my_dir_for_virtual_envs
python3 -m venv pdf-charts-reader-venv
```

### (2) Activate the virtual environment :-
```commandline
source ~/my_dir_for_venvs/pdf-charts-reader-venv/bin/activate
```

### (3) Clone this repository :-
```commandline
cd ~/
git clone https://github.com/nsb700/pdf-medical-charts-analyzer.git pdf_charts_analyzer_app
```

### (4) Install required dependencies by referring to requirements.txt :-
```commandline
cd ~/pdf_charts_analyzer_app
pip install -r requirements.txt
```

### (5) Create directory hierarchy for pdf processing flow
```commandline
cd ~/pdf_charts_analyzer_app
mkdir corpus_flow
mkdir corpus_flow/input_pdf_charts
mkdir corpus_flow/stg_00
mkdir corpus_flow/stg_01
mkdir corpus_flow/stg_02
mkdir corpus_flow/stg_03
mkdir corpus_flow/stg_04
mkdir corpus_flow/stg_05
mkdir corpus_flow/stg_06
```

### (6) Placement of PDF medical charts for processing  :-
Place PDF medical charts in **pdf_charts_analyzer_app/corpus_flow/input_pdf_charts**

### (7) Placement of ICD Codes to be searched :-
For ICD codes which are to be searched, a reference file has already been provided at **pdf_charts_analyzer_app/icd_codes/codesfile.csv**  
One may add/delete icd codes as required as long as same formatting in maintained.

***

## How to run the tool :-
* Run the executable provided at **pdf_charts_analyzer_app/main**.
* Browse and provide the path to the **pdf_charts_analyzer_app/corpus_flow** directory
* Browse and provide the path to the **pdf_charts_analyzer_app/icd_codes** directory
* Click Submit and wait for the tool to finish its processing.
* Output :-
  * After processing is finished, final output csv index files are stored in **pdf_charts_analyzer_app/corpus_flow/stg_05** 
  * Problematic PDF files which cannot be processed will be saved in **pdf_charts_analyzer_app/corpus_flow/stg_06**

## Few screenshots of the tool run :-
![img01.png](screenshot_images%2Fimg01.png)

Below is a small section of a page in the PDF chart -

![img02.png](screenshot_images%2Fimg02.png)

Below is the text extracted. This is an intermediate output which gets deleted after final output is created.

![img03.png](screenshot_images%2Fimg03.png)

![img04.png](screenshot_images%2Fimg04.png)

Below is one row of the final output csv file -

![img05.png](screenshot_images%2Fimg05.png)