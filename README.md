# EvalLLM: Framework for Evaluating Robustness and Fairness in LLMs Using Metamorphic Testing

## Overview

EvalLLM is a framework designed to evaluate the robustness and fairness of Large Language Models (LLMs) through metamorphic testing. This method involves manipulating common human errors in text inputs and making changed to the demographic details of the input to evaluate the LLM-based applications performance. The framework supports:

- **6 Parameterized Metamorphic Relations (PMRs)** for evaluating robustness by simulating various human errors.
- **2 Parameterized Metamorphic Relations (PMRs)** for assessing fairness by altering demographic details.

## Prerequisites

- Python >= 3.8
- Required Python packages. Install them using:
  ```bash
  pip install -r requirements.txt
- To test the plm-icd application, set up the plm-icd environment by cloning the [plm-icd](https://github.com/MiuLab/PLM-ICD) repository and following the setup instructions provided there.
- Move the folders from EvalLLM to the plm-icd directory. 

## Steps to Follow

### Running PMRs for Modifying Inputs

1. **Open the Notebook:**
   - Open the [mr_execution](notebook/mr_execution.ipynb) notebook in Jupyter or another compatible environment.

2. **Execute Initial Cells:**
   - Run the cells that include the following functions to prepare the data and perform initial calculations:
     ```python
     write_to_csv()
     preprocessing()
     cosine_similarity_score()
     transformer_similarity_score()
     ```

3. **Invoke PMR:**
   - Create a new cell in the notebook and invoke the desired PMR function with the required parameter values. Ensure you specify the correct parameters according to the PMR you are testing.

4. **Run `plm-icd`:**
   - Follow the instructions in the [plm-icd](https://github.com/MiuLab/PLM-ICD) repository to run `plm-icd` with the modified inputs. Ensure that you have moved the necessary folders from the `EvalLLM` directory to the `plm-icd` directory as described in the prerequisites.

### Analyzing Results from `plm-icd`

1. **Open the Notebook:**
   - Open the [output_analyzer](notebook/output_analyzer.ipynb) notebook in Jupyter or another compatible environment.

2. **Execute Analysis Cells:**
   - Run the cells that include the following functions to process and analyze the results:
     ```python
     write_to_csv()
     merge_csv()
     format_predicted_labels()
     flatten_extend()
     derive_intersecting_labels()
     cal_intersection_percent()
     ```

3. **Calculate Intersection Percent:**
   - Create a new cell and invoke the `cal_intersection_percent()` function with the input file path and the desired output file path. This function will generate the $I_{MR}$ values for each input, along with the mean $I_{MR}$ for the respective MR.