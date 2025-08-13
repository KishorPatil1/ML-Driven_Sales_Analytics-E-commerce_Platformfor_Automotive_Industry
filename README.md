# ML-Driven Sales Analytics Platform

<p align="center">
  <img src="System Architecture-2.png" alt="System Architecture" width="600"/>
</p>

A sophisticated full-stack e-commerce platform integrated with advanced machine learning capabilities for sales forecasting, demand analysis, and customer sentiment analysis. This project combines traditional retail operations with cutting-edge AI to provide actionable business insights.

## 🌟 Features

### 🛒 E-commerce Platform
- **User Authentication**: Secure JWT-based authentication with role-based access control
- **Product Management**: Complete CRUD operations for product catalog
- **Shopping Cart & Checkout**: Full shopping experience with Stripe payment integration
- **Order Management**: Comprehensive order tracking and management system
- **Review System**: Customer feedback with rating system

### 🤖 AI-Powered Analytics
- **Sales Forecasting**: Advanced ML models for short-term (45 days) and long-term (2 years) predictions
- **Demand Analysis**: Statistical analysis with moving averages and trend identification
- **Stockout Prediction**: Intelligent inventory management with risk assessment
- **Sentiment Analysis**: Real-time customer feedback analysis with improvement suggestions

### 📊 Interactive Dashboards
- **Sales Analytics**: Interactive charts with historical vs predicted data
- **Review Analytics**: Sentiment distribution and problem categorization
- **Admin Dashboard**: Comprehensive business metrics and management tools
- **Real-time Visualizations**: Dynamic charts with Recharts library

## 🏗️ Architecture

### Frontend (React)
- **Framework**: React 18 with Material-UI and Tailwind CSS
- **State Management**: Context API for authentication and global state
- **Routing**: React Router for SPA navigation
- **Charts**: Recharts for interactive data visualizations

### Backend (Hybrid Architecture)
- **Node.js Server** (Port 5000): E-commerce operations with Express.js
- **Python Flask Server** (Port 5001): ML/AI services and data processing
- **Dual Database**: MySQL for transactional data, MongoDB for user management

### AI/ML Stack
- **TensorFlow/Keras**: Deep learning models for long-term forecasting
- **Scikit-learn**: Traditional ML algorithms (Gradient Boosting)
- **Natural Language Processing**: Pre-trained sentiment analysis models
- **Google Gemini API**: AI-powered improvement suggestions

## 🚀 Quick Start

### Prerequisites
- Node.js (v16 or higher)
- Python (v3.8 or higher)
- MySQL Server
- MongoDB

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/ML-driven-sales-Analytics.git
   cd ML-driven-sales-Analytics
   ```

2. **Install dependencies**
   ```bash
   # Root dependencies
   npm install

   # Frontend dependencies
   cd frontend
   npm install

   # Backend dependencies
   cd ../backend
   npm install

   # Python dependencies
   pip install -r requirements.txt
   ```

3. **Environment Setup**
   
   Create `.env` files in the backend directory:
   ```env
   # Database Configuration
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=your_mysql_password
   DB_NAME=feedback_system

   # MongoDB
   MONGODB_URI=your_mongodb_connection_string

   # API Keys
   GEMINI_API_KEY=your_gemini_api_key
   STRIPE_SECRET_KEY=your_stripe_secret_key
   CLOUDINARY_CLOUD_NAME=your_cloudinary_name
   CLOUDINARY_API_KEY=your_cloudinary_key
   CLOUDINARY_API_SECRET=your_cloudinary_secret

   # JWT
   JWT_SECRET=your_jwt_secret
   ```

4. **Database Setup**
   ```bash
   # Initialize MySQL database
   mysql -u root -p < backend/config/init_users.sql

   # Initialize MongoDB users
   cd backend
   npm run init-db
   ```

5. **Start the application**
   
   **Terminal 1 - Frontend:**
   ```bash
   cd frontend
   npm start
   ```

   **Terminal 2 - Node.js Backend:**
   ```bash
   cd backend
   npm start
   ```

   **Terminal 3 - Python ML Server:**
   ```bash
   cd backend
   python app.py
   ```

The application will be available at:
- Frontend: http://localhost:3000
- Node.js API: http://localhost:5000
- Python ML API: http://localhost:5001

## 📖 Usage

### For Customers
1. **Register/Login** to access the platform
2. **Browse Products** in the catalog
3. **Add to Cart** and proceed to checkout
4. **Leave Reviews** after purchase
5. **View Order History** in your profile

### For Administrators
1. **Login** with admin credentials
2. **Manage Products**: Add, edit, or remove products
3. **View Analytics**: Access sales forecasting and sentiment analysis
4. **Upload Data**: Import CSV files for custom analysis
5. **Monitor Orders**: Track and manage customer orders

### Sales Analytics Workflow
1. **Data Upload**: Upload sales data via CSV or use existing data
2. **Select Analysis Type**:
   - **Sales Prediction**: Get future sales forecasts
   - **Demand Analysis**: Understand demand patterns
   - **Stockout Prediction**: Optimize inventory management
3. **Interpret Results**: View interactive charts and recommendations
4. **Export Data**: Download analysis results

## 🔧 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login

### Products
- `GET /api/products` - Get all products
- `POST /api/products` - Create product (Admin)
- `PUT /api/products/:id` - Update product (Admin)
- `DELETE /api/products/:id` - Delete product (Admin)

### Analytics (Python Flask)
- `POST /api/sales/forecast` - Sales forecasting
- `POST /api/sales/demand-analysis` - Demand analysis
- `POST /api/sales/stockout-prediction` - Stockout prediction
- `POST /analyze-product-reviews/:id` - Sentiment analysis

## 📊 Data Format

### Sales Data CSV Structure
```csv
id,product_id,product_name,Date,Model,Brand,Vehicle_Type,Fuel_Type,City,Dealer_Type,Customer_Age_Group,Customer_Gender,Occupation_of_Buyer,Payment_Mode,Festive_Season_Purchase,Advertisement_Type,Service_Availability,Weather_Condition,Road_Conditions,Engine_Capacity_CC,Price_INR,Petrol_Price_at_Purchase,Competitor_Brand_Presence,Discounts_Offers,Stock_on_Date,Quantity_Sold
```

### Sample Data
The project includes Royal Enfield Classic 350 sales data (2024) with 367 records covering:
- **Geographic Coverage**: Major Indian cities
- **Price Range**: ₹180,000 - ₹209,000
- **Customer Demographics**: Various age groups and occupations
- **Market Conditions**: Weather, competition, pricing factors

## 🤖 Machine Learning Models

### Sales Forecasting
- **Short-term (≤45 days)**: Gradient Boosting Regressor
- **Long-term (>45 days)**: LSTM Neural Networks
- **Features**: Time-based, seasonal, lag features, moving averages
- **Accuracy Metrics**: R² Score, Mean Absolute Error

### Sentiment Analysis
- **Model**: Pre-trained TensorFlow model with TF-IDF vectorization
- **Classes**: Positive, Neutral, Negative
- **Enhancement**: Google Gemini API for improvement suggestions

## 🔒 Security Features

- **JWT Authentication**: Secure token-based authentication
- **Rate Limiting**: API request throttling
- **Input Validation**: Comprehensive data validation
- **Environment Variables**: Secure configuration management
- **Role-based Access**: Admin and customer role separation

## 🎨 UI/UX Features

- **Responsive Design**: Mobile-first approach
- **Dark Theme**: Modern dark interface
- **Interactive Charts**: Hover effects and tooltips
- **Loading States**: Progressive loading indicators
- **Error Handling**: User-friendly error messages
- **Real-time Updates**: Live data synchronization

## 📈 Performance Optimizations

- **Database Connection Pooling**: Optimized database connections
- **Lazy Loading**: Component-based code splitting
- **Caching**: Strategic data caching
- **Compression**: Image and asset optimization
- **Parallel Processing**: Concurrent API calls

## 🧪 Testing

```bash
# Frontend tests
cd frontend
npm test

# Backend tests
cd backend
npm test

# Python tests
python -m pytest
```

## 📦 Deployment

### Docker Deployment
```bash
# Build and run with Docker Compose
docker-compose up --build
```

### Manual Deployment
1. **Frontend**: Build and deploy to static hosting (Netlify, Vercel)
2. **Backend**: Deploy to cloud platforms (Heroku, AWS, DigitalOcean)
3. **Database**: Set up managed database services
4. **Environment**: Configure production environment variables

## 📋 Roadmap

- [ ] **Real-time Notifications**: WebSocket integration for live updates
- [ ] **Advanced ML Models**: Integration of more sophisticated forecasting models
- [ ] **Multi-language Support**: Internationalization
- [ ] **Mobile App**: React Native mobile application
- [ ] **API Documentation**: Comprehensive Swagger documentation
- [ ] **Performance Dashboard**: Real-time system metrics
- [ ] **A/B Testing**: Built-in experimentation framework

## 🐛 Known Issues

- CSV upload requires specific column format
- Large datasets may require pagination
- Real-time updates need WebSocket enhancement

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.






