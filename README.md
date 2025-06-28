# Crime Rate Prediction Using K-means Clustering

A Django-based web application that analyzes crime data and provides predictions using machine learning algorithms. The system combines K-means clustering with Random Forest regression to classify areas based on crime rates and predict future crime occurrences.

## 🚀 Features

### Data Processing & Analysis
- **Dataset Support**: Processes crime data with columns: States/UTs, District, Murder, Rape, Theft, Dowry_Deaths, Year
- **Data Preprocessing**: Label Encoding for categorical data and MinMax Scaling for normalization
- **Missing Data Handling**: Automatically fills null values with 0

### Machine Learning Models

#### K-means Clustering
- Classifies areas into "High Crime Rate" or "Low Crime Rate" zones
- Uses 2 clusters with 1200 iterations
- Analyzes all crime types plus location and year data

#### Random Forest Regression
- Predicts future crime counts for specific crime types
- Separate models for Theft, Murder, and Rape prediction
- Uses States/UTs, District, and Year as features

### Web Application Functions
- **Admin Panel**: Simple authentication with dataset management
- **Dataset Upload**: CSV file processing with tabular data display
- **Cluster Prediction**: Area classification as high or low crime rate
- **Future Prediction**: Crime count forecasting for 2022-2023
- **Analysis Dashboard**: Pre-generated graphs (bar charts and pie charts)

## 🛠️ Technical Stack

- **Framework**: Django 2.1.7
- **Database**: SQLite3
- **Machine Learning**: scikit-learn, pandas, numpy, matplotlib
- **Frontend**: HTML templates

## 📋 Prerequisites

```bash
Python 3.6+
Django 2.1.7
scikit-learn
pandas
numpy
matplotlib
```

## 🔧 Installation

1. **Clone the repository**
```bash
git clone [repository-url]
cd crime-rate-prediction
```

2. **Install required packages**
```bash
pip install django==2.1.7
pip install scikit-learn pandas numpy matplotlib
```

3. **Run migrations**
```bash
python manage.py migrate
```

4. **Start the development server**
```bash
python manage.py runserver
```

5. **Access the application**
- Open your browser and go to `http://127.0.0.1:8000/`
- Admin login: username `admin`, password `admin`

## 📊 Data Format

Your CSV file should contain the following columns:
- **States/UTs**: State or Union Territory name
- **District**: District name
- **Murder**: Number of murder cases
- **Rape**: Number of rape cases
- **Theft**: Number of theft cases
- **Dowry_Deaths**: Number of dowry death cases
- **Year**: Year of the data

Example:
```csv
States/UTs,District,Murder,Rape,Theft,Dowry_Deaths,Year
Maharashtra,Mumbai,45,23,156,2,2021
Delhi,New Delhi,32,18,89,1,2021
```

## 🔄 Machine Learning Workflow

### Data Preprocessing Pipeline
```
Raw Data → Fill NaN with 0 → Label Encoding → MinMax Scaling → ML Models
```

### Clustering Process
1. Load dataset with all crime features
2. Apply label encoding to categorical variables
3. Scale all features to 0-1 range
4. Train K-means with 2 clusters
5. Classify new inputs as cluster 0 (Low) or 1 (High)

### Prediction Process
1. Load dataset with location and year as features
2. Extract target variables (Theft, Murder, Rape) separately
3. Train individual Random Forest models for each crime type
4. Use trained models to predict future crime counts

## 📁 Project Structure

```
crime-rate-prediction/
├── views.py              # Main logic and ML implementations
├── urls.py               # URL routing
├── settings.py           # Django configuration
├── templates/            # HTML templates
├── static/              # CSS, JS, images
└── README.md            # This file
```

## 💡 Usage

1. **Upload Dataset**: Go to admin panel and upload your crime data CSV
2. **View Analysis**: Explore pre-generated charts and statistics
3. **Cluster Prediction**: Input area details to get crime rate classification
4. **Future Prediction**: Get crime count predictions for upcoming years

## 🔍 Key Technical Concepts

### K-means Clustering
- Unsupervised learning algorithm grouping similar data points
- Groups areas with similar crime patterns
- Uses Euclidean distance for similarity measurement

### Random Forest Regression
- Ensemble method using multiple decision trees
- Reduces overfitting compared to single decision tree
- Provides feature importance insights

### Label Encoding
- Converts categorical data to numerical format
- Essential for ML algorithms requiring numerical input

### MinMax Scaling
- Normalizes features to 0-1 range
- Prevents features with larger scales from dominating

## 🎯 Real-world Applications

- **Law Enforcement**: Resource allocation based on crime predictions
- **Urban Planning**: Identifying areas needing security infrastructure
- **Policy Making**: Data-driven crime prevention strategies
- **Insurance**: Risk assessment for geographical areas

## ⚠️ Current Limitations

1. **No Model Validation**: Missing train/test split evaluation
2. **Hardcoded Values**: Fixed cluster numbers and parameters
3. **Limited Error Handling**: Minimal edge case management
4. **Basic Security**: Simple authentication, exposed secret key
5. **Simple Data Processing**: Basic NaN filling approach

## 🔮 Potential Improvements

- [ ] Add model evaluation metrics (R², MAE, etc.)
- [ ] Implement cross-validation
- [ ] Enhance data visualization capabilities
- [ ] Improve error handling and input validation
- [ ] Implement proper security measures
- [ ] Add feature selection/engineering techniques
- [ ] Handle unseen categorical values gracefully

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- Your Name - Initial work

## 🙏 Acknowledgments

- Thanks to the open-source community for the amazing libraries
- Crime data sources and research papers that inspired this project
