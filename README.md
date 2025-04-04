# 🌱 Soil-Monitoring-ETL  

## **Automating Soil Health Data Processing**  

Soil health data collected from **conservancies across Laikipia**, including **Borana, Lewa, Mugie, Suyian, and Sosian**, plays a crucial role in monitoring **regenerative agriculture, rangeland restoration, and wildlife conservation**. This data supports initiatives such as the **Ultra-High Density Community Grazing Programme**, which aims to improve soil health and ecosystem resilience through sustainable grazing practices.

By structuring and integrating this data, we can track **soil health trends, grassland species diversity, ground cover, and the ecological impacts of regenerative land management** over time, helping to provide key insights for conservation and land-use planning.

**Soil-Monitoring-ETL** is a Python-based **ETL (Extract, Transform, Load) pipeline** that automates the processing of **SoilMentor CSV files**, cleaning and loading them into a **PostgreSQL database** for structured analysis. This ensures that soil health data is stored in a standardised format, making it easier to analyse and compare across different sites and seasons.

---

## **🔹 Features**  
- ✅ **Automates CSV ingestion** – Detects new SoilMentor files in a designated folder  
- ✅ **Cleans and transforms data** – Normalises field names, converts dates, and handles missing values  
- ✅ **Loads into PostgreSQL** – Stores cleaned data in structured tables for easy analysis  
- ✅ **Supports geospatial data** – Converts GPS coordinates for use in **PostGIS**  
- ✅ **Secure and modular** – Uses **environment variables** for database credentials  

---

## **📦 Project Structure**  
```
soil-monitoring-etl/
│── data_exports/
│   └── soilmentor/              # Folder where CSVs are uploaded
│── etl/
│   ├── etl_soilmentor.py        # Main ETL script
│   ├── db_utils.py              # Database connection functions
│   └── validation.py            # Optional: add data checks here
│── config/
│   └── .env.example             # Example credentials (no real values)
│── sample_data/
│   └── soilmentor_sample.csv    # Example CSV for testing
│── requirements.txt
│── README.md
│── LICENSE
│── .gitignore
```

---

## **📥 Installation & Setup**  

### **1️⃣ Install PostgreSQL (Manual or Docker)**  

#### **Option 1: Install Locally**  
- [Download PostgreSQL](https://www.postgresql.org/download/) and install it on your system.

#### **Option 2: Run via Docker (Recommended)**  
If you prefer an isolated environment, use **Docker**:  
```bash
docker run --name soil_db -e POSTGRES_USER=youruser -e POSTGRES_PASSWORD=yourpassword -e POSTGRES_DB=soil_db -p 5432:5432 -d postgres
```

---

### **2️⃣ Clone the Repository**  
```bash
git clone https://github.com/your-repo-name/soil-monitoring-etl.git
cd soil-monitoring-etl
```

---

### **3️⃣ Set Up Environment Variables**  
Create a `.env` file in the project root and add your **PostgreSQL credentials**:  
```ini
DB_HOST=localhost
DB_NAME=soil_db
DB_USER=youruser
DB_PASSWORD=yourpassword
DB_PORT=5432
```

---

### **4️⃣ Place CSV Files in the Correct Folder**  
All SoilMentor CSV files should be saved in:  
```
data_exports/soilmentor/
```
The script will automatically detect new files in this directory.

---

### **🚀 How to Run the ETL Pipeline**  
Run the script to process SoilMentor data and load it into PostgreSQL:  
```bash
python etl/etl_soilmentor.py
```

---

## **🔒 Security & Best Practices**  
- Do not commit sensitive credentials. Always use `.env` files.  
- Validate CSV data before processing to prevent errors.  
- Set up logging to monitor ETL processes.  
- For cloud ingestion: consider using **Google Drive or OneDrive upload-only folders** and **automated ETL via service accounts** for security.  

---

## **🤝 Contributing**  
We welcome contributions! To get started:  
1. **Fork the repository** on GitHub  
2. **Create a new branch**  
   ```bash
   git checkout -b feature-branch
   ```
3. **Commit your changes**  
   ```bash
   git commit -m "Add new feature"
   ```
4. **Push to your fork and create a pull request**

### ✅ Ideal First Contributions  
- Add unit tests for `etl_soilmentor.py`  
- Add support for other soil indicators  
- Build cloud integration for fetching CSVs from Google Drive or OneDrive  
- Improve logging and error handling  

---

## **📜 License**  
This project is open-source and available under the **MIT License**.  

---

## **📩 Contact**  
For questions or contributions, reach out via:  
📧 **ciarahubble@hotmail.co.uk** / **ciara@borana.co.ke**
