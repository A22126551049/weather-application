import requests

API_KEY = "a4e9bdb1820853a2fd49eefdea8f9b4a"  
BASE_URL = "http://api.openweathermap.org/data/2.5/weather?"

def get_weather(city):
    params = {
        'q': city,
        'appid': API_KEY,
        'units': 'metric' 
    }
    response = requests.get(BASE_URL, params=params)
    if response.status_code == 200:
        data = response.json()
        return data
    else:
        return None

def display_weather(data):
    if data:
        city = data['name']
        temperature = data['main']['temp']
        description = data['weather'][0]['description']
        humidity = data['main']['humidity']
        wind_speed = data['wind']['speed']

        print(f"City: {city}")
        print(f"Temperature: {temperature}°C")
        print(f"Weather: {description}")
        print(f"Humidity: {humidity}%")
        print(f"Wind Speed: {wind_speed} m/s")
    else:
        print("City not found or API request failed.")

def main():
    city = input("Enter city name: ")
    weather_data = get_weather(city)
    display_weather(weather_data)

if __name__ == '__main__':
    main()
