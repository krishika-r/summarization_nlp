# summarization_nlp

Table to Insights/Table to summary and Text to summary
Overview
This solution demonstrates how to train language models for **table-to-insights/table-to-summary and text-to-summary objectives**. 
We can use the power of Seq2Seq generative models and broder objective like summarization to solve these objectives.
We used huggingface [summarization solution](https://github.com/huggingface/transformers/tree/main/examples/pytorch/summarization) as the base and created wrappers & pre-processing modules on top of it to create the solution.

The following steps areThe following steps are followed to train models for Table to Insights/Table to summary objective and the same is demonstrated in the [solution notebook](https://github.com/krishika-r/summarization_nlp/blob/main/Text_table_summarization.ipynb)
    1.Pre-process the tables to flatten text and dump it in required file format (json/csv). The entire table can be converted to flatten text or specifically highlighted cells.
    2.Create training data with flatten text as input and insight/summary as labels.
    3.Train Seq2Seq pre-trained models with summarization objective.
    4.Evaluate model performance on metrics like **ROUGE-1, ROUGE-L, BLEU** and **Semantic similarity** scores

The following steps are followed to train models for Text to summary objective and the same is demonstrated in the solution notebook
    1.Create training data with text as input and insight/summary as labels.
    2.Train Seq2Seq pre-trained models with summarization objective.
    3.Evaluate model performance on metrics like **ROUGE-1, ROUGE-L, BLEU** and **Semantic similarity** scores
