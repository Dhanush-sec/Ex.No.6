# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

#AI Tools Required:

# Explanation:
Experiment the persona pattern as a programmer for any specific applications related with your interesting area. 
Generate the outoput using more than one AI tool and based on the code generation analyse and discussing that. 

# Conclusion:


# Result: The corresponding Prompt is executed successfully.

Exno.6-Prompt-Engg
Name: Dhanush A
Register no:212222210004
Aim
Development of Python Code Compatible with Multiple AI Tools

Algorithm
Input file path (string) is given.

Detect file extension (.csv or .json).

If file is .csv:

Use csv.DictReader() to read rows into dictionaries.
If file is .json:

Use json.load() to parse JSON objects into dictionaries.
Ensure single dictionary objects are converted into a list.
Return data as a list of dictionaries.

Use this unified structure to integrate with multiple AI tools for insights.

Program (Python Code)
import csv
import json
import os

def read_file_to_dicts(file_path):
    """
    Reads a CSV or JSON file and returns a list of dictionaries.
    Supports .csv and .json file formats.
    """
    _, ext = os.path.splitext(file_path)
    ext = ext.lower()
    
    data = []
    
    if ext == ".csv":
        with open(file_path, mode="r", encoding="utf-8") as f:
            reader = csv.DictReader(f)
            data = [row for row in reader]
            
    elif ext == ".json":
        with open(file_path, mode="r", encoding="utf-8") as f:
            data = json.load(f)
            if isinstance(data, dict):
                data = [data]
    
    else:
        raise ValueError("Unsupported file format. Please provide .csv or .json")
    
    return data


# Example Usage:
# csv_data = read_file_to_dicts("sample.csv")
# json_data = read_file_to_dicts("sample.json")
Output
Example CSV Input:
name,age,city
Alice,25,London
Bob,30,New York
Example JSON Input:
[
  {"name": "Alice", "age": 25, "city": "London"},
  {"name": "Bob", "age": 30, "city": "New York"}
]
Unified Output (List of Dicts):
[
  {"name": "Alice", "age": "25", "city": "London"},
  {"name": "Bob", "age": "30", "city": "New York"}
]

   

