# LD-App - Laundry Service Management System

A comprehensive laundry service management platform that connects customers with laundry service providers. The system consists of a Spring Boot backend API and a React-based frontend application for laundry owners.

## 🏗️ Architecture

This project follows a modern microservices architecture with:

- **Backend**: Spring Boot REST API (Java 17)
- **Frontend**: React TypeScript application with Material-UI
- **Database**: PostgreSQL with JPA/Hibernate
- **Authentication**: JWT-based security
- **Real-time Features**: Firebase Cloud Messaging (FCM)
- **File Storage**: Supabase Storage
- **Payment Processing**: Stripe integration
- **SMS Notifications**: Twilio integration

## 🚀 Features

### For Laundry Owners
- **Dashboard**: Real-time overview of business metrics
- **Order Management**: Complete order lifecycle management
- **Customer Management**: Customer profiles and communication
- **Service Management**: Add, edit, and manage laundry services
- **Analytics**: Comprehensive business analytics and insights
- **Chat System**: Real-time communication with customers
- **Notifications**: Push notifications and SMS alerts
- **Settings**: Business profile and preferences management

### For Customers
- **Order Placement**: Easy order creation with service selection
- **Real-time Tracking**: Order status updates and notifications
- **Chat Support**: Direct communication with laundry providers
- **Payment Processing**: Secure online payments
- **Address Management**: Multiple delivery addresses
- **Reviews & Ratings**: Service feedback system

## 📁 Project Structure

```
ld-app/
├── src/                          # Backend Spring Boot application
│   ├── main/java/com/rr/ldapp/
│   │   ├── config/              # Configuration classes
│   │   ├── controller/          # REST API controllers
│   │   ├── model/              # Entity models and DTOs
│   │   ├── repository/         # Data access layer
│   │   ├── service/            # Business logic layer
│   │   └── exception/          # Exception handling
│   └── resources/              # Configuration files
├── laundry-owner-app/          # Frontend React application
│   ├── src/
│   │   ├── components/         # React components
│   │   ├── context/           # React context providers
│   │   └── services/          # API service layer
│   └── public/                # Static assets
├── docs/                      # Project documentation
└── uploads/                   # File uploads directory
```

## 🛠️ Technology Stack

### Backend
- **Framework**: Spring Boot 3.4.2
- **Language**: Java 17
- **Database**: PostgreSQL
- **ORM**: Spring Data JPA / Hibernate
- **Security**: Spring Security with JWT
- **Build Tool**: Maven
- **Testing**: JUnit 5, Spring Boot Test

### Frontend
- **Framework**: React 18.2.0
- **Language**: TypeScript 4.9.5
- **UI Library**: Material-UI (MUI) 5.15.0
- **Charts**: Recharts 3.1.2
- **Routing**: React Router DOM 7.7.1
- **HTTP Client**: Axios 1.11.0
- **Build Tool**: Create React App

### External Services
- **Firebase**: Cloud Messaging (FCM)
- **Supabase**: File storage
- **Stripe**: Payment processing
- **Twilio**: SMS notifications

## 🚀 Getting Started

### Prerequisites
- Java 17 or higher
- Node.js 16 or higher
- PostgreSQL 12 or higher
- Maven 3.6 or higher

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd ld-app
   ```

2. **Configure database**
   - Create a PostgreSQL database
   - Update `src/main/resources/application.properties` with your database credentials

3. **Configure external services**
   - Set up Firebase project and add service account key
   - Configure Supabase storage credentials
   - Add Stripe API keys
   - Configure Twilio credentials

4. **Run the application**
   ```bash
   mvn spring-boot:run
   ```

   The backend will start on `http://localhost:8080`

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd laundry-owner-app
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure API endpoint**
   - Update the API base URL in `src/services/api.ts`

4. **Start the development server**
   ```bash
   npm start
   ```

   The frontend will start on `http://localhost:3000`

## 📚 API Documentation

### Core Endpoints

#### Authentication
- `POST /auth/register` - User registration
- `POST /auth/login` - User login
- `POST /auth/logout` - User logout

#### Orders
- `POST /orders/place` - Place new order
- `GET /orders/{id}` - Get order details
- `PUT /orders/{id}/update-status` - Update order status
- `GET /orders/laundry/{laundryId}` - Get laundry orders

#### Services
- `GET /laundry-services` - Get available services
- `POST /laundry-services` - Create new service
- `PUT /laundry-services/{id}` - Update service
- `DELETE /laundry-services/{id}` - Delete service

#### Chat
- `GET /chat/users/{userId}/conversations` - Get conversations
- `POST /chat/conversations/{id}/messages` - Send message
- `GET /chat/conversations/{id}/messages` - Get messages

#### Analytics
- `GET /analytics/{laundryId}` - Get business analytics
- `GET /analytics/{laundryId}/revenue` - Get revenue analytics
- `GET /analytics/{laundryId}/orders` - Get order analytics

### Complete API Documentation
See the Postman collections in the root directory:
- `Laundry_App_API.postman_collection.json`
- `Laundry_Rating_Review_API.postman_collection.json`
- `All_Laundry_Service_API.postman_collection.json`

## 🔧 Configuration

### Environment Variables

#### Backend
```properties
# Database
spring.datasource.url=jdbc:postgresql://localhost:5432/ldapp
spring.datasource.username=your_username
spring.datasource.password=your_password

# JWT
jwt.secret=your_jwt_secret
jwt.expiration=86400000

# Firebase
firebase.service-account.path=path/to/service-account.json

# Supabase
supabase.url=your_supabase_url
supabase.key=your_supabase_key

# Stripe
stripe.secret-key=your_stripe_secret_key
stripe.publishable-key=your_stripe_publishable_key

# Twilio
twilio.account-sid=your_twilio_account_sid
twilio.auth-token=your_twilio_auth_token
twilio.phone-number=your_twilio_phone_number
```

#### Frontend
```typescript
// src/services/api.ts
const API_BASE_URL = 'http://localhost:8080/api';
```

## 🧪 Testing

### Backend Testing
```bash
# Run all tests
mvn test

# Run specific test class
mvn test -Dtest=UserServiceTest

# Run with coverage
mvn jacoco:report
```

### Frontend Testing
```bash
cd laundry-owner-app

# Run tests
npm test

# Run tests with coverage
npm test -- --coverage
```

## 📊 Key Features in Detail

### 1. Order Management System
- Complete order lifecycle from placement to delivery
- Real-time status updates with notifications
- Order history and analytics
- Bulk order operations

### 2. Real-time Chat System
- Customer-laundry owner communication
- Message history and search
- Read receipts and typing indicators
- Push notifications for new messages

### 3. Analytics Dashboard
- Revenue tracking and forecasting
- Order statistics and trends
- Customer behavior analysis
- Service performance metrics

### 4. Notification System
- Push notifications via FCM
- SMS notifications via Twilio
- Email notifications
- Customizable notification preferences

### 5. Payment Processing
- Secure payment processing with Stripe
- Multiple payment methods
- Payment history and receipts
- Refund processing

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For support and questions:
- Create an issue in the GitHub repository
- Check the documentation in the `docs/` directory
- Review the implementation guides in the root directory

## 🔄 Version History

- **v0.1.0** - Initial release with core features
- **v0.2.0** - Added chat system and analytics
- **v0.3.0** - Enhanced notification system and payment processing

## 📞 Contact

- **Project Link**: [https://github.com/your-username/ld-app](https://github.com/your-username/ld-app)
- **Issues**: [https://github.com/your-username/ld-app/issues](https://github.com/your-username/ld-app/issues)
