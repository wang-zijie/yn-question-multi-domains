# Interpreting Answers to Yes-No Questions in Dialogues from Multiple Domains

The repository for NAACL 2024 finding paper [Interpreting Answers to Yes-No Questions in Dialogues from Multiple Domains](https://arxiv.org/abs/2404.16262)


# Dataset 

We collect yes-no questions from existing dialogue datasets for two tasks: (1) Identifying yes-no questions from dialogue, and (2) Interpreting indirect answers to yes-no questions.
The datasets are available on Google Drive. You can download the data with the [Google Drive Link](https://drive.google.com/drive/folders/1XOzqwSwFuPD0iC9pyez8k04vqb6EDGwg?usp=sharing).

```
dataset    
│
└───indentifying_yes_no_question 
│   │   (yes-no questions indetified by rules or a trained classifier)
|
└───interpreting_indirect_answer
    │
    └───raw_yes_no_question
    │   (yes-no questions without labeling of the answer)
    │
    └───train_set
    │   
    └───validation_set
    |   
    └───test_set
```



## Dataset to identify yes-no questions

The yes-no questions are collected (by rules and a trained classifier) from five dialogue domains: SWDA, MRDA, DailyDialog, Friends, and MWOZ. 



#### Dataset Statistics:
|                      | SWDA | MRDA | DailyDialog | Friends | MWOZ    |
|------------------:   | -----:| ---:|  ------:    |  ------:|  ------:| 
| # yes-no questions   | 3.7k | 2.8k | 13.5k       | 4.9k    | 59.4k   | 

#### Dataset Fields

* ```Question:``` The yes-no question identified from dialogues.
* ```Answer:``` The answer to the yes-no question (the turn immediately after the question turn).


 

## Dataset to interpret indirect answers
We collect yes-no questions from three dialogue domains (by a trained classifier): movie script, tennis interview, and task-oriented dialogues related to travel booking. 



#### Dataset Statistics:


|                      | Movie | Tennis | Air     | 
|------------------:   | -----:| ------:|  ------:| 
| # training instance  | 6,250 | 19,055 | 355,549 | 
| # validation instance|    60 |  60    |  60     | 
| # test instance      |   240 | 240    | 240     | 




#### Dataset Fields

* ```pre_sent_n:``` dialogue turn before the yes-no question. 4 turns (from pre_sent_1 to pre_sent_4) are included.
* ```Q:``` The yes-no question.
* ```A:``` The answer to the yes-no question (the turn immediately after the question turn).
* ```after_sent_n:``` dialogue turn after the answer to yes-no question. 4 turns (from aft_sent_1 to aft_sent_4) are included.
* ```label:``` The interpretation of the answer. For answers in the training dataset, the interpretation is obtained by the polar keywords and thus can only be ```yes``` or ```no```. For answers in the benchmark dataset, the interpretation is made by human annotators and can be ```yes```, ```no``` or ```middle (neither yes nor no)```.



# Citation

```


@inproceedings{Wang2024Interpreting,
  title={Interpreting Answers to Yes-No Questions in Dialogues from Multiple Domains},
  author={Zijie Wang and Farzana Rashid and Eduardo Blanco},
  year={2024},
  url={https://arxiv.org/abs/2404.16262}
}

```

This work is a follow-up of our previous work on interpreting answers in mutliple languages.

```
@inproceedings{wang-etal-2023-interpreting,
    title = "Interpreting Indirect Answers to Yes-No Questions in Multiple Languages",
    author = "Wang, Zijie  and
      Hossain, Md  and
      Mathur, Shivam  and
      Melo, Terry  and
      Ozler, Kadir  and
      Park, Keun  and
      Quintero, Jacob  and
      Rezaei, MohammadHossein  and
      Shakya, Shreya  and
      Uddin, Md  and
      Blanco, Eduardo",
    editor = "Bouamor, Houda  and
      Pino, Juan  and
      Bali, Kalika",
    booktitle = "Findings of the Association for Computational Linguistics: EMNLP 2023",
    month = dec,
    year = "2023",
    address = "Singapore",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.findings-emnlp.146",
    pages = "2210--2227",
    abstract = "Yes-no questions expect a yes or no for an answer, but people often skip polar keywords. Instead, they answer with long explanations that must be interpreted. In this paper, we focus on this challenging problem and release new benchmarks in eight languages. We present a distant supervision approach to collect training data, and demonstrate that direct answers (i.e., with polar keywords) are useful to train models to interpret indirect answers (i.e., without polar keywords). We show that monolingual fine-tuning is beneficial if training data can be obtained via distant supervision for the language of interest (5 languages). Additionally, we show that cross-lingual fine-tuning is always beneficial (8 languages).",
}
```