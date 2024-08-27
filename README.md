# Synthetic Data Creation Project

## Project Overview

This project focuses on generating synthetic data from a real-world medical dataset. The primary goal is to maintain the statistical properties and relationships of the original data while ensuring privacy and confidentiality. The synthetic data is structurally consistent, preserving key relationships between tables.

## Project Structure

### 1. **Synthetic Data Generation Process**
The synthetic data was created using the [SDV (Synthetic Data Vault)](https://sdv.dev/) library. This tool allows for generating synthetic rows for each table while maintaining a hierarchical structure. The process starts with parent tables and moves to child tables, ensuring relational consistency across the entire dataset.

### 2. **Experiment Setup**
- **Development Environment:** Python
- **Key Libraries:** Pandas, Matplotlib, Scipy, NumPy, SDV
- **Data Modeling:** The metadata for each table was defined using SDV’s `MultiTableMetadata` class. This included setting primary keys, data types, and defining relationships between tables (e.g., primary and foreign keys). The synthetic data was generated using the `HMASynthesizer`, which was trained to learn complex distributions within the original dataset.

### 3. **Evaluation and Validation**
The synthetic data was validated to ensure it mirrors the structural and statistical properties of the original data:
- **Data Validity:** Checks included primary key uniqueness, non-null constraints, and adherence to value ranges.
- **Distribution Comparison:** Key columns like `VISITDATE`, `RESULTNUMERIC`, and `TESTTYPEID` were compared between the original and synthetic data. The analysis confirmed that the distributions were well preserved, although minor differences were noted due to noise or variations in the generation process.

### 4. **Comparative Analysis**
A thorough comparison was conducted between the synthetic and original datasets. The synthetic data closely matched the original data’s distributions and properties, validating the effectiveness of the generation process.

## How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/synthetic-data-creation.git
   ```
2. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the data generation script:
   ```bash
   python generate_synthetic_data.py
   ```

## Results
The synthetic data effectively preserves the key characteristics of the original dataset, making it suitable for various downstream tasks while ensuring data privacy.

