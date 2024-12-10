<div align="center">
  <img src="https://github.com/Solrikk/MagicXML/blob/main/assets/gif/taxi-data-science-graphs-on-pc-screen.gif" width="30%"/>
</div>


<div align="center"> <h3> <a href="https://github.com/Solrikk/MagicXML/blob/main/README.md">英語</a> | <a href="https://github.com/Solrikk/MagicXML/blob/main/README_RU.md">ロシア語</a> | <a href="https://github.com/Solrikk/MagicXML/blob/main/README_GE.md">ドイツ語</a> | <a href="https://github.com/Solrikk/MagicXML/blob/main/README_JP.md">⭐日本語⭐</a> | <a href="README_KR.md">韓国語</a> | <a href="README_CN.md">中国語</a> </h3> </div>

-----------------

# Magic-XML ✨

🚀 **_Magic-XMLは https://xmlmagic.ru で利用可能です_** 🚀

**_Magic-XML_** は、XMLファイルからCSV形式へのデータの便利で迅速な変換のために開発された現代的なWebアプリケーションです。このアプリケーションは、リクエスト処理における高性能を保証するためにFastAPIの力を活用し、テキスト情報の効率的な分析と分類のために機械学習アルゴリズムと自然言語処理を使用しています。Magic-XMLは、大量のXMLデータを扱い、その最適化と分析の単純化を目指すデータアナリスト、開発者、および誰にとっても理想的です。


**依存関係:**
- `fastapi` - 自動ドキュメント機能を持つAPI構築用のフレームワーク。
- `uvicorn` - FastAPIアプリケーションを実行するためのASGIサーバー。
- `requests` - HTTPリクエストを行うためのライブラリ。
- `xml.etree.ElementTree` - XML処理用のモジュール。
- `csv` - CSVファイルを扱うためのモジュール。
- `os` - オペレーティングシステムとの対話に使用されるモジュール、ディレクトリ作成に使用。
- `Jinja2Templates` - FastAPIからのJinja2テンプレートを扱うためのもの。
- `StaticFiles` - 静的ファイルを提供するためのもの。
- `BaseModel` - `pydantic`からのデータバリデーションのため。
- `FileResponse` - レスポンスでファイルを送信するためのもの。
- `spacy` - カテゴリゼーションのために使用される自然言語処理のため。
- `TfidfVectorizer` - テキストベクトル化のため。
- `cosine_similarity` - コサイン類似度の計算のため。
- `re` - 正規表現を扱うためのモジュール。
## ⚠️ Getting Started with MagicXML: ⚠️

Welcome to MagicXML, an innovative application designed to process and transform your XML data effortlessly. Whether you're dealing with large datasets, seeking to enhance your data analysis workflow, or needing to automate data processing, MagicXML offers powerful tools and features to meet your needs.

### Prerequisites:

Before you dive into MagicXML, ensure you have the following installed:

- Python (version 3.8 or later) [Download Python](https://www.python.org/downloads/)
- pip (usually comes with Python installation)
- An active internet connection for initial setup and downloading dependencies.

### Installation:

Follow these simple steps to get MagicXML up and running on your system:

1. **Clone the Repository:**

   First, clone the MagicXML repository to your local machine using git:

   ```bash
   git clone https://github.com/Solrikk/MagicXML.git
   cd MagicXML

-----------------

**Application Structure:**
- `FastAPI Application`: Initializes the main application with FastAPI, configures the routes for static files and the `Jinja2 templating engine`.
- `LinkData class (Pydantic model)`: A model for validating incoming data received through a `POST request to /process_link`.

**Data processing functions:**
- `Get_category_replacement()`: A function for categorization based on the cosine similarity between vectors.
- `Load_custom_categories()`: Loading custom categories from a CSV file.
- `Remove_unwanted_tags()`: Cleaning product descriptions of HTML tags.
- `Process_link()`: The main function for processing an XML link, extracting, and saving data to a CSV file.

**FastAPI Routes:**
- `GET /`: Display the home page through a Jinja2 template.
- `POST /process_link`: Accepts data for processing the link and generates a CSV file.
- `GET /download/data_files/{filename}`: Ability to download generated CSV files.

## _Adapting Categories Using TF-IDF and Cosine Similarity:_ 
The program employs `TfidfVectorizer` and `cosine similarity` to determine the most suitable custom category for a product based on its original category name obtained from XML. This showcases an interesting approach to the classification or `category mapping` task, where `machine learning methods` are used instead of direct matching to enhance the accuracy and flexibility of the process.

<img src="https://github.com/Solrikk/MagicXML/blob/main/assets/TF-IDF%20Visualization/TF-IDF%20Visualization.png" width="95%" /> 

more info[[created](https://github.com/Solrikk/MagicXML/tree/main/assets/TF-IDF%20Visualization)]

**Cosine Similarity** is a metric used to determine how similar two entities are irrespective of their size. Mathematically, it measures the cosine of the angle between two vectors projected in a multi-dimensional space. This concept comes from the field of linear algebra and can be applied in various contexts such as data analysis, natural language processing (NLP), and information retrieval systems.

> The idea behind `cosine similarity` is quite simple. Imagine you have two vectors (arrays of numbers), each representing an entity's features in a multidimensional space. The "angle" between these vectors gives an indication of their similarity. If the angle is 0 degrees, it means the vectors are perfectly aligned, indicating a similarity score of 1, which is the maximum similarity. Conversely, if the angle is 90 degrees, the cosine similarity is 0, indicating no similarity. Angles between 0 and 90 degrees result in a similarity score somewhere between 0 and 1, with a smaller angle yielding a higher score.

<img src="https://github.com/Solrikk/MagicXML/blob/main/assets/Visualization%20Cosine%20Similarity%20Matrix/Visualization%20Cosine%20Similarity%20Matrix.png" width="100%" />

more info[[created](https://github.com/Solrikk/MagicXML/tree/main/assets/Visualization%20Cosine%20Similarity%20Matrix)]

- TF (term frequency) is the ratio of the number of occurrences of a certain word to the total number of words in the document.

<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/8ef207eb03f6e9b6f71e73739f45b5179b4f17cc" width="15%" />

- IDF (Inverse Document Frequency) - the inversion of the frequency with which a certain word appears in the documents of a collection. Karen Spärck Jones is the founder of this concept. Taking into account IDF reduces the weight of commonly used words. For each unique word within a specific collection of documents, there is only one IDF value.

<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/b88834044365dea6aedba224eabe7147d4d328ef" width="30%" />

```Python
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.metrics.pairwise import cosine_similarity

def get_category_replacement(original_category_name, custom_categories):
    vectorizer = TfidfVectorizer()
    all_categories = [original_category_name] + custom_categories
    tfidf_matrix = vectorizer.fit_transform(all_categories)
    cosine_similarities = cosine_similarity(tfidf_matrix[0:1], tfidf_matrix[1:]).flatten()
    return custom_categories[cosine_similarities.argmax()]
```

1. **Category Vectorization:**
Using TF-IDF, the program transforms the names of the categories (one of the original names and a list of custom categories) into a vector representation. This means that each category becomes a vector in a multidimensional space, where each dimension represents a word from the category corpus, and the value represents the importance of the word in the context of the category.
2. **Finding Cosine Similarity:**
Then, the program calculates the cosine similarity between the vector of the original category and the vectors of each custom category. This compares how close the custom categories are to the original category in terms of their contextual similarity.
3. **Selecting the Most Suitable Category:**
After calculating the cosine similarities, the custom category with the highest similarity value relative to the original category is selected. This means that this category is considered the most suitable or closest to the original category in terms of semantic content.

> This concept is particularly useful in text analysis for comparing documents or texts. By converting texts into vectors (using techniques such as TF-IDF), where each dimension represents a specific word and the value in that dimension represents the significance of the word, we can compare these vectors to find out how similar the texts are to each other. This is often used in search engines, plagiarism checkers, and recommendation systems to find or suggest content that is most similar to a given input.

## _Asynchronous Request Handling:_
FastAPI is built on top of Starlette and allows the handling of requests asynchronously using async and await keywords. This enables the application to scale and serve a large number of requests efficiently, improving performance on `I/O (Input/Output)` operations such as requests to external `APIs` or file read operations. In the application, asynchronous handling can be particularly useful in scenarios like loading files through an endpoint `/download/data_files/{filename}`, where asynchronous file reading can significantly reduce waiting time for the client.

## _Handling endpoints with asynchronous functions:_

- In the code, an asynchronous endpoint process_link_post is defined through the decorator `@app.post("/process_link")`. This endpoint asynchronously processes `POST requests` by sending link data (for example, a URL to process). Using the async keyword before the function definition indicates that the function will execute asynchronously.
- Similarly, the asynchronous method download_csv handles `GET requests` for downloading files. This also allows for the handling of file download requests without blocking the main execution thread of the application.

## _Working with Text and Natural Language_
> Using spaCy and TfidfVectorizer from scikit-learn for text categorization demonstrates how machine learning tools can be effectively applied in web applications. spaCy is used for preprocessing text in Russian, which is important for the accurate operation of categorization, as text processing includes many aspects, such as lemmatization and stop-word removal, which significantly affect the final accuracy. TfidfVectorizer converts text into a vector representation, allowing then to calculate the cosine similarity between vectors, which is used to select the most suitable category for the text.

<img src="https://github.com/Solrikk/MagicXML/blob/main/assets/SpaCy%20Dependency%20Visualization/SpaCy%20Dependency%20Visualization.jpeg" width="150%" />

## _XML Processing and CSV Generation_
The application involves parsing XML files to extract product data, demonstrating the ability to work with various data formats. After extracting and classifying the data, it is saved in CSV format, which is a widely accepted standard for exchanging tabular data and can be easily imported into various systems and applications for further analysis.

## _Technical Implementation of the Web Interface_
The application uses Jinja2Templates for generating dynamic HTML content. This allows the creation of a more interactive and user-oriented interface. Together with serving static files through StaticFiles, it creates a full-fledged web interface for interacting with the application, eliminating the need for the user to work directly with the API or command line.

## _Data Validation with Pydantic_
Using Pydantic models for validating incoming data not only ensures the correctness of the data but also allows for the automatic generation of API documentation. This significantly simplifies both the development and the use of the API, as clients can precisely know what data and in what format are expected on input.

## _Error and Exception Handling_
The application includes exception handling, such as a URL access error or a file reading error. This ensures the application's stability and provides informative feedback to the user about the issue through FastAPI's HTTP exception mechanisms.

## _Cloning the Repository: Clone the application code to your machine._
- Installing dependencies: Install the necessary dependencies using `pip install -r requirements.txt.`
- Running the server: Start the application with the command `uvicorn main:app --reload.`

**Usage:**
- To process XML files, use the web interface or send a request to `/process_link` with the URL of your XML file. The resulting CSV file will be available for download via the provided link.

### Process your data in a simple and efficient way with Magic-XML!
