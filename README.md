# 📊 Customer Segmentation using Unsupervised Learning

**Created By:** *Sangeeth M*

---

## 🔹 Introduction

Businesses often have thousands of customers with different behaviors. Instead of treating all customers the same, companies use segmentation to group similar customers together.

This project uses **Unsupervised Learning (Clustering)** to:

- Identify different customer groups (high-value, frequent buyers, at-risk, etc.).
- Provide business insights for marketing strategies.
- Apply machine learning models like **K-Means** and **Hierarchical Clustering**.

We use the **Online Retail Dataset (Kaggle)**, which contains transactional data (invoices, customers, products, prices).

---

## 🔄 Workflow of the Project

1. Load dataset  
2. Clean & preprocess  
3. Create RFM Features (Recency, Frequency, Monetary)  
4. Standardize data  
5. Apply PCA (reduce dimensions)  
6. Apply Clustering (K-Means + Hierarchical)  
7. Visualize using PCA and t-SNE  
8. Evaluate clusters  
9. Interpret business meaning  

---

## 📝 Code Explanation

### **Step 1: Import Libraries**
- Data handling → `pandas`, `numpy`  
- Visualization → `matplotlib`, `seaborn`  
- ML Models → `KMeans`, `PCA`, `t-SNE`, `Hierarchical`  
- Evaluation → `silhouette`, `DBI`  

---

### **Step 2: Load Dataset**
- Each row = one product purchase (quantity, price, customer ID, invoice date).  

---

### **Step 3: Data Cleaning**
- Remove customers without IDs.  
- Remove negative quantities (returns).  
- Create `TotalPrice = Quantity × Price`.  
- Convert `InvoiceDate` for Recency calculation.  

---

### **Step 4: Feature Engineering (RFM Model)**  
- **Recency** → Days since last purchase.  
- **Frequency** → Total number of purchases.  
- **Monetary** → Total money spent.  

This gives **customer-level features** instead of transaction-level.  

---

### **Step 5: Standardization**  
- Features scaled using `StandardScaler (mean=0, variance=1)`.  

---

### **Step 6: Dimensionality Reduction with PCA**
- Reduce 3D (Recency, Frequency, Monetary) to 2D.  
- Preserves variance & enables visualization.  

---

### **Step 7: K-Means Clustering**
- Partition data into **K clusters**.  
- Best `K` found using **elbow method (3–5)**.  

---

### **Step 8: Final Clustering**
- Applied **K-Means with 4 clusters**.  
- Visualized with PCA → each color = customer segment.  

---

### **Step 9: Hierarchical Clustering**
- Builds tree-like **dendrogram**.  
- Shows grouping at different similarity levels.  

---

### **Step 10: t-SNE Visualization**
- Nonlinear technique for better visualization.  
- Shows clusters more clearly than PCA.  

---

### **Step 11: Cluster Evaluation**
- **Silhouette Score** → closer to 1 = good separation.  
- **Davies-Bouldin Index** → lower = better.  

---

### **Step 12: Cluster Profiling**
- Profile clusters:  
  - Cluster 0 → High Value  
  - Cluster 1 → At-Risk  
  - Cluster 2 → Frequent Buyers  
  - Cluster 3 → Casual Buyers  

---

## 💡 Business Insights

- **Cluster 0: High Value Customers** → Loyal, frequent, high-spending. Target with premium offers.  
- **Cluster 1: At-Risk Customers** → Haven’t bought recently. Need re-engagement campaigns.  
- **Cluster 2: Frequent Buyers** → Active but low-spending. Upselling opportunities.  
- **Cluster 3: Casual Buyers** → Rare purchases. Use discounts & promotions.  

---

## ✅ Conclusion

This project shows how unsupervised learning can turn raw purchase data into clear customer segments. By applying clustering with PCA and validation metrics, we identified actionable groups that enable businesses to target marketing, boost retention, and drive growth.  

---

📌 *Dataset Source:* [Kaggle – Online Retail Dataset](https://www.kaggle.com/)  
📌 *Tech Stack:* Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn  

---
