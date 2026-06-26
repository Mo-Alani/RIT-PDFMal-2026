# RIT-PDFMal-2026
Benchmark dataset for PDF malware detection
***
## *Overview*
RIT-PDFMal-2026 is a benchmark dataset extracted from real-life PDF malware samples. The goal is to create a dataset that can be used to build robust machine learning-based detection systems.

| **Samples** | **Benign** | **Malicious** | **Total** |
|---------------------|-------:|------:|-------------:|
| Collected          | 13,242 | 11,243 | |
| Corrupted          | 7      | 141 | |
| Included in PDFMal | 13,235 | 11,102 | 24,337 |

## *Data Collection*
The malicious samples were obtained from [VirusTotal](https://virustotal.com). These malicious samples were submitted by VirusTotal users, and collected during the period 2017 to 2025. Benign samples were collected using a specialized internet crawler we built to find and download benign PDF files.

## *Data Extraction*
For data extraction from the collected samples, we used a tool that we built for this purpose. The tool is called [PDFMalExtract](https://github.com/Mo-Alani/PDFMalExtract). The table below shows the extracted 42 features and their description.

| **Feature Name**     | **Description**                                                                                                                                                     |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **pdfsize**          | Size of the PDF file in kilobytes.                                                                                                                                  |
| **metadata size**    | Size of metadata extracted from the PDF file, in bytes.                                                                                                             |
| **pages**            | Number of pages in the PDF file.                                                                                                                                    |
| **xref length**      | xref length as extracted from the file header.                                                                                                                      |
| **title length**     | Number of characters in the file title.                                                                                                                             |
| **isEncrypted**      | 1 If the file is encrypted, and 0 otherwise.                                                                                                                        |
| **embedded files**   | Number of embedded files inside the PDF as extracted from the PDF header                                                                                             |
| **images**           | Number of images in the PDF file. This will return -1 if the file is corrupted and doesn't show the number of images.                                                                                                                                  |
| **contains_text**    | Does the file contain a certain number of characters of text? (the default threshold is 50 characters). This shows 1, is the threshold is met, 0 if it wasn't met, and -1 if the file is corrupted and the script couldn't read the text. |
| **pdf_ver**          | Version of the PDF file, as extracted fro mthe file header.                                                                                                         |
| **obj**              | Number of occurrences of the string "obj" in the PDF file.                                                                                                          |
| **endobj**           | Number of occurrences of the string "endobj" in the PDF file.                                                                                                       |
| **stream**           | Number of occurrences of the string "stream" in the PDF file.                                                                                                       |
| **endstream**        | Number of occurrences of the string "endstream" in the PDF file.                                                                                                    |
| **trailer**          | Number of occurrences of the string "trailer" in the PDF file.                                                                                                      |
| **xref**             | Number of occurrences of the string "xref" in the PDF file.                                                                                                         |
| **startxref**        | Number of occurrences of the string "startxref" in the PDF file.                                                                                                    |
| **page_command**     | Number of occurrences of the string "/Page" in the PDF file.                                                                                                        |
| **Encrypt**          | Number of occurrences of the string "/Encrypt" in the PDF file.                                                                                                     |
| **ObjStm**           | Number of occurrences of the string "/ObJStm" in the PDF file.                                                                                                      |
| **JS**               | Number of occurrences of the string "/JS" in the PDF file.                                                                                                          |
| **JavaScript**       | Number of occurrences of the string "/JavaScript" in the PDF file.                                                                                                  |
| **AA**               | Number of occurrences of the string "/AA" in the PDF file.                                                                                                          |
| **OpenAction**       | Number of occurrences of the string "/OpenAction" in the PDF file.                                                                                                  |
| **Acroform**         | Number of occurrences of the string "/Acroform" in the PDF file.                                                                                                    |
| **JBIG2Decode**      | Number of occurrences of the string "/JBIG2Decode" in the PDF file.                                                                                                 |
| **RichMedia**        | Number of occurrences of the string "/RichMedia" in the PDF file.                                                                                                   |
| **Launch**           | Number of occurrences of the string "/Launch" in the PDF file.                                                                                                      |
| **EmbeddedFile**     | Number of occurrences of the string "/EmbeddedFile" in the PDF file.                                                                                                |
| **XFA**              | Number of occurrences of the string "/XFA" in the PDF file.                                                                                                         |
| **Colors**           | Number of occurrences of the string "/Colors > 2^24" in the PDF file.                                                                                               |
| **URI**              | Number of occurrences of the string "/URI" in the PDF file.                                                                                                         |
| **BaseEncoding**     | Number of occurrences of the string "/BaseEncoding" in the PDF file.                                                                                                |
| **Encoding**         | Number of occurrences of the string "/Encoding" in the PDF file.                                                                                                    |
| **ProcSet**          | Number of occurrences of the string "/ProcSet" in the PDF file.                                                                                                     |
| **Registry**         | Number of occurrences of the string "/Registry" in the PDF file.                                                                                                    |
| **Resources**        | Number of occurrences of the string "/Resources" in the PDF file.                                                                                                   |
| **www**              | Number of occurrences of the string "/www" in the PDF file.                                                                                                         |
| **server**           | Number of occurrences of the string "/server" in the PDF file.                                                                                                      |
| **Root**             | Number of occurrences of the string "/Root" in the PDF file.                                                                                                        |
| **BitsPerComponent** | Number of occurrences of the string "/BitsPerComponent" in the PDF file.                                                                                            |
| **Label**            | The label of the entry                                                                                                                                              |

## *Dataset Files*
The extracted dataset is found in the encrypted zip file named **rit-pdfmal-2026.csv.zip**. The password is *pdfmal*
You can find the details of the features description in the file named **features_description.xlsx**.


## *Citation Information*
If you'd like to use this dataset in your research, please cite the following paper that introduced the dataset:

Mohammed M. Alani, Ernesto Damiani, [*RIT-PDFMal-2026: A Comprehensive Benchmark Dataset for PDF Malware Detection*](https://doi.org/10.1109/ACCESS.2026.3707213), IEEE Access, 2026.

    @article{alani2026ritpdf,
      title={RIT-PDFMal-2026: A Comprehensive Benchmark Dataset for PDF Malware Detection},
      author={Alani, Mohammed M. and Damiani, Ernesto},
      doi = "10.1109/ACCESS.2026.3707213"
      journal={IEEE Access},
      volume={xxx},
      pages={xxxx--xxxxx},
      year={2026},
      publisher={IEEE}
      }

## *Acknowledgements*
* This script was built as part of a research project funded by [Rochester Instituite of Technology - Dubai](https://www.rit.edu/dubai/), with grant number RITD-ARC-2025-001.
* We would also like to express our gratitude to [VirusTotal](https://virustotal.com) for providing us with access to the malicious samples used in the creation of this dataset.

## *Contributors*
* **Mohammed M. Alani** ([@Mo-Alani](https://github.com/Mo-Alani/))