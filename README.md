# ZeoTap-assignment
Real-Time Weather Monitoring App
This project is a real-time weather monitoring system that fetches data from the OpenWeatherMap API and provides detailed, summarized insights on current and forecasted weather conditions. The app displays real-time updates for specified locations (metros in India) and stores data with daily summaries and alerts for user-defined conditions.

Table of Contents
Features
Design Choices
Installation
Dependencies
Setup Instructions
Usage
Data Processing System
Test Cases
Future Improvements
Features
Real-time weather updates for metros in India (Delhi, Mumbai, Chennai, Bangalore, Kolkata, Hyderabad).
Configurable update intervals (e.g., every 5 minutes).
Temperature conversions from Kelvin to Celsius.
Daily aggregates for average, maximum, minimum temperatures, and dominant weather conditions.
Customizable alert thresholds for specific temperature or weather conditions.
Visualizations for daily summaries, historical trends, and triggered alerts.
Design Choices
Data Source: We use the OpenWeatherMap API to obtain weather data, as it provides comprehensive and reliable weather information.
Rollups and Aggregates: Daily summaries with average, max, and min temperatures provide concise daily insights. Dominant weather condition is identified based on the most frequently reported main condition (e.g., Rain, Clear).
Alerting: User-defined thresholds enable personalized alerting, which is efficient for monitoring critical weather conditions.
Visualization: Visual components are implemented to display trends and alerts in an easy-to-understand format, aiding in user interaction and data comprehension.
Installation
To run this application, ensure you have the following installed:

Node.js (for the application server and API calls)
Docker (optional, to run the application within a container environment)
Database (PostgreSQL or MongoDB are recommended for storing weather summaries)
Dependencies
Install the following dependencies:

Express: for setting up a server
Axios: for API requests to OpenWeatherMap
Moment.js: for handling date and time formatting
Mongoose (if using MongoDB) or Sequelize (if using PostgreSQL): for database management
To install all dependencies, run:

bash
Copy code
npm install express axios moment dotenv
# For MongoDB
npm install mongoose
# For PostgreSQL
npm install sequelize pg pg-hstore
Setup Instructions
API Key: Sign up at OpenWeatherMap and generate an API key. Store this key in a .env file.

Database Configuration:

MongoDB: Configure MongoDB with a database URL in .env if you plan to use MongoDB for data storage.
PostgreSQL: Configure PostgreSQL with credentials and URL if using it for storage.
Docker Configuration:

Dockerfile: Set up Docker with a Dockerfile that specifies the environment, application dependencies, and scripts.
Docker-Compose: Optionally, set up docker-compose.yml for a multi-container environment with a database (MongoDB/PostgreSQL) and web server.
Run the Application:

bash
Copy code
npm start
The app should now be running and accessible at localhost:3000.

Usage
Configurable Settings: Define the data update interval (default is every 5 minutes) in the .env file.
Alert Settings: Adjust threshold settings in the config.json file to set specific temperature limits (e.g., alert if temperature exceeds 35°C).
Data Processing System
The system consists of the following main components:

Data Retrieval: The application makes periodic API requests to fetch data for predefined cities.

Temperature Conversion: Temperatures are converted from Kelvin to Celsius for user convenience.

Rollups and Aggregates:

Daily Summaries:
Average Temperature: Calculated from all readings within a day.
Maximum and Minimum Temperatures: The highest and lowest recorded temperatures of the day.
Dominant Condition: The most frequently observed condition (e.g., Rain, Clear).
Threshold Alerts:
Tracks real-time data to trigger alerts when conditions exceed predefined thresholds.
Data Storage: Stores data in a database, allowing for historical insights.

Test Cases
System Initialization:

Confirm the application starts and connects to OpenWeatherMap using a valid API key.
Data Retrieval:

Simulate and verify API calls for each location.
Temperature Conversion:

Test conversions from Kelvin to Celsius or Fahrenheit as per user preference.
Daily Weather Summary:

Run a series of weather updates to validate daily aggregates for average, max, and min temperatures.
Alert System:

Set threshold values and test alert generation by simulating data that crosses these thresholds.
Future Improvements
Extendable Parameters: Support for additional weather parameters (e.g., humidity, wind speed).
Advanced Visualizations: Enhanced trend analysis and forecasting.
Notification System: Email or SMS alerts for threshold breaches.
