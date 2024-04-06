# SummarizeAI
SummarizeAi is a Python-based project that provides a smooth and efficient way to summarize both PDF documents and URLs using their text content. It employs advanced preprocessing techniques and model selection to generate concise and informative summaries. Additionally, SummarizeAi offers a user-friendly interface with features like model selection, URL and PDF input, custom summary length, and more.

## Features
1. PDF and URL Summarization: SummarizeAi supports summarization of both PDF documents and web URLs, extracting text content for summarization.
2. Model Selection: Users can choose from a variety of pre-trained models to generate summaries, allowing flexibility based on specific requirements.
3. Custom Summary Length: SummarizeAi enables users to specify the desired length of the summary, tailoring it to their preferences.
4. Smooth User Interface: The project is designed with a user-friendly interface, ensuring ease of use and accessibility for all users.

![image](https://github.com/skillingshark/SummarizeAI/assets/117962699/55311c75-8268-4069-b886-a2b4a47eb814)

## Preprocessing
- Text Extraction
   - For PDFs we have used ```PyPDF2``` and ```pdfminer``` libraries to extract raw text content from the pdf
   - For Urls we used ```selenium webdriver``` to scrape off the raw text content from the given url

- The raw text content is then passed to ```RecursiveCharacterTextSplitter``` imported from ```langchain.text_splitter``` to chunk the data using separators such as '\n' and using a chunk overlap of 25 to reduce the problem of loss of context during splitting text into chunks.
- Stopword Removal: Common stopwords are removed from the text to reduce noise and improve the quality of the summary.
- Sentence Tokenization: The text is segmented into individual sentences to facilitate sentence-level analysis.

## Model Selection
We have used various pre-trained models from Hugging Face for specific purposes like
```
1. "Basic Model":
    Model_Version = "sshleifer/distilbart-cnn-12-6"
```
```
2. "For Resume PDF Summary":
    Model_Version = "Samir001/ResumeSummary-t5-Wang-Arora"
```
```
4. "For URL News/Article Summary":
    Model_Version = "mrm8488/t5-base-finetuned-summarize-news"
```
```
5. "For Book/Document PDF Summary (Recommended)"
    Model_Version = "pszemraj/long-t5-tglobal-base-16384-book-summary"
```

