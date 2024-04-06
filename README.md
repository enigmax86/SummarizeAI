# SummarizeAI
This project can be used to get summary of pdfs and urls using fine trained models for specific purposes like Book Summary , Resume Summary , General PDF Summary , Url News/Article Summary

![image](https://github.com/skillingshark/SummarizeAI/assets/117962699/55311c75-8268-4069-b886-a2b4a47eb814)

1. You can choose what you want to summarize [ URL or PDF ] 
2. You can choose among models fine tuned for specific purposes like Book/Document Summary, Resume Summary, General PDF Summary, Url News/Article Summary

## Preprocessing
- PDF
   - We have used ```PyPDF2``` and ```pdfminer``` libraries to extract raw text content from the pdf
- URL
   - We used ```selenium webdriver``` to Scrape off the raw text content from the given url
 
The raw text content is then passed to ```RecursiveCharacterTextSplitter``` imported from ```langchain.text_splitter``` to chunk the data using separators such as '\n' and using a chunk overlap of 25 to reduce the problem of loss of context during splitting text into chunks.

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

