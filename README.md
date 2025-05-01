# bert-chunk-tags
There are comments within the code that provide explanations, but I’ll also give a more detailed overview here. As mentioned earlier, this project is based on a BERT model that has been fine-tuned.

First, I loaded the required dataset, removed unnecessary columns, and renamed the relevant columns. As you can see in the code, we performed some initial exploration of the dataset to understand what possible labels we have.

One of the main challenges we encountered was how to correctly align labels with tokens after tokenization—since a single word may be split into multiple tokens. We handled this issue by implementing a custom function that maps the original labels to the tokenized outputs.

After that, we applied this function during the tokenization step on our dataset. Then, we loaded the model and passed the label mappings (label-to-ID and ID-to-label) to it. Finally, we trained the model using the Trainer API provided by Hugging Face.

