# 📊 SubsTracker - AI-Powered Subscription Management System

## 🎯 Project Overview

**SubsTracker** is a comprehensive subscription management platform that helps users track, analyze, and optimize their recurring subscriptions. Built with Spring Boot, the application leverages AI technology to provide intelligent recommendations, spending analysis, and cost-saving alternatives for subscription services.

## 🌟 Key Features

### 📈 Subscription Management
- **Complete CRUD Operations**: Add, update, delete, and view subscriptions
- **Smart Categorization**: Digital vs Service subscription classification  
- **Flexible Billing Periods**: Monthly, 3-month, 6-month, and yearly options
- **Status Tracking**: Active and Expired subscription monitoring
- **Automated Expiration Detection**: Scheduled tasks to update subscription status

### 🤖 AI-Powered Intelligence
- **Personalized Recommendations**: AI-generated financial advice based on spending patterns
- **Alternative Service Suggestions**: AI finds cheaper alternatives for existing subscriptions
- **Spending Analysis**: Comprehensive financial insights and metrics
- **Smart Categorization**: Automatic categorization of subscription types

### 📊 Financial Analytics
- **Spending Breakdown**: Digital vs Service subscription analysis
- **Budget Analysis**: Income-to-spending ratio calculations
- **Efficiency Metrics**: Subscription cost-effectiveness scoring
- **Projection Models**: Future spending scenarios with salary changes
- **Savings Calculations**: Potential monthly and yearly savings identification

### 🔔 Intelligent Notifications
- **Expiration Alerts**: Automated email notifications (7-day and 2-day warnings)
- **HTML Email Templates**: Professional, responsive email designs
- **Customizable Notifications**: User-controlled notification preferences
- **Manual Alert Triggers**: Admin capability to send immediate alerts

### 💳 Payment Integration
- **Moyasar Payment Gateway**: Secure payment processing for premium features
- **Card Management**: Secure storage and management of payment methods
- **PDF Receipts**: Automated receipt generation and email delivery
- **Subscription Billing**: Automated payment processing for AI features

### 📄 Document Generation
- **PDF Reports**: Professional subscription summaries and receipts
- **Email Integration**: Automated document delivery via email
- **Template Engine**: Thymeleaf-powered document templates
- **Receipt Management**: Payment confirmation and transaction records

## 🏗️ System Architecture

### 🎛️ Controllers Layer
- **UserController**: User management and profile operations
- **SubscriptionController**: Core subscription CRUD and filtering
- **SpendingAnalysisController**: Financial analytics and insights
- **PaymentController**: Payment processing and card management  
- **ExpirationAlertController**: Notification system management
- **AiSubscriptionAlternativeController**: AI-powered service recommendations
- **AiAnalysisController**: AI-generated financial analysis

### ⚙️ Services Layer
- **UserService**: User profile management and preferences
- **SubscriptionService**: Business logic for subscription operations
- **SpendingAnalysisService**: Financial calculation and analysis engine
- **PaymentService**: Moyasar integration and transaction processing
- **ExpirationAlertService**: Notification scheduling and delivery
- **AiSubscriptionAlternativeService**: AI-powered alternative discovery
- **AiAnalysisService**: AI recommendation generation
- **NotificationService**: Email communication system
- **PdfService**: Document generation and formatting
- **PdfMailService**: Email delivery with attachments

## 🛠️ Technology Stack

### Backend Framework
- **Spring Boot 3.x**: Main application framework
- **Spring Data JPA**: Database operations and ORM
- **Spring AI**: Integration with AI services for recommendations
- **Spring Mail**: Email notification system
- **Spring Scheduling**: Automated task execution

### External Integrations
- **Moyasar Payment Gateway**: Secure payment processing (Saudi Arabia)
- **AI Chat Services**: Intelligent recommendation engine
- **Email Services**: SMTP integration for notifications

### Document Processing
- **Thymeleaf**: Template engine for PDF generation
- **OpenHTMLToPDF**: HTML to PDF conversion
- **Jakarta Mail**: Email composition and delivery

### Data Management
- **MySQL/PostgreSQL**: Primary database storage
- **JPA/Hibernate**: Object-relational mapping
- **Bean Validation**: Input validation and constraints

## 🚀 API Endpoints

### 👤 User Management
```
GET    /api/v1/user/get                     - Get all users
GET    /api/v1/user/get/dto                 - Get users with detailed info
GET    /api/v1/user/get/{userId}/dto        - Get specific user details
POST   /api/v1/user/add                     - Create new user
PUT    /api/v1/user/update/{id}             - Update user profile
DELETE /api/v1/user/delete/{id}             - Delete user account
PUT    /api/v1/user/{userId}/notifications/trigger - Toggle notifications
GET    /api/v1/user/get-subscribed          - Get premium users
GET    /api/v1/user/get-unsubscribed        - Get free users
GET    /api/v1/user/get/email/{email}       - Check email existence
```

### 📋 Subscription Management
```
GET    /api/v1/subscription/get                           - All subscriptions
GET    /api/v1/subscription/get/dto                       - Subscriptions with details
GET    /api/v1/subscription/get/{userId}                  - User's subscriptions
GET    /api/v1/subscription/get/{userId}/dto              - User's subscriptions (detailed)
POST   /api/v1/subscription/add/{userId}                  - Add new subscription
PUT    /api/v1/subscription/update/{userId}/{subId}       - Update subscription
DELETE /api/v1/subscription/delete/{userId}/{subId}       - Delete subscription
PUT    /api/v1/subscription/renew/{userId}/{subId}/{period} - Renew expired subscription

# Advanced Filtering
GET    /api/v1/subscription/user/{userId}/upcoming        - Upcoming renewals
GET    /api/v1/subscription/user/{userId}/day/{days}      - Due within X days
GET    /api/v1/subscription/user/{userId}/active          - Active subscriptions
GET    /api/v1/subscription/user/{userId}/expired         - Expired subscriptions
GET    /api/v1/subscription/user/{userId}/category/{cat}  - By category
GET    /api/v1/subscription/user/{userId}/billing/{period} - By billing period
GET    /api/v1/subscription/user/{userId}/price-range/{min}/{max} - By price range
GET    /api/v1/subscription/user/{userId}/most-expensive  - Highest cost subscription
GET    /api/v1/subscription/user/{userId}/cheapest        - Lowest cost subscription
```

### 📊 Financial Analysis
```
GET    /api/v1/spending_analysis/analyze/{userId}         - Basic spending analysis
GET    /api/v1/spending_analysis/analyze/{userId}dto      - Detailed analysis
GET    /api/v1/spending_analysis/get-all-spending         - All users' analysis
GET    /api/v1/spending_analysis/user/{userId}/ratio-status - Health check
GET    /api/v1/spending_analysis/user/{userId}/averages   - Cost averages
GET    /api/v1/spending_analysis/user/{userId}/projections - Future scenarios
GET    /api/v1/spending_analysis/user/{userId}/insights   - AI insights
GET    /api/v1/spending_analysis/user/{userId}/efficiency - Efficiency metrics
GET    /api/v1/spending_analysis/user/{userId}/budget-analysis - Budget recommendations
```

### 💳 Payment Processing
```
POST   /api/v1/payment/add-card/{userId}           - Add payment method
POST   /api/v1/payment/process-payment/{userId}    - Process subscription payment
PUT    /api/v1/payment/check-payment/{userId}      - Verify payment status
GET    /api/v1/payment/get-card/{userId}           - Get payment methods
```

### 🔔 Notification System
```
POST   /api/v1/expiration-alert/send/{subId}/{alertType} - Send manual alert
```

### 🤖 AI-Powered Features
```
GET    /api/v1/ai/alternative/{subscriptionId}                    - Get service alternative
GET    /api/v1/ai/get/Ai-subscription-alternative-DTO/{subId}     - Alternative details
GET    /api/v1/ai_analysis/get_ai_analysis_by_user_id/{userId}    - AI analysis
GET    /api/v1/ai_analysis/get/user/{userId}/dto                  - AI analysis (detailed)
```

## 🔧 Core Business Logic

### 💰 Spending Analysis Engine
The system automatically calculates:
- **Category Totals**: Separate totals for Digital and Service subscriptions
- **Average Costs**: Per-subscription and per-category averages  
- **Spending Ratios**: Percentage of income spent on subscriptions
- **Health Metrics**: Financial health scoring based on spending patterns
- **Efficiency Scores**: Cost-effectiveness analysis of subscription portfolio

### 🤖 AI Recommendation System
- **Financial Advice**: Personalized recommendations based on spending patterns
- **Alternative Discovery**: AI-powered search for cheaper service alternatives
- **Budget Optimization**: Intelligent suggestions for cost reduction
- **Market Analysis**: Real-time pricing comparisons and recommendations

### ⏰ Automated Scheduling
- **Expiration Monitoring**: Daily checks for upcoming subscription renewals
- **Status Updates**: Automatic status changes for expired subscriptions  
- **Email Notifications**: Scheduled alerts at 7-day and 2-day intervals
- **Payment Processing**: Automated billing for premium features

## 🏃‍♂️ Getting Started

### Prerequisites
- Java 17+
- MySQL 8.0+
- Maven 3.6+
- Moyasar API credentials
- SMTP server configuration

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/MohammedAlherz/Capstone3.git
cd Capstone3
```

2. **Configure application properties**
```properties
# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/substracker
spring.datasource.username=your_username
spring.datasource.password=your_password

# Moyasar Payment Gateway
moyasar.api.key=your_moyasar_api_key

# Email Configuration
spring.mail.host=your_smtp_host
spring.mail.username=your_email
spring.mail.password=your_email_password

# AI Service Configuration
spring.ai.chat.api-key=your_ai_api_key
```

3. **Build and run**
```bash
mvn clean install
mvn spring-boot:run
```

4. **Access the application**
- API Base URL: `http://localhost:8080/api/v1`
- Database will be auto-created on first run

## 📋 Usage Examples

### Adding a New Subscription
```json
POST /api/v1/subscription/add/1
{
  "subscriptionName": "Netflix",
  "category": "Digital",
  "price": 49.99,
  "billingPeriod": "monthly",
  "description": "Streaming service",
  "url": "netflix.com"
}
```

### Getting Financial Analysis
```json
GET /api/v1/spending_analysis/analyze/1dto
Response:
{
  "digitalSubscriptionsTotalPrice": 150.00,
  "serviceSubscriptionsTotalPrice": 200.00,
  "totalSpendingPrice": 350.00,
  "averageSubscriptionCost": 58.33,
  "spendingToIncomeRatio": 17.5,
  "totalSubscriptionsCount": 6,
  "digitalSubscriptionsCount": 3,
  "serviceSubscriptionsCount": 3
}
```

### Processing Payment
```json
POST /api/v1/payment/add-card/1
{
  "name": "John Doe",
  "number": "4111111111111111",
  "cvc": "123",
  "month": "12",
  "year": "2025",
  "amount": 100.00,
  "currency": "SAR"
}
```

## 🚀 Advanced Features

### 📈 Budget Health Monitoring
The system provides comprehensive budget analysis:
- **Health Status**: Excellent (< 20%), Good (20-30%), Caution (30-40%), High Risk (> 40%)
- **Spending Projections**: Analysis with different salary scenarios
- **Savings Potential**: Identification of cost-reduction opportunities

### 🔍 Smart Filtering
Advanced subscription filtering capabilities:
- Filter by category, billing period, price range
- Find most/least expensive subscriptions
- Track upcoming renewals and expired services
- Monitor subscriptions due within specific timeframes

### 📧 Professional Notifications
- **Responsive HTML Templates**: Professional email designs
- **Multi-stage Alerts**: 7-day warnings and 2-day urgent alerts
- **PDF Attachments**: Automated receipt generation and delivery
- **User Preferences**: Customizable notification settings

## 📊 Database Design

### ERD Diagram

![erdCapstone3](https://github.com/user-attachments/assets/ab86db06-d92c-4c64-9751-03f35e4b155e)


## 📋 Project Presentation

For a comprehensive overview of the project, including architecture, features, and implementation details, check out our presentation

## 👥 Development Team & Contributions

**Project Type**: Capstone Project - Software Engineering Program

**Key Contributions by Mohammed Alherz:**

### 🔧 **Subscription Management Endpoints (6 endpoints):**
- Subscription renewal system with flexible billing periods
- Advanced filtering system by category (Digital/Service subscriptions)
- Filter subscriptions by billing period (monthly, 3-month, 6-month, yearly)
- Price range filtering for budget-conscious users
- Most expensive subscription finder
- Cheapest subscription finder

### 📊 **Financial Analysis Endpoints (6 endpoints):**
- Spending ratio health status checker (< 30% income threshold)
- Average costs breakdown by category and billing period
- Spending projections with different salary scenarios
- Personalized spending insights and optimization recommendations
- Subscription efficiency metrics and scoring system
- Comprehensive budget analysis with threshold recommendations

### 🔔 **Alert Management Endpoints (1 endpoint):**
- Manual alert system for testing expiration notifications

### ✉️ **Email Notification System:**
- Comprehensive HTML email notification system
- Automated daily expiration checks (7-day and 2-day warnings)
- Professional responsive email templates with user personalization
- Automatic URL formatting for renewal links
- Database tracking to prevent duplicate alerts

**Total Contribution: 13+ endpoints and complete email notification system**
---

**SubsTracker** - Making subscription management intelligent and effortless! 🚀
