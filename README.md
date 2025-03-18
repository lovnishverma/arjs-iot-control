# AR.js Web-Based IoT Control
Live Demo: https://nielitar.glitch.me/


![nielitar](https://github.com/user-attachments/assets/a6397754-7c8b-4d2c-aeee-49e1582f0df3)

This project uses **AR.js** and **A-Frame** to detect a custom marker and send control signals to an IoT application. When the marker is detected, the system sends a request to toggle the state of an external application hosted on **Glitch**.

## Features

- **Custom Marker Detection**: Uses a `.patt` file for custom marker recognition.
- **3D Box Visualization**: Displays a 3D box that changes color based on the application state.
- **Web-Based AR Implementation**: Works directly in the browser using a webcam.
- **IoT Control via API**: Sends HTTP requests to toggle an IoT-based system.

## Technologies Used

- **HTML, JavaScript**
- **A-Frame (1.2.0)**
- **AR.js**
- **Glitch (for backend toggle service)**

## Getting Started

### 1. Clone or Download the Repository

```sh
git clone https://github.com/lovnishverma/arjs-iot-control.git
cd arjs-iot-control
```

### 2. Setup a Web Server

Since the `.patt` file needs to be accessible via a URL, you can:

- Host it on **Glitch**, **GitHub Pages**, **Firebase Hosting**, or any static file server.
- If testing locally, use Python's built-in HTTP server:
  ```sh
  python3 -m http.server
  ```
  Then, open `http://localhost:8000` in your browser.

### 3. Run the Project

- Open `index.html` in a browser.
- Ensure your `.patt` file is correctly hosted and accessible.
- Print the marker (`pattern-nielit.patt`) and hold it in front of your webcam.
- The 3D box should appear, and the system should send **on/off** requests to the IoT backend.

## API Endpoint

The system communicates with an external application using the following API:

```sh
GET https://roomcontrol.glitch.me/toggle-app?state=on  # Turns the app on
GET https://roomcontrol.glitch.me/toggle-app?state=off # Turns the app off
```

### Example Response

```sh
App turned on
```

## Troubleshooting

1. **Marker Not Detected?**
   - Check if the `.patt` file URL is correct and accessible.
   - Ensure there is enough light for the webcam to detect the marker.
2. **3D Box Not Appearing?**
   - Open DevTools (`F12` → Console) and check for errors.
   - Make sure A-Frame and AR.js are loading properly.
3. **IoT Toggle Not Working?**
   - Open `https://roomcontrol.glitch.me/toggle-app?state=on` in your browser to verify it responds.
   - Check network requests in DevTools (`F12` → Network).

## Future Enhancements

- Add a UI button to manually trigger the IoT toggle.
- Improve marker recognition by optimizing the `.patt` file.
- Implement WebRTC for better real-time AR tracking.

## License

This project is licensed under the **MIT License**. Feel free to modify and distribute it.

---

### Author

**Lovnish Verma**  
[GitHub](https://github.com/lovnishverma)  
[Website](https://lovnishverma.glitch.me) 
[Website](https://lovnishverma.glitch.me)  

