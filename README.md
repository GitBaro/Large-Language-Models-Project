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
My chosen performance metrics was using Rouge.
It achieves the following results on the evaluation set:
- Loss: 5.7052
- Rouge1: 0.3780
- Rouge2: 0.0738
- Rougel: 0.2719
- Rougelsum: 0.3092

## Hyperparameters

The hyperparameters I found most important and relevant while optimizing my model were:
- learning_rate
- per_device_train_batch_size
- per_device_eval_batch_size
- num_train_epochs
- warmup_steps
