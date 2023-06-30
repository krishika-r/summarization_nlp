# summarization_nlp

Table to Insights/Table to summary and Text to summary

## Overview
This solution demonstrates how to train language models for **table-to-insights/table-to-summary and text-to-summary objectives**. 
We can use the power of Seq2Seq generative models and broder objective like summarization to solve these objectives.
We used huggingface [summarization solution](https://github.com/huggingface/transformers/tree/main/examples/pytorch/summarization) as the base and created wrappers & pre-processing modules on top of it to create the solution.

The following steps are followed to train models for the objective and the same is demonstrated in the [solution notebook](https://github.com/krishika-r/summarization_nlp/blob/main/Text_table_summarization.ipynb)

**Table to Insights/Table to summary**

    1.Pre-process the tables to flatten text and dump it in required file format (json/csv). The entire table can be converted to flatten text or specifically highlighted cells.
    2.Create training data with flatten text as input and insight/summary as labels.
    3.Train Seq2Seq pre-trained models with summarization objective.
    4.Evaluate model performance on metrics like **ROUGE-1, ROUGE-L, BLEU** and **Semantic similarity** scores

## Dataset:

ToTTo introduces a controlled generation task in which a given Wikipedia table with a set of selected cells is used as the source material for the task of producing a single sentence description that summarizes the cell contents in the context of the table. The example below demonstrates some of the many challenges posed by the task, such as numerical reasoning, a large open-domain vocabulary, and varied table structure.

![totto_table_to_text_example]

*Example in the ToTTo dataset, where given the source table and set of highlighted cells (left), the goal is to generate a one-sentence description, such as the “target sentence” (right). Note that generating the target sentence would require numerical inference (eleven NFL seasons) and an understanding of the NFL domain.*

To read more on ToTTo, visit [ToTTo: A Controlled Table-to-Text Generation](https://ai.googleblog.com/2021/01/totto-controlled-table-to-text.html)

## Dataset
To carry out different experiments based on table-to-insight or table-to-summary objectives we can use a similar approach as Google ToTTo to flatten the table into free-flowing text and deal with it similarly to Seq2Seq objectives. We have included a pre-processing [code](https://github.com/krishika-r/summarization_nlp/blob/main/) to process tables to flattened text which is based on [Lattice Repo](https://github.com/luka-group/Lattice/tree/main/Lattice).

[**Google ToTTo Dataset**](https://github.com/google-research-datasets/totto)


1. ToTTo datasets were pre-trained on T5 and BART-based models. 
2. T5 models show better performance as compared to BART models.

**Model Training Time**
1. T5-small
    - 1K training data and 4-5 epochs (2-3 mins)
    - 80K training data and 4-5 epochs (5-6 hrs)
2. BART-Large
    - 1K training data and 4-5 epochs (5-10 mins)
    - 80K training data and 4-5 epochs (8-10 hrs)

**Text to summary**

    1.Create training data with text as input and insight/summary as labels.
    2.Train Seq2Seq pre-trained models with summarization objective.
    3.Evaluate model performance on metrics like **ROUGE-1, ROUGE-L, BLEU** and **Semantic similarity** scores
