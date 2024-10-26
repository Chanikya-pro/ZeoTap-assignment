# Weather App

This project is a responsive weather application that displays real-time weather information and a weekly forecast for the user's current location. It utilizes the OpenWeather API to fetch weather data, and the app is styled with CSS for a clean and intuitive user experience.

## Features

- **Real-Time Weather Data**: Displays the current weather conditions, including temperature, humidity, pressure, wind speed, sunrise, and sunset times.
- **Weekly Forecast**: Shows a daily forecast for the next 5 days.
- **Responsive Design**: Adjusts layout for both mobile and desktop displays.

## Technologies Used

- **HTML**: For structuring the layout.
- **CSS**: For styling and responsive design.
- **JavaScript**: For dynamic data fetching and display updates.
- **Moment.js**: For date and time formatting.
- **OpenWeather API**: To retrieve live weather data.

## Dependencies

To run the application, ensure the following dependencies are set up:

1. **Docker**: Used to create a web server container to host the application.
2. **OpenWeather API Key**: Obtain an API key from [OpenWeather](https://openweathermap.org/api) for data retrieval.

## Installation and Setup

Follow these steps to run the application locally using Docker:

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd weather-app
   ```

2. **Add API Key**:
   - Replace the `API_KEY` in the `script.js` file with your OpenWeather API key:
     ```javascript
     const API_KEY = 'your_openweather_api_key_here';
     ```

3. **Run Docker Container**:
   - Create a Dockerfile in the project root:
     ```dockerfile
     FROM nginx:latest
     COPY . /usr/share/nginx/html
     EXPOSE 80
     CMD ["nginx", "-g", "daemon off;"]
     ```
   - Build and run the container:
     ```bash
     docker build -t weather-app .
     docker run -p 8080:80 weather-app
     ```

4. **Access the Application**:
   - Open a browser and navigate to `http://localhost:8080`.

## Design Choices

- **API**: Chose the OpenWeather API for its comprehensive weather data.
- **Responsive Design**: Media queries ensure a smooth user experience on both desktop and mobile devices.
- **Modular JavaScript**: Functions are separated by purpose for maintainability.
- **CSS Flexbox**: Used for flexible layout adjustments across different screen sizes.

## Future Improvements

- **Enhanced Forecasts**: Extend to display hourly weather forecasts.
- **User Input**: Allow users to search for weather in specific locations.
- **Theming**: Provide light and dark mode options based on user preference.

## License

This project is open-source and available under the [MIT License](https://opensource.org/licenses/MIT).
