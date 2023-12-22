# RISE ASSIGNMENT
Assignment for Research Engineer position at RISE.

This project was built as an assignment for a Research position at RISE. Due to the automatic creation of the requirements file, additional automatically installed packages in the Google Collab environment have also been included. As such, the first cell of the notebook can also be used as a reference if the project is being run in a local environment.

The following project was largely built on top of the tutorial on token classification provided by HuggingFace: https://huggingface.co/learn/nlp-course/chapter7/2?fw=pt. However, the contents of the file have been partly adjusted in order to fit with the details given in the assignment description. As such, the project implements two BERT-base models (https://huggingface.co/bert-base-cased) fine-tuned on two separate alternations of the same dataset (https://huggingface.co/datasets/Babelscape/multinerd?row=17) but tested on the same test set. Thus, model A acknowledges all 30 NER tags in the given dataset while training. Contrastingly, model B only acknowledges 10 of the NER tags in the training set. Consequently, all other NER tags are seen as non-entities.

The project can be run in environments such as Google Colab by running all individual cells. However, one must be able to provide a HuggingFace token in order to properly upload the given model. Thus, a HugginFace account is a requirement.

The results show that model B is performing worse on recall but better on precision. This is likely due to the fact that the model got very specialized during the training phase. By only focusing on a total of 10 tags, it is likely that it suffered less diffusion during training, and thus, it got specialized on a few sets of labels. However, it is inferior in terms of recall, as it has not familiarized itself with many of the classes existing in the test set.

Furthermore, the evaluation of the model could have been carried out in a more interpretable manner. By providing additional metrics according to previous research (https://aclanthology.org/2020.emnlp-main.489.pdf), such as attribute-wise, bucket-wise evaluation, or even label-level performance, a greater understanding of the models could have been provided. As such, it would have been interesting to see how factors such as label consistency and entity length would influence the outcome of the predictions. Given more time, such an analysis could add further depth to the project.

Regarding the performance of the models, one could have more carefully investigated the specific characteristics of the dataset in order to pick a more applicable model for optimizing the performance. As has been previously shown (https://aclanthology.org/2020.emnlp-main.489.pdf), LSTM-based models such as FLAIR may perform differently when compared to Transformer-based models such as BERT when applied to datasets with varying characteristics. Las, the hyperparameters could have been more carefully picked and tuned during training.


