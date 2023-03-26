import openai
import PyPDF2
from tkinter import filedialog, Tk
import os

if 'TK_SILENCE_DEPRECATION' not in os.environ:
    os.environ['TK_SILENCE_DEPRECATION'] = '1'

# Prompt the user for their API key
api_key = input("Enter your OpenAI API key: ")

# Set up the OpenAI API with the provided API key
openai.api_key = api_key

# Define a function to extract text from a PDF file
def extract_text_from_pdf(file_path):
    with open(file_path, 'rb') as f:
        pdf_reader = PyPDF2.PdfReader(f)
        text = ''
        for page_num in range(len(pdf_reader.pages)):
            page = pdf_reader.pages[page_num]
            text += page.extract_text()
    return text

# Define a function to generate answers to user questions using the ChatGPT API
def generate_answer(question, text):
    max_context_length = 4096 - len(question) - 30
    truncated_text = text[:max_context_length]

    prompt = f"{truncated_text}\n\nQuestion: {question}\nAnswer:"
    response = openai.Completion.create(
        engine="text-davinci-002",
        prompt=prompt,
        max_tokens=1024,
        n=1,
        stop=None,
        temperature=0.7,
    )
    answer = response.choices[0].text.strip()
    return answer

# Define a function to handle the file upload and answer generation
def handle_file_upload():
    root = Tk()
    root.withdraw()
    file_path = filedialog.askopenfilename(
        filetypes=[("PDF Files", "*.pdf")]
    )

    if not file_path:
        return

    text = extract_text_from_pdf(file_path)

    while True:
        question = input("Enter a question (type 'exit' to end): ")
        if question.lower() == 'exit':
            break

        answer = generate_answer(question, text)
        print(answer)

# Define a main function to run the program
def main():
    handle_file_upload()

if __name__ == "__main__":
    main()
