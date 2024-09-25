# Recommending-code-tokens-via-N-gram-models
> What is N-gram? <br>
  > An n-gram is a sequence of n consecutive items in a text, such as words, symbols, numbers, or punctuation. N-grams are a fundamental concept in Natural Language Processing (NLP) and are used in many text analytics applications


## Data Collection
> For every project data collection is a very important part. Researchers spent most of the time to collect the data also pre-process data. In order to collect the data, I used [SEART](https://seart-ghs.si.usi.ch/) website. By using this website anyone can collect any amount of github repositories. For this project, I only choose those repo which has at least **5000** commit. <br>
> After collecting the repositories, I've saved it in a csv file. After that I used **Python Script** to extract only java code from the repositories and saved all the files into docx file.<br>


Example of how I geetting data from the csv file and saved it to word file.
~~~python
df = pd.read_csv('results.csv')
for i in range(1, 1001):
    try:
        repo_owner, repo_name = df.at[i, 'name'].split('/')
        java_files = extract_java_files_from_github(repo_owner, repo_name)

        if java_files:
            save_to_word(doc, java_files, repo_owner, repo_name)
    except Exception as e:
        print(f'Error processing {df.at[i, "name"]}: {e}')
~~~

## Data Pre-processing
>Data preprocessing is the process of transforming raw data into a format that's easier to analyze and understand. It's a fundamental step in any projects, and is often performed before data analysis or machine learning modeling.
>![image](https://github.com/user-attachments/assets/539ba038-f2c0-4271-9e3d-2e37da119c75)
![image](https://github.com/user-attachments/assets/794733a3-df7b-4816-a401-97410c970e7a)




