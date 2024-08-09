# Introduction
This repo tries different PDF content extraction methods and compare their pros/cons.

## 00 - deep_layout_parsing.ipynb
This notebook uses layoutparser library to extract PDF content and categorize them into different format. By default, the layoutparser library could extract figure, table, text, title, which could satifisfy the basic requirement of academic paper extraction requirement. The github repo is located at https://github.com/Layout-Parser/layout-parser 

The ![YouTube tutorial](Customized Layout Detection for Scientific PDFs with LayoutParser and Label Studio) explains how to use Label Studio to train LayoutParser model and create new labels (such as `formula` block or `algorithm` block, etc.). The Label Studio is developed with Django, with the similar functionality of annotation tool CVAT. After creating label (annoation), you could follow its sample code to fine tune the LayoutParser model to add new labels, just like you fine tune Yolo model.

However, for this module layoutparser, it does not provide the conversion from the image to Lax, and you need to implement by yourself. It's advantage lies in its accurate layout segmentation and re-organization.

## 00 - use_pix2lax_pipeline.ipynb
This module is similar to the above layoutparser, but it adds some public libraries to convert each segmented image into Lax format, so provide a complete PDF-to-Lax pipeline. It is a bit complicated to understand its code structure since there are many wrapper functions. Compared to Mathpix, its OCR functionalities are not error-proof and some recognized texts are not 100% correct, but it offers a complete pipeline from PDF image to Latex extraction. The extraction content could be categorized into figure, table, formula, text, title. For those text mixing both plain text and formula, it could also extract correct information and combine back to form correct .md file.

The github repo is located at https://github.com/breezedeus/pix2text.
It offers log and output folder, so you could see all the temporary layout segmentataion results and all the output files.
It is a bit complicated to understand the code structure. The documentation does not provide detailed specification for some functions. However, once you understand, you feel convenient to use this library. 

## 01 - simple_local_rag.ipynb
This notebook is based upon the steps from 00 - use_pix2lax_pipeline.ipynb. Once getting the .md file for each pdf page, we could further process the .md file by splitting into sentence blocks, comparing the similarity between query and sentence blocks and finding the most similar sentences. Then we could use LLM model to generate new text based on the argumented reference information.

# generate_dataset.ipynb
This notebook provides some helper function. It provides routines to convert PDF files into images.


