Link of the Topsis Package: https://pypi.org/project/topsis-102217115/1.1/
## PROJECT DESCRIPTION 

TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution) is a method used to evaluate and rank alternatives by comparing them to an ideal solution. It calculates how close each option is to the best possible outcome and how far it is from the worst. By considering multiple criteria and their importance, TOPSIS helps make clear and logical decisions, often used in areas like project selection, resource allocation, and performance evaluation. Its simplicity and effectiveness make it a popular choice for solving complex problems.

### How does it work?

Suppose you are deciding between various smartphone models by comparing features such as price, storage, camera quality, and design. Rather than guessing, TOPSIS processes the data by normalizing it, weighting each criterion based on its importance (e.g., prioritizing camera quality over design), and determining the distance of each model from the optimal solution. The model nearest to the "perfect scenario" receives the highest rank.

### Prerequisites

To get started, ensure you have the following:

- **Python**: Version 3.7 or higher (preferably).
- **Pandas**: For data handling and manipulation.
- **NumPy**: For numerical calculations.

To install the dependencies, just run:
```bash
pip install pandas
pip install numpy
```

### How to run the script?

#### Command-Line Execution
Here is the command you will use to run the script:
```bash
topsis <inputFileName> <Weights> <Impacts> <resultFileName>
```

Where:
inputFileName: is your CSV file that holds the data. It should have one column for alternatives and the rest for decision-making criteria (e.g., price, storage, camera).
Weights: is a comma-separated string that specifies the importance (weight) of each criterion.
Impacts: is another comma-separated string, indicating whether a criterion is beneficial (+) or non-beneficial (-).
resultFileName: is where you want to save the output, containing the scores and ranks.

#### Example
Let us say we have a CSV file named input_data.csv and we want to weigh the features as 20%, 30%, 30%, and 20%, respectively, with the first three being beneficial and the last one (Looks) being non-beneficial.

Run:
```bash
topsis input_data.csv "0.2,0.3,0.3,0.2" "+,+,+,-" result.csv
```
This command will process the data, calculate the scores, and save the results in a file called result.csv.

### Input File Structure

The CSV file should look like this:


| Model | Price | Storage | Camera | Looks |
|-------|-------|---------|--------|-------|
| M1    | 250   | 16      | 12     | 5     |
| M2    | 200   | 16      | 8      | 3     |
| M3    | 300   | 32      | 16     | 4     |
| M4    | 275   | 32      | 8      | 4     |
| M5    | 225   | 16      | 16     | 2     |

Here, each row represents a different alternative (e.g., smartphone model) and each column represents a decision-making criterion.

### Output Format

After running the decision-making script, the output includes the calculated **Score** and **Rank** for each model:

| Model | Price | Storage | Camera | Looks | Score   | Rank |
|-------|-------|---------|--------|-------|---------|------|
| M1    | 250   | 16      | 12     | 5     | 0.4459  | 4    |
| M2    | 200   | 16      | 8      | 3     | 0.3700  | 5    |
| M3    | 300   | 32      | 16     | 4     | 0.6299  | 1    |
| M4    | 275   | 32      | 8      | 4     | 0.4936  | 2    |
| M5    | 225   | 16      | 16     | 2     | 0.4758  | 3    |

### Explanation

- **Score**: The score is calculated based on a weighted evaluation of the decision-making criteria.
- **Rank**: Models are ranked based on their scores, with `1` being the highest rank.


### License

This project is licensed under the MIT License. Feel free to use, modify, or contribute!
