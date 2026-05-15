# OpenWeatherMap API Setup Guide

This guide will help you get your free API key and set up the Weather Dashboard.

## Step 1: Create an OpenWeatherMap Account

1. Visit [OpenWeatherMap](https://openweathermap.org/api)
2. Click on **Sign Up** in the top navigation
3. Fill in your details:
   - Email
   - Username
   - Password
   - Accept Terms & Conditions
4. Click **Create Account**
5. Check your email for verification link and confirm

## Step 2: Generate Your API Key

1. Log in to your OpenWeatherMap account
2. Go to **Account** → **API Keys**
3. You should see a default API key generated
4. Copy this key (starts with a long alphanumeric string)

## Step 3: Setup the Weather Dashboard

### Option A: Using the Settings Modal

1. Open `index.html` in your web browser
2. You'll see a message asking for your API key
3. Click on the settings button (if visible) or go to the modal
4. Paste your API key in the **"OpenWeatherMap API Key"** field
5. Select your preferred temperature unit (Celsius or Fahrenheit)
6. Click **Save Settings**

### Option B: Direct Configuration

1. Open `script.js` in a text editor
2. Find this line (around line 5):
   ```javascript
   API_KEY: localStorage.getItem('weatherApiKey') || '',
   ```
3. Replace the empty string with your API key:
   ```javascript
   API_KEY: localStorage.getItem('weatherApiKey') || 'your_actual_api_key_here',
   ```
4. Save the file

## Step 4: Verify Everything Works

1. Open `index.html` in your browser
2. You should see the current weather for your location (after allowing location access)
3. Try searching for different cities
4. Check that the hourly and daily forecasts load correctly

## API Rate Limits

**Free Tier:**
- 60 calls/minute
- 1,000,000 calls/month
- This is more than enough for personal use!

**What's Included:**
- Current weather
- 5-day forecast
- Hourly forecasts
- Geolocation-based weather

## Troubleshooting

### "City not found" Error
- Make sure the city name is spelled correctly
- Try a more well-known city (e.g., "London" instead of a small town)

### "Invalid API Key" Error
- Verify you've copied the entire API key correctly
- Check if your account is verified (check your email)
- API keys may take a few minutes to become active after creation

### "Permission Denied" for Location
- Allow location access when your browser prompts
- You can manually search for cities as an alternative

### Weather Data Not Loading
- Check your internet connection
- Verify your API key is correct
- Check that you have API calls remaining (not exceeded rate limit)
- Open browser developer console (F12) to see any error messages

## Advanced Features

### Using Different Endpoints

The dashboard uses:
- `weather` endpoint for current weather
- `forecast` endpoint for 5-day forecast

You can extend this to use:
- `air_pollution` for air quality data
- `uvi` for UV index
- `onecall` for comprehensive weather data (paid feature)

### Caching

The dashboard automatically caches API responses for 10 minutes to reduce API calls. This is stored in your browser's localStorage.

### Local Storage

The dashboard stores:
- API Key
- Temperature unit preference
- Theme preference (dark/light mode)
- Favorite cities
- Search history

All data is stored locally in your browser and never sent to external servers (except OpenWeatherMap for weather data).

## Additional Resources

- [OpenWeatherMap Documentation](https://openweathermap.org/api)
- [API Response Examples](https://openweathermap.org/weather-conditions)
- [Icons & Conditions](https://openweathermap.org/weather-conditions)

## Support

For issues with:
- **Weather Dashboard**: Check the troubleshooting section above or create an issue on GitHub
- **OpenWeatherMap API**: Visit their documentation or support page

Enjoy your Weather Dashboard! 🌤️
