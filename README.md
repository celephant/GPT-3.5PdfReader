# PDF Reader with ChatGPT
PDF Reader with OpenAI GPT-3 API is a Python program that allows users to upload a PDF file and generate answers to their questions using OpenAI's GPT-3 API. This program makes use of the PyPDF2 library to extract text from the PDF file and the OpenAI API to generate answers to user questions.

Prerequisites
Before running this program, you will need:

Python 3.7 or later installed on your machine
An OpenAI API key. You can obtain an API key by signing up for an OpenAI account and following the instructions on the API Keys page.
Installation
To install the required Python packages, run the following command:

Copy code
pip install -r requirements.txt
Usage
To use this program, run the following command:

css
Copy code
python main.py
Upon running the program, you will be prompted to enter your OpenAI API key. After entering your API key, a file dialog will appear allowing you to select a PDF file to upload. The program will extract the text from the file and prompt you to enter a question. You can enter any question related to the content of the PDF file, and the program will generate an answer using the OpenAI GPT-3 API.

You can continue entering questions until you are finished. To exit the program, simply type "exit" when prompted for a question.

Acknowledgements
This program was created using the PyPDF2 and OpenAI Python libraries. The PyPDF2 library is used to extract text from PDF files, and the OpenAI Python library is used to generate answers to user questions using GPT-3.

License
This program is licensed under the MIT License. See the LICENSE file for details.

The updated README provides clearer instructions on how to install and use the program, and makes use of bullet points to make the information easier to read. Additionally, the acknowledgements section provides more information about the libraries used in the program, and the license information is clearly stated at the end of the document.
