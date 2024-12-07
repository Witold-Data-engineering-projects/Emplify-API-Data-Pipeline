
# **Emplifi Social Media Metrics Extraction**

This project demonstrates an end-to-end data pipeline for fetching, transforming, and aggregating social media metrics using the **Emplifi API**. The extracted data includes both profile-level and post-level metrics, making it a valuable resource for understanding social media performance across platforms.

## **Project Overview**
The purpose of this project is to showcase a practical implementation of a data engineering pipeline. It includes:
- Fetching data from multiple social media platforms (e.g., Facebook, Instagram, Twitter, YouTube, TikTok).
- Transforming raw API responses into structured tabular formats.
- Aggregating key metrics at both **profile** and **post** levels.
- Using secure practices for authentication and data encryption.

## **Features**
- **API Integration:** Uses the Emplifi API to pull social media metrics.
- **Dynamic Configuration:** Credentials, SSL certificates, and other configurations are fetched from a `.env` file for local development and are planned to be migrated to Azure Key Vault for deployment.
- **Custom Transformation Logic:** Converts nested JSON API responses into clean DataFrames using `pandas`.
- **Multi-Level Data Insights:** Supports metrics aggregation at both profile and post levels.
- **Secure Practices:** Employs SSL certificates and environment variables for safe API access.

---

## **Technologies Used**
- **Python**: Core programming language.
- **pandas**: Data manipulation and transformation.
- **requests**: For API interaction.
- **dotenv**: To manage environment variables securely.
- **JSON**: For handling API responses.
- **Azure Key Vault (planned)**: Secure storage of sensitive information in production.

---

## **Setup Instructions**

### **Prerequisites**
1. Install Python 3.8+.

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file in the root directory with the following variables:
   ```env
   emplify_token=<Your Emplifi API Token>
   emplify_secret=<Your Emplifi API Secret>
   SSL_cert_loc=<Path to your SSL certificate>
   ```

---

## **Project Details**

### **1. API Integration**
- The project interacts with the Emplifi API to fetch metrics.
- Supported platforms: Facebook, Instagram, Twitter, YouTube, TikTok.

### **2. Profile-Level Metrics**
- Fetches and aggregates key metrics:
  - `insights_impressions`
  - `insights_video_views`
  - `insights_engagements`
  - `likes`
  - `number_of_comments`
- Aggregated metrics are stored in a `prof_lev_met_agg` DataFrame.

### **3. Post-Level Metrics**
- Retrieves and transforms data for specific post labels.
- Aggregates metrics by post and time for detailed insights.

### **4. Secure Authentication**
- Authentication credentials and SSL certificates are fetched from the `.env` file for local testing.
- Planned migration to **Azure Key Vault** for production deployment.

---

## **Future Developments**
1. **Azure Integration**:
   - Migrate credentials and sensitive information from `.env` to **Azure Key Vault** for enhanced security.
   - Deploy the pipeline on **Azure Data Factory** for automation.
2. **Database Integration**:
   - Store the transformed data in a relational database (e.g., Azure SQL, PostgreSQL) for further analysis.
3. **Data Visualization**:
   - Develop interactive dashboards in **Power BI** to visualize the fetched metrics.
4. **Error Handling and Logging**:
   - Add robust error handling and logging mechanisms using **logging** or **Azure Monitor**.


---

## **Example Outputs**
### **Profile-Level Metrics (Sample)**
| Profile        | Date       | Metric               | Value     |
|----------------|------------|----------------------|-----------|
| Triumph_Facebook | 2024-07-03 | insights_engagements | 2345      |
| Triumph_Instagram | 2024-07-03 | likes                | 1200      |

### **Post-Level Metrics (Sample)**
| Date       | Post Label      | Metric               | Value     |
|------------|-----------------|----------------------|-----------|
| 2024-07-03 | #Adventure      | insights_impressions | 5000      |
| 2024-07-03 | #Motorcycles    | number_of_comments   | 50        |


---

## **Contact**
If you have any questions or feedback, feel free to reach out via GitHub or email me at [witold.piecz@gmail.com].

---
