# Taiwan-Indictment-Summarization-Corpus (TWISC)

Taiwan-Indictment-Summarization-Corpus (TWISC) is a dataset designed for legal judgment prediction and legal text summarization. It is collected from Taiwan Ministry of Justice and covers data from 2018/06 to 2021/06.

This dataset is used in the paper [**Improving Colloquial Case Legal Judgment Prediction via Abstractive Text Summarization**](https://www.sciencedirect.com/science/article/abs/pii/S0267364923000730) published in Computer Law & Security Review (2023).

We express our gratitude to Professor Chia-Hui Chang for her guidance and advisement, and to Kuo-Chun Chien for his assistance in data collection.

You can access and download the dataset on [Hugging Face](https://huggingface.co/datasets/yxhong-tw/twisc).


## Dataset Overview

- **Source**: [Taiwan Ministry of Justice](https://psue.moj.gov.tw/psiqs)
- **Coverage**: 2018/06 - 2021/06
- **Size**: ~300K data
- **Format**: JSONL
- **Language**: Simplified Chinese (`zh-CN`)
- **License**: [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0)


## Data Collection & Processing

- **Scraping**: The dataset was collected from [psue.moj.gov.tw](https://psue.moj.gov.tw/psiqs), which is the public data search system of Taiwan Ministry of Justice.
- **Processing**: Several steps were applied to enhance data quality, including:
    - Standardizing the format.
    - Removing irrelevant information.
    - Filtering out incomplete or inconsistent data.
- **Dataset Splits**:
    - `train`: The main training set.
    - `30k_test` A test set of ~30K data, where each data contains 3 representations of facts:
        - `fact`: The original fact.
        - `bart_summary`: A summary generated using BART trained on [CNewSum](https://arxiv.org/abs/2110.10874) dataset.
        - `chatgpt_summary`: A summary generated using OpenAI's `text-davinci-002-render-paid` model.
    - `235_test`: Another test set contains 235 human-written summaries.


## Usage

To load the dataset, use the following code:

```python
from datasets import load_dataset

dataset = load_dataset("yxhong-tw/twisc")
```

## Citation

```
@article{clsr2023hong,
    title = {Improving Colloquial Case Legal Judgment Prediction via Abstractive Text Summarization},
    journal = {Computer Law & Security Review},
    volume = {51},
    pages = {105863},
    year = {2023},
    issn = {0267-3649},
    doi = {https://doi.org/10.1016/j.clsr.2023.105863},
    url = {https://www.sciencedirect.com/science/article/pii/S0267364923000730},
    author = {Yu-Xiang Hong and Chia-Hui Chang},
    keywords = {Legal judgment prediction, Legal text summarization, Abstractive text summarization, Legal artificial intelligence}
}
```

## Contact

If you have any questions, please contact [Yu-Xiang Hong](mailto:yxhong.tw@gmail.com).
