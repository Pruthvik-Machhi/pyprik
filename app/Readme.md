# `pyprik`

## Overview

This library provides a set of powerful functions designed to assist in data analysis, data preprocessing, and the development of recommendation engines. It offers tools for flexible matching of data entries based on character similarity, making it ideal for scenarios where exact matches may not be available. The library is particularly useful in recommendation systems where close matches need to be identified from a large dataset.

### `find_matching(dataset, requirements)`

#### Purpose
The `find_matching` function is designed to compare a dataset against specified requirements and identify matching entries. It helps you find rows in your dataset that best match the criteria provided.

#### Parameters
- `dataset` (DataFrame): The dataset to be checked.
- `requirements` (dict): A dictionary where keys are column names and values are the required values for matching.

#### Returns
- `DataFrame`: A new DataFrame with additional columns indicating whether each row matches the specified requirements.

---

### `extract_characters(s)`

#### Purpose
The `extract_characters` function is used to extract alphanumeric characters from a given string. It converts the string to lowercase and counts the occurrence of each alphanumeric character.

#### Parameters
- `s` (str): The input string from which to extract characters.

#### Returns
- `Counter`: A Counter object containing the counts of each alphanumeric character in the string.

---

### `character_match_score(user_input, feature_value)`

#### Purpose
The `character_match_score` function calculates the similarity between two strings based on their alphanumeric characters. It compares the characters in the user input and a feature value, then computes a match score based on the intersection of character counts.

#### Parameters
- `user_input` (str): The user input string to be compared.
- `feature_value` (str): The string from the dataset to compare against.

#### Returns
- `int`: The match score indicating the number of matching characters between the two strings.

---

### `find_closest_match(user_input, feature_values)`

#### Purpose
The `find_closest_match` function identifies the closest matching value from a list of feature values based on character similarity. It is useful when an exact match is not found, allowing the user to find the next best option.

#### Parameters
- `user_input` (str): The user input string to be matched.
- `feature_values` (list): A list of feature values to compare against.

#### Returns
- `str`: The feature value with the highest character match score.

---

### `find_top_matching(dataset, requirements, top_n, g=None)`

#### Purpose
The `find_top_matching` function ranks entries in a dataset based on how well they match specified requirements. It calculates a total match score for each entry and returns the top N matching entries. This function can also return a specific column along with the match score if specified.

#### Parameters
- `dataset` (DataFrame): The dataset containing the data to be matched.
- `requirements` (dict): A dictionary where keys are column names and values are the required values for matching.
- `top_n` (int): The number of top matching entries to return.
- `g` (str, optional): A specific column to return along with the match score.

#### Returns
- `DataFrame`: A DataFrame containing the top N matching entries. If `g` is provided, it returns that column along with the match score; otherwise, it returns the entire matching dataset.

---
