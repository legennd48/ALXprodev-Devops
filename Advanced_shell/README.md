# Advanced_shell

This directory contains advanced shell scripting exercises and automation tasks as part of the **ALXprodev-Devops** learning repository.

---

## Overview

Here you'll find practical scripts that demonstrate:
- API automation and data retrieval
- Advanced text processing with `jq`, `awk`, and `sed`
- Batch and parallel processing
- Error handling and retry logic
- Data extraction and reporting

These scripts are designed to help you practice real-world DevOps automation scenarios using Bash and common Linux command-line tools.

---

## Questions & Tasks

Below are the tasks and questions that guided the creation of the scripts in this directory:

---

### 0. API Request Automation

**Objective:** Automate the process of making API requests to the Pokémon API and saving the results to a file

**Instructions:**
- Write a shell script that makes a request to the Pokémon API and retrieves data for a specific Pokémon Pikachu.
- It should save the response to a json file: data.json
- If the request fails, it should log the error to an error file: errors.txt

---

### 1. Extract Pokémon Data

**Objective:** Use advanced text manipulation tools (jq, awk, sed) to extract specific data from the API response.

**Instructions:**
- Write a script that extracts the Pokémon’s name, height, weight, and type from the JSON file created in Task 0.
- Format the output in a human-readable way, “Pikachu is of type Electric, weighs 6kg, and is 0.4m tall.”
- You should only use these commands: jq, awk, sed

---

### 2. Batch Data Retrieval

**Objective:** Automate the retrieval of data for multiple Pokémon and store it in separate files.

**Instructions:**
- Create a script that loops through a list of Pokémon [Bulbasaur, Ivysaur, Venusaur, Charmander, Charmeleon]
- For each Pokémon, retrieve its data from the API and save it to a separate file named after the Pokémon (e.g., pikachu.json, bulbasaur.json…).
- Handle any potential rate-limiting issues by adding a delay between requests.

---

### 3. Summarize Pokémon Data

**Objective:** Create a report that summarizes data for multiple Pokémon.

**Instructions:**
- Write a shell script that reads all the JSON files generated in Task 2 and extracts the name, height, and weight of each Pokémon.
- Generate a CSV file containing the Pokémon’s name, height, and weight.
- Use awk to calculate the average height and weight of all Pokémon in the report.

---

### 4. Error Handling and Retry Logic

**Objective:** Add robust error handling and retry logic for API requests.

**Instructions:**
- Modify the script from Task 2 to handle potential errors (e.g., network issues, invalid Pokémon names).
- If an API request fails, implement a retry mechanism that attempts the request up to 3 times before logging the error and skipping to the next Pokémon.

---

### 5. Parallel Data Fetching

**Objective:** Speed up data retrieval using parallel processing.

**Instructions:**
- Write a script that fetches data for these Pokémon [Bulbasaur, Ivysaur, Venusaur, Charmander, Charmeleon] in parallel by leveraging background processes and process management tools.
- Ensure that the script handles background processes properly and waits for all processes to complete before moving to the next step.

---

## Directory Contents

- **apiAutomation-0x00 / apiAutomation-0x00.sh**  
  Automate API requests to the Pokémon API and save results to `data.json` with error logging.

- **data_extraction_automation-0x01 / data_extraction_automation-0x01.sh**  
  Extract and format Pokémon data (name, type, height, weight) from the JSON response.

- **batchProcessing-0x02 / batchProcessing-0x02.sh**  
  Fetch data for multiple Pokémon, with error handling and retry logic, saving each to its own file.

- **batchProcessing-0x04 / batchProcessing-0x04.sh**  
  Fetch Pokémon data in parallel using background processes for faster automation.

- **summaryData-0x03 / summaryData-0x03.sh**  
  Summarize all Pokémon data into a CSV report and calculate average height and weight.

- **pokemon_data/**  
  Directory containing individual Pokémon JSON data files.

- **pokemon_report.csv**  
  Generated CSV report summarizing Pokémon data.

- **errors.txt, pokemon_errors.log, pokemon_errors_parallel.log**  
  Error logs for failed API requests.

- **data.json**  
  Example API response for Pikachu.

---

## Usage

1. **Make scripts executable**  
   ```bash
   chmod +x *.sh
   ```

2. **Run the scripts as needed**  
   For example:
   ```bash
   ./apiAutomation-0x00.sh
   ./data_extraction_automation-0x01.sh
   ./batchProcessing-0x02.sh
   ./batchProcessing-0x04.sh
   ./summaryData-0x03.sh
   ```

3. **Check output files and logs**  
   - JSON data in `pokemon_data/`
   - Reports in `pokemon_report.csv`
   - Errors in `errors.txt` or `pokemon_errors.log`

---

## Requirements

- Bash shell
- `curl` for API requests
- `jq` for JSON parsing
- `awk`, `sed` for text processing

Install missing tools with:
```bash
sudo apt update
sudo apt install curl jq
```

---

## Notes

- Scripts are modular and can be updated or extended for more Pokémon or different APIs.
- Error handling and retry logic are included for robustness.
- Parallel processing is demonstrated for efficient data fetching.

---

Happy scripting and DevOps learning!