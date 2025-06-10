# LLM Project

### Notebooks would not upload properly, please see these links to google collabs. 
[Preprocessing](https://colab.research.google.com/drive/1RHpvMXorbQCSCzSvlye5sLN7c0eDLGxA#scrollTo=O2kpmZaEdZ0z)
[Representation](https://colab.research.google.com/drive/1M6UltVPh_HoUPlJzLhxEGi79O-rEQTpi#scrollTo=KAikIGa5kPpz)
[Pre-Trained Model](https://colab.research.google.com/drive/1oPaL8uHaa1-b0BYu_n6nybxK6T9S96BR#scrollTo=lsiC1u21-Ifi)
[Optimization](https://colab.research.google.com/drive/1niI11aARnmpsV_8O42Ge7yuIJRJfh8kd#scrollTo=ORshxmM4UNnD&uniqifier=1)

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

The pretrained models I used were BART Large and T5 Small.

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
