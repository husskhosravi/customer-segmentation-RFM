### 📊 Project Title  
Customer segmentation using RFM (Recency, Frequency, Monetary) analysis and KMeans clustering

---

### 🔍 Overview  
Retaining existing customers is often more cost-effective than constantly seeking new ones. Businesses must recognise that if customer churn exceeds the rate of new acquisitions, overall transaction volume and revenue will inevitably decline. Prioritising customer retention ensures a stable customer base and more predictable sales outcomes, making it just as vital as attracting fresh leads.

Not every transaction is profitable, nor is every client willing to spend. Consequently, it’s important for marketers to align resources with the potential value each customer brings. By focusing on targeted strategies and customised offerings, marketers can maximise return on investment for their promotional efforts.

In this project, we apply RFM (Recency, Frequency, Monetary) analysis to segment customers based on their purchase history. Using a real e-commerce dataset, we calculate how recently customers made purchases, how often they buy, and how much they spend. With these metrics, we create distinct groups and tailor deals or discounts accordingly. This approach helps marketers identify high-value customers, bolster engagement, and ultimately increase customer lifetime value.

RFM segmentation is a powerful technique for strategic decision-making, allowing businesses to quickly group customers with similar behaviours and personalise marketing campaigns. By understanding each segment’s unique characteristics, marketers can deliver more relevant offers and drive stronger response rates. This data-driven method leverages existing information such as purchase patterns, browsing history, and demographics to accurately target the most promising customer segments, leading to higher loyalty and sustained growth.

---

### 📁 Steps in the Pipeline  

## 1. 📥 Data Loading  
The dataset is imported with `pandas`, ensuring missing `CustomerID` rows are dropped and cancelled orders are excluded. Basic data cleaning operations (e.g., handling negative quantities) are performed to prepare for analysis.

## 2. 🔧 Feature Engineering  
A `TotalSum` column is created (Quantity × UnitPrice). A log transformation is applied to Monetary to reduce skewness. These steps ensure the data is properly scaled and ready for clustering.

## 3. 📊 RFM Computation  
Recency, Frequency, and Monetary values are computed per customer. Recency is derived from the days since the last purchase, Frequency is the count of unique invoices, and Monetary is the total spend.

## 4. 📐 Data Transformation & Scaling  
Any missing values are imputed, and features are scaled with `RobustScaler` to handle outliers. This step standardises the dataset, improving clustering performance.

## 5. 🤖 Clustering & Evaluation  
KMeans is applied to the scaled features. The optimal number of clusters is determined using the Elbow Method and Silhouette Score. Final cluster labels are assigned to each customer for analysis.

## 6. 📈 Visualisation & Insights  
Pairplots reveal how clusters differ in Recency, Frequency, and Monetary. A bar chart highlights each cluster’s average spend. These visuals help interpret and validate the clusters formed.

---

### 📌 Model & Techniques  
- **KMeans Clustering**: Chosen for its simplicity and efficiency.  
- **Elbow Method & Silhouette Score**: Used to guide the choice of optimal clusters.  
- **Log Transformation & RobustScaler**: Employed to handle skewness and outliers, improving cluster separation.
---

### 📈 Results & Insights  
- **Number of Clusters**: Four segments emerge, each reflecting different purchasing patterns.  
- **High-Spend vs. Low-Spend**: Certain groups exhibit significantly higher Monetary values.  
- **Recency Differences**: Clusters vary in how recently customers made purchases, informing retention strategies.

---

### 🛠️ Tech Stack  
- **pandas**  
- **NumPy**  
- **scikit-learn**  
- **matplotlib**  
- **seaborn**  

---

### ✍️ How to Use  
1. Clone this repository and place the dataset (`OnlineRetail.csv`) in the same folder as the notebook.  
2. Install dependencies with `pip install -r requirements.txt`.  
3. Open `RFM.ipynb` in Jupyter (or any Python IDE) and run the cells sequentially.  
4. Review the cluster output and visualisations at the end of the notebook to interpret results.
