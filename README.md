# A High-Quality Multilingual Sentiment Analysis Dataset (EN/ZH)
# 一个高质量的中英双语情感分析数据集

[![License: MIT](https.img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A high-quality, re-labeled 3-class sentiment analysis dataset containing 100k Chinese (from Weibo) and 100k English (from SST-2, IMDB, Yelp, Amazon) samples. This dataset was created to provide a balanced and more reliable resource for multilingual and cross-lingual sentiment analysis tasks.

这是一个高质量、经过重新标注的三分类情感分析数据集。它包含10万条来自微博的中文数据和10万条来自多个知名英文数据集（SST-2, IMDB, Yelp, Amazon）的数据。本数据集旨在为多语言和跨语言情感分析研究提供一个更均衡、更可靠的资源。

---

## 🌟 Introduction | 项目简介

In the field of Natural Language Processing (NLP), sentiment analysis is a crucial task. However, many existing datasets suffer from noise or annotation inconsistencies. To address this, we developed this multilingual dataset by carefully selecting and re-labeling data from popular sources. The result is a more robust dataset that has demonstrated decent performance in our experiments, making it ideal for training and evaluating modern NLP models.

在自然语言处理（NLP）领域，情感分析是一项核心任务。然而，许多现有的数据集都存在噪声或标注不一致的问题。为了解决这些痛点，我们通过对多个主流数据集进行筛选和重新人工标注，构建了这个多语言数据集。最终的数据集在我们的实验中表现出良好的性能，非常适合用于训练和评估现代NLP模型。

## 📊 Dataset Details | 数据集详情

The dataset is divided into two main files: one for English and one for Chinese.

数据集被分为两个文件：一个英文数据集，一个中文数据集。

### English Dataset (`English_Sentiment_3-Class_Dataset.zip`)
* **Note:** This file is in `.zip` format due to its large size. The code example below shows how to load it directly.
* **注意：** 由于文件较大，此数据集为 `.zip` 压缩格式。下面的代码示例展示了如何直接加载它。
* **Source:** A combination and re-labeling of several famous datasets:
    * [SST-2](https.nlp.stanford.edu/sentiment/index.html) (Stanford Sentiment Treebank)
    * [IMDB Reviews](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)
    * [Yelp Reviews](https://www.yelp.com/dataset)
    * [Amazon Review Polarity](https://www.kaggle.com/datasets/bittlingmayer/amazonreviews)
* **Total Samples:** 100,000
* **Language:** English

### Chinese Dataset (`Chinese_Sentiment_3-Class_Dataset.csv`)
* **Source:** Weibo (A major Chinese microblogging platform)
* **Total Samples:** 100,000
* **Language:** Chinese (Simplified)

## 📁 Data Format | 数据格式

Both CSV files share the same simple structure, with two columns: `data` and `label`.

两个CSV文件都遵循相同的结构，包含两列：`data` 和 `label`。

| Column | Description                                    |
| :----- | :--------------------------------------------- |
| `data` | The text content of the review/post. (文本内容) |
| `label`  | The sentiment label. (情感标签)                 |

### Label Description | 标签说明
The sentiment is categorized into three classes:
情感标签被分为以下三类：

* `0`: Negative (负面)
* `1`: Neutral (中性)
* `2`: Positive (正面)

***Note:** Please verify if this mapping is correct for your dataset and adjust if necessary. / **注意：** 请根据您的数据集确认此标签映射是否正确，如有需要请自行调整。*

## 🚀 Getting Started | 如何使用

Here's a simple example of how to load and use the dataset with Python's `pandas` library. The code can directly read the English data from the `.zip` file without manual extraction.

下面是一个使用 Python `pandas` 库加载和查看数据的简单示例。该代码**无需手动解压**，即可直接从 `.zip` 文件中读取英文数据。

```python
import pandas as pd

# Define filenames
# Note: The English dataset is a zip archive.
english_dataset_path = 'English_Sentiment_3-Class_Dataset.zip'
chinese_dataset_path = 'Chinese_Sentiment_3-Class_Dataset.csv'

# Load the datasets
try:
    # Pandas can read directly from a zip file.
    # We assume the csv file inside the zip is named 'English_Sentiment_3-Class_Dataset.csv'
    df_en = pd.read_csv(english_dataset_path)
    df_zh = pd.read_csv(chinese_dataset_path)

    # Display the first 5 rows of the English dataset
    print("--- English Dataset ---")
    print(df_en.head())
    print("\nLabel Distribution:")
    print(df_en['label'].value_counts(normalize=True).sort_index())

    # Display the first 5 rows of the Chinese dataset
    print("\n--- Chinese Dataset ---")
    print(df_zh.head())
    print("\nLabel Distribution:")
    print(df_zh['label'].value_counts(normalize=True).sort_index())

except FileNotFoundError as e:
    print(f"Error: {e}")
    print("Please make sure the dataset files are in the correct directory and named correctly.")
    print("请确保数据集文件位于正确的目录下且文件名无误。")
except Exception as e:
    print(f"An error occurred: {e}")
    print("If you have trouble loading the zip file, ensure it contains one CSV file or specify the filename inside the archive.")
    print("如果加载zip文件时出错，请确保压缩包内只包含一个CSV文件，或在代码中指定内部的文件名。")

```

## 📈 Performance | 性能表现

This dataset was used in a graduation project and achieved promising results, demonstrating its quality and utility for sentiment analysis tasks. We encourage you to use it and see how it performs with your models!

本数据集已在作者的毕业设计中使用，并取得了良好的实验结果，证明了其在情感分析任务中的高质量和实用性。我们非常欢迎您使用本数据集来训练和检验您的模型！

##  citation | 如何引用

If you use this dataset in your research, please consider citing it. This helps acknowledge the effort and allows others to find the work.

如果您在您的研究中使用了本数据集，请考虑引用。这不仅是对我们工作的认可，也能帮助其他人发现这份资源。

```bibtex
@misc{lights-think_2025_multilingual_sentiment,
  author       = {lights-think},
  title        = {A High-Quality Multilingual Sentiment Analysis Dataset (EN/ZH)},
  month        = jun,
  year         = 2025,
  publisher    = {GitHub},
  howpublished = {\url{[https://github.com/lights-think/Multilingual-Sentiment-Analysis-Dataset](https://github.com/lights-think/Multilingual-Sentiment-Analysis-Dataset)}}
}
```

## 📄 License | 许可证

This dataset is released under the [MIT License](LICENSE). You are free to use, modify, and distribute it for any purpose, including commercial use.

本数据集基于 [MIT 许可证](LICENSE) 发布。您可以自由地使用、修改和分发，包括商业用途。

## 📧 Contact | 联系方式

If you have any questions, suggestions, or find any issues with the dataset, please feel free to open an issue in this repository or contact me at:

* **Email:** `lightsmile7@outlook.com`
* **GitHub:** `lights-think`

如果您对数据集有任何疑问、建议或发现任何问题，欢迎在本仓库中提交 Issue 或通过以下方式联系我：

* **邮箱:** `lightsmile7@outlook.com`
* **GitHub:** `lights-think`
