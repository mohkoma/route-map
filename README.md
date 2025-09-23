# 🗺️ Route Map CSV Uploader

A modern web application that allows you to upload CSV files containing GPS coordinates and timestamps to visualize routes on an interactive map.

## Features

- **CSV File Upload**: Upload CSV files with latitude, longitude, and timestamp data
- **Interactive Map**: View routes on a beautiful, interactive map using Leaflet
- **Waypoint Markers**: Each waypoint is marked with a numbered marker
- **Timestamp Display**: Click on any waypoint to see the timestamp and coordinates
- **Route Information**: View total distance, duration, and waypoint count
- **Modern UI**: Clean, responsive design with gradient backgrounds and smooth animations
- **Error Handling**: Comprehensive error handling and validation

## CSV Format

Your CSV file should contain the following columns (column names are flexible):

- **Latitude**: Column containing latitude values (looks for "lat" in column name)
- **Longitude**: Column containing longitude values (looks for "lng" or "lon" in column name)
- **Timestamp**: Column containing timestamp data (looks for "created_at", "timestamp", or "time" in column name)
- **Speed**: Column containing speed data in meters per second (m/s) - automatically converted to km/h for display

### Example CSV Format:

```csv
id,drive_id,lat,lng,heading,speed,created_at,updated_at
1,100,59.15397716,17.64833628,322.04895020,2.8,"2025-01-15 09:00:00","2025-01-15 09:00:00"
2,100,59.17038923,17.64826827,345.80773926,7.8,"2025-01-15 09:02:30","2025-01-15 09:02:30"
```

**Note**: Speed values are in meters per second (m/s) as provided by GPS devices, and are automatically converted to km/h for display.

## How to Use

1. **Open the Application**: Open `map.html` in your web browser
2. **Upload CSV**: Click "Choose CSV File" and select your CSV file
3. **View Route**: The application will automatically parse your data and display the route
4. **Interact**:
   - Click on waypoint markers to see timestamps and coordinates
   - Use map controls to zoom and pan
   - View route statistics in the info panel
5. **Clear Map**: Click "Clear Map" to remove the current route and upload a new file

## Technical Details

- **Map Library**: Leaflet.js with OpenStreetMap tiles
- **Routing**: Leaflet Routing Machine for road-following paths
- **File Processing**: Client-side CSV parsing (no server required)
- **Responsive Design**: Works on desktop and mobile devices

## Browser Compatibility

- Chrome (recommended)
- Firefox
- Safari
- Edge

## Sample Data

A sample CSV file (`sample-route.csv`) is included to demonstrate the expected format.

## Features in Detail

### Route Visualization

- Blue route line following roads
- Numbered waypoint markers
- Automatic map fitting to show entire route

### Information Display

- **Waypoint Count**: Total number of GPS points
- **Duration**: Time between first and last timestamp
- **Distance**: Total distance in kilometers (straight-line calculation)

### Error Handling

- Validates CSV format and required columns
- Shows helpful error messages
- Handles file reading errors gracefully

## Customization

The application is built with vanilla JavaScript and can be easily customized:

- **Map Style**: Change the tile layer in the `initializeMap()` function
- **Route Colors**: Modify the `lineOptions` in the routing control
- **Marker Style**: Customize the marker appearance in the `createMarker` function
- **UI Colors**: Update the CSS variables for different color schemes

## License

This project is open source and available under the MIT License.
