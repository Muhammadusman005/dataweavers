# StockPulse - Advanced Stock Market Anomaly Detection System

## 🚀 Project Overview

**StockPulse** is a comprehensive stock market anomaly detection system designed to analyze GameStop (GME) stock data and identify unusual patterns or events in stock behavior. The system combines multiple machine learning techniques with an interactive web dashboard to provide real-time insights into market dynamics and potential trading opportunities.

### 🎯 Key Highlights
- **Multi-Algorithm Detection**: 5 different ML algorithms for comprehensive analysis
- **Interactive Dashboard**: Modern web interface with real-time visualization
- **Scalable Architecture**: MongoDB integration with Flask API
- **Real-time Analysis**: Dynamic date range selection and instant results
- **Production Ready**: Complete error handling and responsive design

![Project Demo](https://github.com/user-attachments/assets/d1b5c802-1635-44d7-b92c-d341fd908c91)

## ✨ Features

### 🔍 Anomaly Detection Algorithms
- **Z-Score Method**: Statistical outlier detection based on standard deviations
- **Isolation Forest**: Tree-based unsupervised anomaly detection
- **DBSCAN Clustering**: Density-based spatial clustering for outlier identification
- **LSTM Neural Networks**: Deep learning time series prediction for temporal anomalies
- **Autoencoder**: Neural network reconstruction error-based detection

### 🎨 Interactive Dashboard
- **Real-time Visualization**: Dynamic charts with Chart.js integration
- **Responsive Design**: Mobile-friendly interface with TailwindCSS
- **Date Range Selection**: Flexible time period analysis
- **Performance Metrics**: Live statistics and anomaly counts
- **Multi-method Comparison**: Side-by-side algorithm results

### 🏗️ Technical Features
- **MongoDB Integration**: Scalable data storage and retrieval
- **Flask API**: RESTful endpoints for data processing
- **Feature Engineering**: Advanced technical indicators (Bollinger Bands, Volatility)
- **Error Handling**: Comprehensive error management and validation
- **Modular Architecture**: Clean separation of concerns

## 🚀 Quick Start

### Prerequisites
- Python 3.7+
- MongoDB 4.0+
- pip (Python package manager)

### Installation Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Hifzatoufiq/dataweavers.git
   cd DataWeavers/code/StockPulse
   ```

2. **Setup Virtual Environment**
   ```bash
   python -m venv venv
   # Windows
   venv\Scripts\activate
   # Linux/Mac
   source venv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Setup MongoDB**
   - Install MongoDB locally or use MongoDB Atlas
   - Update connection string in `Database/database connection.txt`

5. **Run the Application**
   ```bash
   python app.py
   ```

6. **Access Dashboard**
   - Open browser: `http://localhost:5000`
   - Select date range and click "Detect Anomalies"

## 📊 Usage Guide

### Web Dashboard
1. **Launch Application**
   ```bash
   python app.py
   ```

2. **Access Dashboard**
   - Open `http://localhost:5000` in your browser
   - Select start and end dates
   - Click "Detect Anomalies" to analyze

3. **Interpret Results**
   - View interactive price chart with Bollinger Bands
   - Identify anomalies marked with different colors:
     - 🔴 Red: Z-Score anomalies
     - 🟠 Orange: Isolation Forest anomalies  
     - 🟣 Purple: DBSCAN anomalies
   - Check statistics cards for anomaly counts and percentages

### Jupyter Notebook Analysis
1. **Open Detailed Analysis**
   ```bash
   jupyter notebook "Anomalies Detection.ipynb"
   ```

2. **Run Complete Analysis**
   - Execute cells sequentially for comprehensive analysis
   - View detailed visualizations and performance metrics
   - Compare algorithm effectiveness

## 📁 Project Structure

```
DataWeavers/
├── Documentation/
│   ├── StockPulse_Project_Overview.md    # Comprehensive project documentation
│   └── Architecture_Diagram.md           # System architecture diagrams
├── code/StockPulse/
│   ├── app.py                            # Flask web application
│   ├── requirements.txt                  # Python dependencies
│   ├── clean_gme_data.csv               # Processed stock data
│   ├── Anomalies Detection.ipynb        # Jupyter analysis notebook
│   ├── README.md                         # Project documentation
│   ├── static/
│   │   └── style.css                     # Custom CSS styles
│   └── templates/
│       └── index.html                    # Main dashboard template
└── Database/
    └── database connection.txt           # MongoDB connection details
```

## 🏗️ System Architecture

### High-Level Architecture
```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Data Sources  │    │   Data Pipeline │    │   ML Engine     │
│                 │    │                 │    │                 │
│ • Yahoo Finance │───▶│ • yfinance API  │───▶│ • Z-Score       │
│ • Real-time     │    │ • Data Cleaning │    │ • Isolation     │
│   Stock Data    │    │ • Feature Eng.  │    │   Forest        │
│                 │    │ • MongoDB Store │    │ • DBSCAN        │
└─────────────────┘    └─────────────────┘    │ • LSTM          │
                                              │ • Autoencoder   │
                                              └─────────────────┘
                                                       │
                                                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Web Frontend  │◀───│   Flask API     │◀───│   Results       │
│                 │    │                 │    │   Processing    │
│ • Interactive   │    │ • REST Endpoints│    │                 │
│   Dashboard     │    │ • Data Serving  │    │ • Anomaly       │
│ • Chart.js      │    │ • JSON Response │    │   Detection     │
│ • TailwindCSS   │    │ • Error Handling│    │ • Statistical   │
│                 │    │                 │    │   Analysis      │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### Technology Stack
- **Backend**: Python 3.x, Flask, Pandas, NumPy, Scikit-learn, TensorFlow
- **Database**: MongoDB with PyMongo
- **Frontend**: HTML5, JavaScript, Chart.js, TailwindCSS
- **Data Source**: Yahoo Finance API via yfinance

## 🔬 Methodology

### 1. Data Collection & Preprocessing
- **Data Source**: Yahoo Finance API for GME stock data (2000-2023)
- **Data Cleaning**: Handle missing values, outliers, and data validation
- **Feature Engineering**: 
  - Returns calculation (percentage change)
  - Volatility (20-day rolling standard deviation)
  - Moving averages (20-day MA)
  - Bollinger Bands (Upper/Lower bounds)

### 2. Anomaly Detection Algorithms
- **Z-Score Method**: Statistical outliers beyond 3 standard deviations
- **Isolation Forest**: Tree-based unsupervised anomaly detection (1% contamination)
- **DBSCAN Clustering**: Density-based spatial clustering (eps=0.5, min_samples=5)
- **LSTM Neural Network**: Deep learning time series prediction
- **Autoencoder**: Neural network reconstruction error-based detection

### 3. Performance Evaluation
- **Metrics**: Precision, Recall, F1-Score
- **Comparison**: Side-by-side algorithm performance analysis
- **Visualization**: Interactive charts with anomaly markers

### 4. Real-time Processing
- **API Endpoints**: RESTful Flask API for data processing
- **Response Time**: < 5 seconds for 3-year dataset
- **Scalability**: Handles datasets up to 10,000+ data points

## Results

The project provides insights into:
- Periods of unusual activity in GME stock
- Effectiveness of different anomaly detection techniques for stock market data
- Comparative analysis of model performances

Detailed results and visualizations are available in the Jupyter notebook and Streamlit app.

## Streamlit App Features

The Streamlit app offers an interactive interface for exploring the anomaly detection results:

- Stock data input and date range selection
- Interactive EDA visualizations
- Individual plots for each anomaly detection method
- Combined visualization of all methods' results
- Performance metrics comparison
- Summary statistics of detected anomalies

## Future Work

- Incorporate additional features (e.g., sentiment analysis, market indicators)
- Experiment with ensemble methods for improved anomaly detection
- Extend the analysis to other stocks or financial instruments
- Implement real-time anomaly detection for live stock data

## 👥 Development Team

### Core Team Members
- **Muhammad Usman** - Machine Learning & Data Science
- **Amir Khan** - Frontend Development & UI/UX
- **Youhana** - Database Architecture & Data Pipeline
- **Waris Ali** - System Integration & DevOps

*For detailed team information, roles, and contact details, please refer to the Documentation folder.*

## 🤝 Contributing

Contributions to this project are welcome! Please fork the repository and submit a pull request with your proposed changes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- yfinance library for providing easy access to Yahoo Finance data
- Streamlit for enabling interactive data visualization
- The open-source community for the various machine learning libraries used in this project

## Contact

For any queries or discussions related to this project, please open an issue in the GitHub repository.

