# **Scalable Class Imbalance Solutions in Big Data using Apache Spark and SMOTE Ensembles**

 ![Apache Spark](https://img.shields.io/badge/Apache%20Spark-3.x-orange?logo=apachespark) 
 ![Python](https://img.shields.io/badge/Python-3.x-blue)
 ![MLlib](https://img.shields.io/badge/MLlib-Spark%20MLlib-yellow)
 ![Imbalanced Learn](https://img.shields.io/badge/imbalanced--learn-SMOTE%20adaptation%20for%20Spark-green)
 ![Pandas](https://img.shields.io/badge/Pandas-Data%20Manipulation-lightgrey?logo=pandas)
 ![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-blue)  

## **Overview**
This project explores **scalable solutions** for handling **class imbalance** in large datasets by combining **distributed oversampling techniques (SMOTE)** with **ensemble machine learning methods** in an **Apache Spark** environment.

The implementation leverages PySpark for **distributed data processing**, ensuring scalability and efficiency when dealing with large datasets.

---

## **Objectives**
- Address **class imbalance** in large datasets using **Distributed SMOTE**.
- Implement and evaluate **ensemble classifiers** (Random Forest, Gradient Boosted Trees).
- Measure **execution time** and **scalability** in a distributed environment.
- Demonstrate an **end-to-end pipeline** from preprocessing to evaluation on big data.

---

## **Dataset**
- **Source**: Diabetes Health Indicators Dataset  
- **Format**: CSV (`Diabetes_dataset.csv`)  
- **Target Variable**: `Diabetes_binary` (binary classification)  
- **Size**: ~250,000 records  
- **Imbalance**: Significant skew towards the negative class.

---

## **Technologies & Libraries**
- **Apache Spark (PySpark)** – Distributed data processing
- **Python 3.x**
- **MLlib** – Machine learning in Spark
- **Imbalanced-learn** – SMOTE adaptation for Spark
- **Pandas** – Data manipulation (local analysis)
- **Matplotlib** – Result visualization

---

## **Methodology**
1. **Data Loading & Exploration**  
   - Load dataset into Spark DataFrame  
   - Check for missing values, imbalance ratio

2. **Distributed SMOTE for Class Balancing**  
   - Apply SMOTE to oversample minority class in Spark
   - Maintain scalability for large datasets

3. **Feature Engineering**  
   - VectorAssembler for Spark ML
   - Scaling & normalization

4. **Model Training**  
   - **Random Forest Classifier** (Spark MLlib)
   - **Gradient Boosted Trees**
   - Comparison with baseline (no balancing)

5. **Evaluation Metrics**  
   - Precision, Recall, F1-Score
   - Execution time
   - Scalability test with different cluster sizes

---

## **Execution**
### **Prerequisites**
- Apache Spark 3.x  
- Python 3.x  
- Install dependencies:
```bash
pip install pyspark pandas matplotlib imbalanced-learn
```

## **Results Summary**
- **Distributed SMOTE** significantly improved **Recall** without drastically affecting **Precision**.  
- **Random Forest** achieved the best balance between performance and execution time.  
- **Scalability tests** showed near-linear speedup when increasing worker nodes.  

### **Example Output**
| Model                  | Precision | Recall | F1-Score | Execution Time (s) |
|------------------------|-----------|--------|----------|--------------------|
| Random Forest (SMOTE)  | 0.82      | 0.78   | 0.80     | 120                |
| Gradient Boosted Trees | 0.84      | 0.75   | 0.79     | 150                |
| Baseline RF            | 0.88      | 0.62   | 0.73     | 95                 |


