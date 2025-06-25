# 🛍️ Mall Customer Segmentation with K-Means Clustering

## Unlocking Customer Insights for Targeted Marketing Strategies

-----

## ✨ Project Overview

This project demonstrates **Customer Segmentation** for a mall's customer base using the **K-Means Clustering algorithm**. By analyzing customer data, specifically their `Annual Income` and `Spending Score`, we identify distinct groups (segments) of customers. This segmentation provides invaluable insights for businesses to tailor marketing strategies, personalize customer experiences, and optimize resource allocation.

The project encompasses data loading, preprocessing, determining the optimal number of clusters using the Elbow Method, applying K-Means clustering, visualizing the segments, and demonstrating how to predict the segment of a new customer.

-----

## 💡 Why Customer Segmentation?

In today's competitive retail landscape, a "one-size-fits-all" approach rarely works. Customer segmentation allows businesses to:

  * **Understand Customer Behavior**: Gain deeper insights into different customer groups' preferences and habits.
  * **Targeted Marketing**: Create highly specific marketing campaigns that resonate with each segment, leading to higher conversion rates.
  * **Personalized Experience**: Offer tailored product recommendations, promotions, and services.
  * **Optimize Resource Allocation**: Focus resources on the most valuable or promising customer segments.
  * **Improve Customer Retention**: Address specific needs and concerns of different groups to foster loyalty.

-----

## 🧠 How It Works

1.  **Data Loading**: The `Mall_Customers.csv` dataset, containing customer demographics and spending habits, is loaded.
2.  **Feature Selection**: `Annual Income (k$)` and `Spending Score (1-100)` are chosen as the key features for segmentation.
3.  **Data Scaling**: Features are scaled using `StandardScaler` to ensure that all features contribute equally to the distance calculations in K-Means, preventing features with larger values from dominating.
4.  **Elbow Method**: The **Elbow Method** is used to determine the optimal number of clusters (`k`). This involves plotting the Within-Cluster Sum of Squares (WCSS) against the number of clusters and identifying the "elbow" point, where the rate of decrease in WCSS significantly slows down.
5.  **K-Means Clustering**: The K-Means algorithm is applied with the optimal `k` value to group customers into distinct clusters based on their similarity in income and spending score.
6.  **Cluster Visualization**: The segmented customers are visualized on a scatter plot, with different colors representing different clusters and centroids marked for clarity.
7.  **Model Persistence**: The trained K-Means model and the scaler are saved using `joblib` for future use, allowing for easy prediction of new customer segments without re-training.

-----

## 📊 Dataset

The dataset `Mall_Customers.csv` typically contains the following columns:

  * `CustomerID`: Unique identifier for each customer.
  * `Gender`: Male or Female.
  * `Age`: Age of the customer.
  * `Annual Income (k$)`: Annual income of the customer in thousands of USD.
  * `Spending Score (1-100)`: A score assigned by the mall based on customer behavior and spending nature, ranging from 1 to 100.

For this project, `Annual Income (k$)` and `Spending Score (1-100)` are the primary features used for clustering.

-----

## 🛠️ Technologies & Libraries

  * `Python 3.x`
  * `Pandas` - Data manipulation and analysis.
  * `NumPy` - Numerical operations.
  * `Scikit-learn` - K-Means clustering and data preprocessing (`StandardScaler`).
  * `Matplotlib` - Plotting visualizations.
  * `Seaborn` - Enhanced statistical data visualization.
  * `joblib` - Saving and loading models.

-----

## 🚀 Getting Started

Follow these steps to set up the project locally and run the customer segmentation analysis:

### Prerequisites

  * Python 3.9+
  * Pip (Python package installer)

### Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/mall-customer-segmentation.git
    cd mall-customer-segmentation
    ```

    (Replace `your-username` with your actual GitHub username)

2.  **Download the dataset:**
    Make sure you have the `Mall_Customers.csv` file in the root directory of your project. You can typically find this dataset on Kaggle or other public data repositories.

3.  **Create a virtual environment (recommended):**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: `venv\Scripts\activate`
    ```

4.  **Install the required libraries:**

    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn joblib
    ```

### Running the Analysis

To run the K-Means clustering analysis, visualize the segments, and demonstrate predictions, execute the main script:

```bash
python your_main_script_name.py
```

(Replace `your_main_script_name.py` with the actual name of your Python file containing the analysis code. If you are using a Jupyter Notebook, simply open and run the cells.)

This will:

  * Load the data.
  * Perform scaling.
  * Generate the Elbow Method plot.
  * Perform K-Means clustering with the optimal `k=5` clusters.
  * Display the customer segmentation scatter plot.
  * Save the `kmeans_mall_model.pkl` and `scaler_mall.pkl` files.
  * Demonstrate a prediction for a new customer.

-----

## 📈 Results & Visualizations

### Elbow Method to Determine Optimal K

The Elbow Method plot helps in identifying the ideal number of clusters. The "elbow" in the curve indicates a point after which adding more clusters does not significantly reduce the WCSS, suggesting the optimal `k`. In this analysis, `k=5` was chosen.

*(Note: You'll need to generate this plot and save it as `elbow_method.png` in an `images` folder, or update the path.)*

### Customer Segments Visualization

The scatter plot clearly illustrates the 5 distinct customer segments based on their annual income and spending score. Each color represents a unique cluster, and the 'X' markers denote the cluster centroids.

*(Note: You'll need to generate this plot and save it as `customer_segments.png` in an `images` folder, or update the path.)*

#### Interpreting the Clusters (Example):

  * **Cluster 0 (e.g., Low Income, High Spending)**: Likely young adults, students, or those who prioritize experiences.
  * **Cluster 1 (e.g., High Income, Low Spending)**: Potential savers, older demographic, or those who shop elsewhere for high-value items.
  * **Cluster 2 (e.g., Average Income, Average Spending)**: The general customer base.
  * **Cluster 3 (e.g., Low Income, Low Spending)**: Budget-conscious shoppers.
  * **Cluster 4 (e.g., High Income, High Spending)**: **Target VIPs\!** These are valuable customers who spend a lot.

This segmentation allows the mall to create tailored marketing campaigns for each group, such as loyalty programs for high spenders or budget deals for low-income segments.

-----

## 📂 Project Structure

```
.
├── Mall_Customers.csv                       # The dataset
├── customer_segmentation_analysis.ipynb     # Main Jupyter/Colab Notebook (or customer_segmentation_analysis.py)
├── kmeans_mall_model.pkl                    # Saved K-Means model
├── scaler_mall.pkl                          # Saved StandardScaler object
├── README.md                                # This file
```

*(Note: `kmeans_mall_model.pkl`, `scaler_mall.pkl`, and the plot images will be generated after running the analysis code.)*

-----

## 🤝 Contributing

Contributions are most welcome\! If you have suggestions for improvements, new features (e.g., different clustering algorithms, more features), or bug fixes, please open an issue or submit a pull request.

1.  Fork the repository.
2.  Create your feature branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.

-----

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](https://www.google.com/search?q=LICENSE) file for details.

-----

## 🧑‍💻 Author

**Deva** (AI Assistant created by Moksh Bhardwaj)

  * **Moksh Bhardwaj** - B.Tech AIML Student | DPG ITM College
  * **Location**: Basai Enclave Part 3, Gurugram, Haryana, India

-----
