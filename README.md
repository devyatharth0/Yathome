# Yathhome: A Simple New Tab Extension Inspired by Google's Default Page Design

Yathhome is a browser extension that enhances your new tab experience with a clean, customizable interface inspired by Google's default page design. It offers weather information, customizable shortcuts, and multilingual support.

This extension provides a blend of functionality and simplicity, allowing users to personalize their browsing experience while maintaining a familiar and intuitive layout. Yathhome is designed to work seamlessly across different browsers, including Chrome and Firefox.

## Repository Structure

- `background.js`: Background script for the extension
- `feedback.html`: Feedback form for users
- `index.html`: Main HTML file for the new tab page
- `languages.js`: Translations and language support
- `manifest.json`: Chrome extension manifest file
- `manifest(firefox).json`: Firefox extension manifest file
- `script.js`: Main JavaScript file for extension functionality
- `style.css`: CSS styles for the extension

## Usage Instructions

### Installation

1. Clone the repository or download the source code.
2. For Chrome:
   - Open Chrome and navigate to `chrome://extensions/`
   - Enable "Developer mode" in the top right corner
   - Click "Load unpacked" and select the extension directory
3. For Firefox:
   - Open Firefox and navigate to `about:debugging#/runtime/this-firefox`
   - Click "Load Temporary Add-on" and select the `manifest(firefox).json` file

### Configuration

1. Weather API:
   - The extension uses a default Weather API key, but you can provide your own for better reliability.
   - To add your own key, click on the settings icon and enter your WeatherAPI key in the designated field.

2. Location:
   - By default, the extension attempts to detect your location based on your IP address.
   - You can manually set your location by clicking the settings icon and entering your city or coordinates.

3. Proxy Settings:
   - If you experience issues with search suggestions, you can set up a CORS bypass proxy.
   - Enter the proxy URL in the settings menu under "CORS Bypass Proxy".

4. Customization:
   - Toggle between Celsius and Fahrenheit
   - Enable or disable search suggestions
   - Customize shortcuts and Google Apps menu
   - Switch between 12-hour and 24-hour time formats
   - Add personalized text below the clock

### Features

- Weather Display: Shows current weather conditions, temperature, and humidity
- Customizable Shortcuts: Add and edit shortcuts for quick access to frequently visited sites
- Google Apps Menu: Quick access to popular Google services
- Multilingual Support: Includes translations for English, Portuguese, and Chinese (Simplified)
- Search Functionality: Integrated search bar with support for multiple search engines
- Digital Clock: Displays time in 12-hour or 24-hour format
- Greeting Messages: Dynamic greetings based on the time of day

## Data Flow

1. User opens a new tab in their browser
2. The extension's `index.html` is loaded, which includes `script.js` and `style.css`
3. `script.js` initializes the page:
   - Loads saved settings from localStorage
   - Fetches weather data from WeatherAPI
   - Sets up event listeners for user interactions
4. User interacts with the page:
   - Searches using the search bar
   - Clicks on shortcuts or Google Apps menu items
   - Adjusts settings through the settings menu
5. User actions trigger corresponding functions in `script.js`
6. Data is saved to localStorage when settings are changed
7. The page updates dynamically based on user interactions and fetched data

```
[Browser] -> [New Tab] -> [index.html] -> [script.js]
                                             |
                                             v
[User Interaction] <-> [Event Listeners] <-> [Page Updates]
                                             |
                                             v
[localStorage] <-> [Settings/Data Storage] <-> [WeatherAPI]
```

Note: The extension operates primarily client-side, with the only external data source being the WeatherAPI for weather information.

## Troubleshooting

1. Weather not displaying:
   - Ensure you have an active internet connection
   - Check if you've entered a valid WeatherAPI key in the settings
   - Verify that your location is correctly set or detected

2. Search suggestions not working:
   - Try enabling the CORS bypass proxy in the settings
   - Ensure you have an active internet connection

3. Shortcuts or Google Apps menu not appearing:
   - Check if these features are enabled in the settings menu
   - Try resetting the extension settings and reconfiguring

4. Language issues:
   - Verify that your browser's language settings are correct
   - The extension supports English, Portuguese, and Chinese (Simplified)

For any persistent issues, please submit feedback through the extension's feedback form or contact the developer directly.