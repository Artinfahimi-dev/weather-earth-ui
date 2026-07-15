# 🌍 Earth Weather Explorer

Earth Weather Explorer is a responsive web application that allows users to check real-time weather conditions by searching for a city or selecting any location directly on an interactive satellite map.

The project uses **Flask** for the backend, **OpenWeatherMap API** for live weather data, and **Leaflet.js** with Esri satellite tiles for the interactive map.

## ✨ Features

- Search weather information by city name
- Click anywhere on the map to get weather data for that location
- Interactive satellite map with smooth zoom and movement
- Quick-access buttons for popular cities
- Displays:
  - Current temperature
  - Feels-like temperature
  - Weather description and icon
  - Humidity
  - Wind speed
  - Atmospheric pressure
- Responsive glassmorphism user interface
- Error handling for invalid cities, missing API keys, and connection problems

## 🛠️ Technologies Used

### Backend

- Python
- Flask
- Requests
- Python Dotenv

### Frontend

- HTML5
- CSS3
- JavaScript
- Leaflet.js
- Esri World Imagery

### API

- OpenWeatherMap Current Weather API

## 📁 Project Structure

```text
weather_earth_ui/
├── app.py
├── requirements.txt
├── .env
├── README.md
├── static/
│   ├── script.js
│   └── style.css
└── templates/
    └── index.html
```

## 🚀 Installation and Setup

### 1. Clone or download the project

```bash
git clone https://github.com/your-username/weather-earth-ui.git
cd weather-earth-ui
```

You can also download the project as a ZIP file and extract it.

### 2. Create a virtual environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS or Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install the required packages

```bash
python -m pip install -r requirements.txt
```

### 4. Get an OpenWeatherMap API key

1. Create an account on OpenWeatherMap.
2. Generate an API key from your account dashboard.
3. Create a `.env` file in the project root.
4. Add your API key as shown below:

```env
OPENWEATHER_API_KEY=your_api_key_here
```

> Never publish your real `.env` file or API key on GitHub.

### 5. Run the application

```bash
python app.py
```

Open the following address in your browser:

```text
http://127.0.0.1:5000
```

## 📡 API Endpoint

The Flask backend provides one weather endpoint.

### Search by city

```http
GET /api/weather?city=Muscat
```

### Search by coordinates

```http
GET /api/weather?lat=23.5880&lon=58.3829
```

### Example response

```json
{
  "city": "Muscat",
  "country": "OM",
  "lat": 23.6139,
  "lon": 58.5922,
  "temperature": 32.5,
  "feels_like": 36.1,
  "humidity": 55,
  "pressure": 1002,
  "wind_speed": 4.2,
  "description": "clear sky",
  "icon": "01d"
}
```

## 🔐 Security Notes

- Keep the OpenWeatherMap API key inside the `.env` file.
- Add `.env` to `.gitignore` before uploading the project to GitHub.
- Disable Flask debug mode before deploying the application publicly.
- Use a production WSGI server such as Gunicorn or Waitress for deployment.

Suggested `.gitignore` content:

```gitignore
.env
venv/
__pycache__/
*.pyc
```

## 🌐 How It Works

1. The user enters a city name or clicks a location on the map.
2. JavaScript sends a request to the Flask `/api/weather` endpoint.
3. Flask securely adds the OpenWeatherMap API key and requests current weather data.
4. The backend returns a simplified JSON response.
5. The interface updates the weather panel, map position, and marker.

## 💡 Possible Future Improvements

- Add hourly and seven-day forecasts
- Detect the user's current location
- Add temperature-unit selection between Celsius and Fahrenheit
- Save favorite cities
- Add weather alerts
- Add animated weather effects
- Add light and dark themes
- Deploy the project online

## 📄 License

This project is intended for educational and portfolio use. You may modify and expand it for your own projects.

## 👤 Author

Developed as an interactive weather and map-based web application.
