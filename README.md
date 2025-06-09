# LLM Project

## Project Task

Document Summarization Tool: Develop a tool that can summarize long documents into key points and sections, making them easier to digest for the readers.

## Dataset

### Dataset Summary
Multi-News, consists of news articles and human-written summaries of these articles from the site newser.com. Each summary is professionally written by editors and includes links to the original articles cited.

There are two features:

- document: text of news articles seperated by special token "|||||".
- summary: news summary.

The dataset contains a train and a test split.

## Pre-trained Model

The pretrained model I used was T5 Small.

### Model Description
The developers of the Text-To-Text Transfer Transformer (T5) write:

With T5, we propose reframing all NLP tasks into a unified text-to-text-format where the input and output are always text strings, in contrast to BERT-style models that can only output either a class label or a span of the input. Our text-to-text framework allows us to use the same model, loss function, and hyperparameters on any NLP task.

### Direct Use and Downstream Use
The developers write in a blog post that the model:

Our text-to-text framework allows us to use the same model, loss function, and hyperparameters on any NLP task, including machine translation, document summarization, question answering, and classification tasks (e.g., sentiment analysis). We can even apply T5 to regression tasks by training it to predict the string representation of a number instead of the number itself.

## Performance Metrics
(fill in details about your chosen metrics and results)

## Hyperparameters
(fill in details about which hyperparemeters you found most important/relevant while optimizing your model)

