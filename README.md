# MeTooMA
a repository for sharing the dataset produced in the ICWSM paper titled #MeTooMA: Multi-Aspect Annotations of Tweets Related to the MeToo Movement by students and collaborators working at

<br>
<p align="center">
  <img src="https://github.com/midas-research/bhaav/blob/master/MIDAS-logo.jpg" alt="MIDAS lab at IIIT-Delhi"  width="60%"/>
  <br>
</p>
<br>

**MeTooMA** is a dataset containing 9,973 tweets related  to  the  MeToo  movement  that  were  manually  annotated  for  five  different  linguistic  aspects:  **relevance** (relevant, not relevant),  **stance** (support, opposition), **hate speech**  (directed hate, generalized hate), **sarcasm** (sarcastic, not sarcastic), and **dialogue acts** (allegation, refutation, justification). For more details please refer to the paper below.


This repository contains link to download the data, and information about the corpus. Akash, the lead author of the work has also written a wonderful [blog post](https://medium.com/@418akash/a-multi-aspect-view-of-metoo-movement-on-twitter-9fdefae484df) describing the dataset and the rationale behind the study. 


Currently this dataset is a part of the HuggingFace `🤗Datasets` library for community usage. This would assist easy sharing and access of this dataset for research purposes. 

The dataset can be obtained from https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/JN4EYU

## Dataset Overview

#### Distribution of tweets by country

<br>
<p align="center">
  <img src="https://github.com/midas-research/MeTooMA/blob/master/tweets-by-country.png" alt="Distribution of tweets by country"  width="60%"/>
  <br>
</p>
<br>

<br>
<p align="center">
  <img src="https://github.com/midas-research/MeTooMA/blob/master/fvc.png" alt="Distribution of tweets by country"  width="60%"/>
  <br>
</p>
<br>


### Geographical  distribution  of  various  class  labels

<br>
<p align="center">
  <img src="https://github.com/midas-research/MeTooMA/blob/master/country_share_2.png" alt="Geographical  distribution  of  various  class  labels"  width="60%"/>
  <br>
</p>
<br>

### Word cloud representation of the dataset

<br>
<p align="center">
  <img src="https://github.com/midas-research/MeTooMA/blob/master/nrc_wordcloud.png" alt="Word cloud representation of the dataset"  width="70%"/>
  <br>
</p>
<br>

### Top five phrases learned by SAGE Topic model for the all the labels

<br>
<p align="center">
  <img src="https://github.com/midas-research/MeTooMA/blob/master/sage-topic-dist.png" alt="Top five phrases learned by SAGE Topic model for the all the labels"  width="60%"/>
  <br>
</p>
<br>

### Inter-annotator agreements for all the annotation tasks

<br>
<p align="center">
  <img src="https://github.com/midas-research/MeTooMA/blob/master/inter-annotator-agreement.png" alt="Inter-annotator agreements for all the annotation tasks"  width="40%"/>
  <br>
</p>
<br>

### Distribution of class labels for all tasks

<br>
<p align="center">
  <img src="https://github.com/midas-research/MeTooMA/blob/master/class-distribution.png" alt="Distribution of class labels for all tasksDistribution of tweets by country"  width="60%"/>
  <br>
</p>
<br>


## HuggingFace Support for MeTooMA Dataset
<p align="center">
    <br>
    <img src="https://raw.githubusercontent.com/huggingface/datasets/master/docs/source/imgs/datasets_logo_name.jpg" width="35%"/>                                                                         
    <br>
<p>

**MeTooMA** is officially now a part of the HuggingFace datasets library. `🤗Datasets` is a lightweight and extensible library to easily share and access datasets and evaluation metrics for Natural Language Processing (NLP) and more. It has many interesting features (beside easy sharing and accessing datasets/metrics):

- Built-in interoperability with NumPy, pandas, PyTorch and Tensorflow 2
- Lightweight and fast with a transparent and pythonic API
- Strive on large datasets: `🤗Datasets` naturally frees the user from RAM memory limitation, all datasets are memory-mapped on drive by default.
- Smart caching: never wait for your data to process several times

### Installation

`🤗Datasets` can be installed from PyPi and has to be installed in a virtual environment (venv or conda for instance)

```bash
pip install datasets
```

For more details on installation, check the installation page in the documentation: https://huggingface.co/docs/datasets/installation.html

### Using with PyTorch/TensorFlow/pandas

If you plan to use `🤗Datasets` with PyTorch (1.0+), TensorFlow (2.2+) or pandas, you should also install PyTorch, TensorFlow or pandas.

For more details on using the library with NumPy, pandas, PyTorch or TensorFlow, check the quick tour page in the documentation: https://huggingface.co/docs/datasets/quicktour.html

### Usage

`🤗Datasets` is made to be very simple to use. The main methods are:

- `datasets.list_datasets()` to list the available datasets
- `datasets.load_dataset(dataset_name, **kwargs)` to instantiate a dataset
- `datasets.list_metrics()` to list the available metrics
- `datasets.load_metric(metric_name, **kwargs)` to instantiate a metric

Here is a quick example to use **MeTooMA** dataset after installing the `🤗Datasets` library:

```python
from datasets import list_datasets, load_dataset, list_metrics, load_metric

# Print all the available datasets
print(list_datasets())

# Load a dataset and print the first examples in the training set
metooma_dataset = load_dataset('metooma')
print(metooma_dataset['train'][0])
{'Allegation': 0, 'Directed_Hate': 0, 'Generalized_Hate': 0, 'Image_Only_Informative': 1, 
'Justification': 1, 'Oppose': 0, 'Refutation': 0, 'Sarcasm': 0, 'Support': 1, 
'Text_Only_Informative': 1, 'TweetId': '1052237153789390853'}


# List all the available metrics
print(list_metrics())
['accuracy', 'bertscore', 'bleu', 'bleurt', 'coval', 'f1', 'gleu', 'glue', 'indic_glue', 'meteor', 
'precision', 'recall', 'rouge', 'sacrebleu', 'seqeval', 'squad', 'squad_v2', 'xnli']

```
A few pointers to note for the members of the community using this dataset:
- The presence of 0 or 1 indicates the absence or presence of an applicable label for a given Tweet.
- You can browse the live version of this dataset with [live datasets viewer](https://huggingface.co/datasets/viewer/?dataset=metooma)
- The dataset is already split into train and test splits. Please refer to the example for its usage. 
- Please refer to the accompanying publication for detailed information about the data collection process, annotation, 
statistical analysis and ethical discussions on this dataset. 


## Terms of Use

1. This corpus can be used freely for research purposes.
2. The paper listed below provide details of the creation and use of the corpus. If you use the corpus, then please cite the     paper.
3. If interested in commercial use of the corpus, send email to midas@iiitd.ac.in.
4. If you use the corpus in a product or application, then please credit the authors and [Multimodal Digital Media Analysis Lab - Indraprastha Institute of Information Technology, New Delhi](http://midas.iiitd.edu.in) appropriately. Also, if you send us an email, we will be thrilled to know about how you have used the corpus.
5. Multimodal Digital Media Analysis Lab - Indraprastha Institute of Information Technology, New Delhi, India disclaims any responsibility for the use of the corpus and does not provide technical support. However, the contact listed above will be happy to respond to queries and clarifications.
6. Rather than redistributing the corpus, please direct interested parties to this [page](https://github.com/midas-research/MeTooMA)

Please feel free to send us an email:
- with feedback regarding the corpus.
- with information on how you have used the corpus.
- if interested in having us analyze your social media data.
- if interested in a collaborative research project.

Copyright (C) 2019 Multimodal Digital Media Analysis Lab - Indraprastha Institute of Information Technology, New Delhi (MIDAS, IIIT-Delhi)

## References

Please cite these papers if you found the relevant resources in this repository useful.


```
@article{Gautam_Mathur_Gosangi_Mahata_Sawhney_Shah_2020, title={#MeTooMA: Multi-Aspect Annotations of Tweets Related to the MeToo Movement}, volume={14}, url={https://aaai.org/ojs/index.php/ICWSM/article/view/7292}, abstractNote={&lt;p&gt;In this paper, we present a dataset containing 9,973 tweets related to the MeToo movement that were manually annotated for five different linguistic aspects: relevance, stance, hate speech, sarcasm, and dialogue acts. We present a detailed account of the data collection and annotation processes. The annotations have a very high inter-annotator agreement (0.79 to 0.93 k-alpha) due to the domain expertise of the annotators and clear annotation instructions. We analyze the data in terms of geographical distribution, label correlations, and keywords. Lastly, we present some potential use cases of this dataset. We expect this dataset would be of great interest to psycholinguists, socio-linguists, and computational linguists to study the discursive space of digitally mobilized social movements on sensitive issues like sexual harassment.&lt;/p&#38;gt;}, number={1}, journal={Proceedings of the International AAAI Conference on Web and Social Media}, author={Gautam, Akash and Mathur, Puneet and Gosangi, Rakesh and Mahata, Debanjan and Sawhney, Ramit and Shah, Rajiv Ratn}, year={2020}, month={May}, pages={209-216} }
```

```
@inproceedings{ghosh-chowdhury-etal-2019-youtoo,
    title = "{\#}{Y}ou{T}oo? Detection of Personal Recollections of Sexual Harassment on Social Media",
    author = "Ghosh Chowdhury, Arijit  and
      Sawhney, Ramit  and
      Shah, Rajiv Ratn  and
      Mahata, Debanjan",
    booktitle = "Proceedings of the 57th Annual Meeting of the Association for Computational Linguistics",
    month = jul,
    year = "2019",
    address = "Florence, Italy",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/P19-1241",
    doi = "10.18653/v1/P19-1241",
    pages = "2527--2537",
    abstract = "The availability of large-scale online social data, coupled with computational methods can help us answer fundamental questions relat- ing to our social lives, particularly our health and well-being. The {\#}MeToo trend has led to people talking about personal experiences of harassment more openly. This work at- tempts to aggregate such experiences of sex- ual abuse to facilitate a better understanding of social media constructs and to bring about social change. It has been found that disclo- sure of abuse has positive psychological im- pacts. Hence, we contend that such informa- tion can leveraged to create better campaigns for social change by analyzing how users react to these stories and to obtain a better insight into the consequences of sexual abuse. We use a three part Twitter-Specific Social Media Lan- guage Model to segregate personal recollec- tions of sexual harassment from Twitter posts. An extensive comparison with state-of-the-art generic and specific models along with a de- tailed error analysis explores the merit of our proposed model.",
}
```


```
@inproceedings{ghosh-chowdhury-etal-2019-speak,
    title = "Speak up, Fight Back! Detection of Social Media Disclosures of Sexual Harassment",
    author = "Ghosh Chowdhury, Arijit  and
      Sawhney, Ramit  and
      Mathur, Puneet  and
      Mahata, Debanjan  and
      Ratn Shah, Rajiv",
    booktitle = "Proceedings of the 2019 Conference of the North {A}merican Chapter of the Association for Computational Linguistics: Student Research Workshop",
    month = jun,
    year = "2019",
    address = "Minneapolis, Minnesota",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/N19-3018",
    doi = "10.18653/v1/N19-3018",
    pages = "136--146",
    abstract = "The {\#}MeToo movement is an ongoing prevalent phenomenon on social media aiming to demonstrate the frequency and widespread of sexual harassment by providing a platform to speak narrate personal experiences of such harassment. The aggregation and analysis of such disclosures pave the way to development of technology-based prevention of sexual harassment. We contend that the lack of specificity in generic sentence classification models may not be the best way to tackle text subtleties that intrinsically prevail in a classification task as complex as identifying disclosures of sexual harassment. We propose the Disclosure Language Model, a three part ULMFiT architecture, consisting of a Language model, a Medium-Specific (Twitter) model and a Task-Specific classifier to tackle this problem and create a manually annotated real-world dataset to test our technique on this, to show that using a Discourse Language Model often yields better classification performance over (i) Generic deep learning based sentence classification models (ii) existing models that rely on handcrafted stylistic features. An extensive comparison with state-of-the-art generic and specific models along with a detailed error analysis presents the case for our proposed methodology.",
}
```


