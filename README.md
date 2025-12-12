# dbms_fooddeliveryapp
# Install required packages
pip install streamlit mysql-connector-python pandas

#run this to create the databse with all tables,triggers ,procedures, functions
python createfoodappdatabase.py

#make sure to update the databse configurations with correct password and database name

#run the streamlit app for final gui
streamlit run dbmstest1.py

food-delivery-app/
├── dbmstest1.py              # Main Streamlit application
├── createfoodappdatabase.py   # Database setup 
└── README.md                 # This file

# 🍔 FoodDelight - Multi-Panel Food Delivery System

## 🎯 Application Architecture

The application features **three distinct user panels** with specialized interfaces and functionalities:

### 👤 **Customer Panel** - Ordering & Shopping Experience
- **🏠 Restaurant Browser**: Browse all restaurants with ratings and locations
- **🍽️ Menu Interface**: View available menu items with real-time stock levels
- **🛒 Smart Cart**: Add/remove items with quantity validation
- **💳 Checkout System**: Multiple payment methods (COD, UPI, Card)
- **📋 Order History**: Track all past and current orders
- **👤 Profile Management**: View spending statistics and personal info

### 👨‍💼 **Admin Panel** - Complete Business Management  
- **📊 Dashboard**: Real-time business metrics and KPIs
- **🏪 Restaurant Management**: Add/edit restaurants and their details
- **🍽️ Menu Management**: Full CRUD operations for menu items
- **📦 Order Management**: View and update order statuses
- **🚚 Partner Management**: Manage delivery personnel
- **💳 Payment Monitoring**: Track all payment transactions
- **📈 Analytics**: Advanced reports and business insights
- **👥 User Management**: View all customer accounts

### 🚚 **Delivery Partner Panel** - Delivery Operations
- **📦 Assigned Orders**: View orders assigned to the partner
- **🚚 Delivery Workflow**: 
  - Accept orders → Start delivery → Mark as delivered
- **💰 Payment Collection**: Handle COD payments at delivery
- **📊 Performance Stats**: Delivery metrics and earnings

## 🔄 Core Workflow

### Order Processing Pipeline:
1. **Customer** browses restaurants → adds items to cart → checks out
2. **System** automatically:
   - Creates payment record
   - Assigns random delivery partner  
   - Reduces inventory quantities
3. **Delivery Partner** receives order → updates status → collects payment
4. **Admin** monitors entire process and can intervene if needed

### Smart Features:
- ✅ **Auto inventory management** - quantities update in real-time
- ✅ **Automatic partner assignment** - random but fair distribution
- ✅ **Payment status synchronization** - updates when order delivered
- ✅ **Rating system** - partners get rating boosts on successful deliveries
- ✅ **COD handling** - payment only collected upon delivery

## 🛠️ Technical Implementation

### Database Integration:
- **MySQL** with stored procedures, functions, and triggers
- **Automatic payment creation** for COD orders via triggers
- **Rating updates** through automated trigger system
- **Inventory validation** during checkout

### Session Management:
- Role-based access control
- Persistent cart across sessions
- Secure authentication flow
- State management for multi-step processes

### UI/UX Features:
- Responsive Streamlit interface
- Real-time data updates
- Intuitive navigation
- Visual status indicators
- Comprehensive error handling

This multi-panel architecture ensures **seamless collaboration** between customers, admins, and delivery partners while maintaining **data integrity** and **business logic consistency** throughout the entire food delivery ecosystem.
