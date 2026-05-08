# Tourism-Analytics-Hotel-Recommendation

This project presents a Big Data Analytics and Recommendation System using PySpark.

Project Overview :

This project presents a Big Data Analytics and Recommendation System using PySpark. The goal is to analyze hotel booking data and generate insights, predict cancellations, and recommend hotels to users.

Technologies Used : Python / PySpark (Apache Spark) /Pandas / Matplotlib / Seaborn Spark MLlib / Scikit-learn

Dataset : This project uses a synthetic dataset generated based on a real-world hotel booking dataset.

Original dataset source: https://www.kaggle.com/datasets/kundanbedmutha/hotel-booking-reservation The dataset was adapted to represent Sri Lanka tourism data, with simulated records and modified features to support big data analytics and recommendation modeling. The synthetic dataset enables experimentation while maintaining realistic booking behavior patterns.
- Records: 50,000 hotel bookings
- Columns: 33 original + 29 engineered features
- File: "hotel_bookings_updated_2024.csv"

How to Run the Project : Install required libraries: pip install pyspark pandas matplotlib seaborn scikit-learn 
Open the notebook: Tourism_Analytics_Hotel_Recommendation.ipynb Run all cells sequentially

Project Workflow : 
1. Data Loading - PySpark CSV ingest with schema inference (50,000 records, 33 columns)
2. Data Cleaning - Duplicate removal, ADR filtering, null imputation, type casting
3. Feature Engineering - 29 new features including season, revenue, guest tier, booking status
4. EDA - Market segment analysis, cancellation rates, ADR distribution, correlation
5. K-Means Clustering - Guest segmentation (K=4 selected, Silhouette=0.2962)
6. GBT Cancellation Prediction - 83.59% accuracy, AUC-ROC 87.85% (29 features)
7. ALS Collaborative Filtering - Top-5 hotel recommendations per booking agent
8. TF-IDF Content-Based Filtering - Hotel similarity for cold-start scenarios
9. Evaluation & Summary - Metrics, cluster profiles, visualisations

Key Results :
| Model | Metric | Value |
|-------|--------|-------|
| K-Means | Silhouette Score | 0.2962 (K=4) |
| GBT Classifier | Accuracy | 83.59% |
| GBT Classifier | AUC-ROC | 87.85% |
| GBT Classifier | AUC-PR | 95.09% |
| ALS | RMSE | 1.2177 (Rank=15) |
| TF-IDF | Best Similarity | 0.2205 (Mirissa <--> Yala) |


Future Improvements:
- Deploy as Streamlit web application for real-time recommendations
- Integrate Neural Collaborative Filtering (NCF) using deep learning
- Connect live booking streams for real-time cancellation prediction
- Expand dataset with real tourism authority data
