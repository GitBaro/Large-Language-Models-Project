# LLM Project

### Notebooks would not upload properly, please see these links to google collabs. 
[Preprocessing](https://colab.research.google.com/drive/1RHpvMXorbQCSCzSvlye5sLN7c0eDLGxA#scrollTo=O2kpmZaEdZ0z)
[Representation](https://colab.research.google.com/drive/1M6UltVPh_HoUPlJzLhxEGi79O-rEQTpi#scrollTo=KAikIGa5kPpz)
[Pre-Trained Model](https://colab.research.google.com/drive/1oPaL8uHaa1-b0BYu_n6nybxK6T9S96BR#scrollTo=lsiC1u21-Ifi)
[Optimization](https://colab.research.google.com/drive/1RHpvMXorbQCSCzSvlye5sLN7c0eDLGxA#scrollTo=O2kpmZaEdZ0z)

## Project Task

Document Summarization Tool: Develop a tool that can summarize long documents into key points and sections, making them easier to digest for the readers.

My HuggingFace Model Link:
https://huggingface.co/HFBaro/Large-Language-Models-Project

## Dataset

### Dataset Summary
Multi-News, consists of news articles and human-written summaries of these articles from the site newser.com. Each summary is professionally written by editors and includes links to the original articles cited.

Multi-News Dataset Link: https://huggingface.co/datasets/alexfabbri/multi_news

There are two features:

- document: text of news articles seperated by special token "|||||".
- summary: news summary.

The dataset contains a train and a test split.

## Pre-trained Model

The pretrained models I used were BART Large and T5 Small. I used both these models because they are standard document summarization models which respectively work effectively for training models on large and small datasets.

### Model Description: BART

BART is a transformer encoder-encoder (seq2seq) model with a bidirectional (BERT-like) encoder and an autoregressive (GPT-like) decoder. BART is pre-trained by (1) corrupting text with an arbitrary noising function, and (2) learning a model to reconstruct the original text.

BART is particularly effective when fine-tuned for text generation (e.g. summarization, translation) but also works well for comprehension tasks (e.g. text classification, question answering). This particular checkpoint has been fine-tuned on CNN Daily Mail, a large collection of text-summary pairs.
The developers of the Text-To-Text Transfer Transformer (T5) write:

### Model Description: T5 Small

With T5, we propose reframing all NLP tasks into a unified text-to-text-format where the input and output are always text strings, in contrast to BERT-style models that can only output either a class label or a span of the input. Our text-to-text framework allows us to use the same model, loss function, and hyperparameters on any NLP task.

### Direct Use and Downstream Use
The developers write in a blog post that the model:

Our text-to-text framework allows us to use the same model, loss function, and hyperparameters on any NLP task, including machine translation, document summarization, question answering, and classification tasks (e.g., sentiment analysis). We can even apply T5 to regression tasks by training it to predict the string representation of a number instead of the number itself.

## Performance Metrics
My chosen performance metrics was using Rouge.
It achieves the following results on the evaluation set:
- Loss: 5.7059
- Rouge1: 0.3782
- Rouge2: 0.0730
- Rougel: 0.2713
- Rougelsum: 0.3079

## Hyperparameters

The hyperparameters I found most important and relevant while optimizing my model were:
- learning_rate: Because it determines and adjusts how quick the model learns, kept low because using pre-trained model and trying to avoid messing with the models pre-trained knowledge
- batch_size: Because it determines training speed and stability, as well as determining how much memory usage while training the model. Kept to a side where its able to train the model without crashing due to memory usage
- num_train_epochs: Because it determines how many times the dataset is seen by the model, allowoing it to learn more but also not enough to overfit depending on the size of the model
