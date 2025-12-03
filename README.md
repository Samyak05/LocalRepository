# Privacy-Preserving Credit Risk Analysis using Federated SecureBoost and Homomorphic Encryption

## 📌 Project Overview
This project implements a **privacy-preserving framework** for credit risk analysis in the financial sector. It addresses the "data island" problem—where banks and fintech institutions cannot share raw user data due to privacy regulations (like GDPR)—by enabling collaborative model training without data exposure.

We synergize **Vertical Federated Learning (VFL)** with the **CKKS Homomorphic Encryption** scheme to train a **SecureBoost (Gradient Boosting)** model. This allows multiple parties to compute gradients and update a shared model on encrypted data, ensuring zero leakage of raw customer information.

## 🚀 Key Features
* **Vertical Federated Learning (VFL):** Enables collaboration between parties holding different features for the same users (e.g., Bank + Fintech).
* **CKKS Homomorphic Encryption:** Supports encrypted floating-point arithmetic for precise gradient aggregation.
* **SecureBoost Implementation:** A privacy-preserving adaptation of XGBoost for distributed tabular data.
* **High Utility:** Retains **~96%** of the predictive performance (AUC 0.737) of a centralized baseline (AUC 0.769).
* **Scalability Analysis:** Includes benchmarks comparing 2-Party vs. 4-Party setups and encryption overhead analysis.

## 📂 Repository Structure
* `1.VFL + HE 2 Party.ipynb`: Core implementation of the 2-party VFL SecureBoost framework using TenSEAL and PySyft logic.
* `2. Parties Comparison.ipynb`: Scalability experiments comparing model performance on 2-party vs. 4-party data splits.
* `3. Hyperparameters.ipynb`: Scripts for hyperparameter tuning (learning rate, tree depth, binning) to optimize the secure model.
* `4. Performance_Overhead_Analysis.ipynb`: Benchmarking scripts to measure training latency, memory usage, and communication overhead.
* `5. Encryption Time.ipynb`: Micro-benchmarks for CKKS encryption, decryption, and homomorphic arithmetic operations.
* `Seminar_Research_Paper.pdf`: The accompanying research paper detailing the methodology, math, and full results.

## 🛠️ Tech Stack
* **Language:** Python 3.10+
* **Machine Learning:** XGBoost, Scikit-Learn, Pandas, NumPy
* **Cryptography & FL:** TenSEAL (CKKS), PyFhel, PySyft (Simulated)
* **Visualization:** Matplotlib, Seaborn

## 📊 Results Summary
| Model Type | Test AUC | Privacy Level |
| :--- | :--- | :--- |
| **Centralized XGBoost** | 0.769 | None (Raw Data Shared) |
| **SecureBoost (Ours)** | **0.737** | **High (Homomorphic Encryption)** |

* **Performance:** The privacy-preserving model successfully identified key risk factors without accessing raw data.
* **Overhead:** Encryption introduces significant latency (training takes minutes/hours vs. seconds), highlighting the need for future hardware acceleration (GPU).

## 🔧 Setup & Installation
1.  Clone the repository:
    ```bash
    git clone [https://github.com/your-username/secure-credit-risk-vfl.git](https://github.com/your-username/secure-credit-risk-vfl.git)
    cd secure-credit-risk-vfl
    ```
2.  Install dependencies:
    ```bash
    pip install tenseal pyfhel xgboost scikit-learn pandas numpy matplotlib
    ```
3.  Run the notebooks in order (starting with `1.VFL + HE 2 Party.ipynb`).

## 👥 Contributors
* **Samyak Shriram Gedam**
* **Rohit Kumar Sah**
* **Anusha Hegde H**

## 📄 License
This project is open-source and available under the MIT License.
