---
title: "JavaScript APIs"
seoTitle: "JavaScript APIs"
seoDescription: "JavaScript APIs can be categorized into high-level and low-level APIs based on their abstraction and the level of detail they expose to developers."
datePublished: Tue Dec 19 2023 10:56:06 GMT+0000 (Coordinated Universal Time)
cuid: clqc8br9l000i08jt3dgx2yvs
slug: javascript-apis
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/Zs5X1KnHUzw/upload/6235114c6c0372d4a16f1a80347de46a.jpeg
tags: js, javascript, saifur-rahman-mahin, javascript-apis

---

# JavaScript APIs

JavaScript APIs can be categorized into high-level and low-level APIs based on their abstraction and the level of detail they expose to developers. High-level APIs provide more abstraction, making it easier for developers to work with certain functionalities without delving into intricate details. On the other hand, low-level APIs offer more control and detail, allowing developers to fine-tune their implementations.

## 🚀 **High-Level JavaScript APIs:**

1. **🏰 DOM (Document Object Model) API:**
    
    * Manipulates the structure and content of HTML documents.
        
    * Example: `document.getElementById('example').innerHTML = 'New content';`
        
2. **🌐 Web API (Fetch API):**
    
    * Fetches resources across the network asynchronously.
        
    * Example: `fetch('`[`https://api.example.com/data').then(response`](https://api.example.com/data').then(response) `=> response.json());`
        
3. **💾 Web Storage API:**
    
    * Provides methods for storing data on the client side.
        
    * Example: `localStorage.setItem('username', 'John');`
        
4. **🌍 Geolocation API:**
    
    * Retrieves the user's geographical location.
        
    * Example: `navigator.geolocation.getCurrentPosition(successCallback, errorCallback);`
        
5. **🎨 Canvas API:**
    
    * Allows dynamic, scriptable rendering of 2D shapes and bitmap images.
        
    * Example: Drawing a rectangle on a canvas.
        
6. **🔊 Web Audio API:**
    
    * Provides advanced audio processing and synthesis capabilities.
        
    * Example: Creating and manipulating audio nodes for custom sound effects.
        
7. **🗣️ Speech Recognition API:**
    
    * Converts spoken language into text.
        
    * Example: Implementing voice commands in a web application.
        
8. **👀 Intersection Observer API:**
    
    * Observes changes in the intersection of an element with an ancestor or the viewport.
        
    * Example: Lazy loading images as they come into view.
        
9. **🦷 Web Bluetooth API:**
    
    * Enables web pages to communicate with Bluetooth devices.
        
    * Example: Connecting to a Bluetooth-enabled fitness tracker.
        
10. **🗣️ Web Speech API (Text-to-Speech):**
    
    * Converts text into spoken language.
        
    * Example: Providing an accessibility feature for reading web content aloud.
        
11. **💳 Payment Request API:**
    
    * Streamlines the payment process on the web.
        
    * Example: Initiating a payment request for an online purchase.
        
12. **🕶️ WebXR API (Extended Reality):**
    
    * Provides access to virtual reality (VR) and augmented reality (AR) devices.
        
    * Example: Building immersive VR experiences using WebXR.
        
13. **🔔 Notification API:**
    
    * Displays system-level notifications to the user.
        
    * Example: Notifying users of new messages or updates.
        
14. **🔋 Battery Status API:**
    
    * Retrieves information about the device's battery.
        
    * Example: Adjusting power-intensive features based on battery level.
        
15. **🎥 MediaDevices API (getUserMedia):**
    
    * Accesses connected media devices like cameras and microphones.
        
    * Example: Capturing user's camera input for video conferencing.
        

## ⚙️ **Low-Level JavaScript APIs:**

1. **🔄 WebGL API:**
    
    * Renders 3D graphics in the browser using the GPU.
        
    * Example: Creating a 3D visualization or game.
        
2. **🌐 WebSockets API:**
    
    * Enables bidirectional communication between clients and servers.
        
    * Example: Real-time chat applications.
        
3. **🛠️ Web Workers API:**
    
    * Runs scripts in the background to perform parallel processing.
        
    * Example: Offloading CPU-intensive tasks to improve performance.
        
4. **🗄️ IndexedDB API:**
    
    * Provides a low-level, asynchronous API for storing large amounts of structured data.
        
    * Example: Creating an offline-capable web application with a local database.
        
5. **📁 File API (deprecated):**
    
    * Interacts with files on the user's device (deprecated in favor of File System Access API).
        
    * Example: Reading and writing files in a browser-based text editor.
        
6. **📡 WebRTC API:**
    
    * Enables real-time communication, including video and audio streaming.
        
    * Example: Implementing video conferencing directly in the browser.
        
7. **🔒 Pointer Lock API:**
    
    * Locks the mouse cursor within a specific element.
        
    * Example: Creating immersive first-person navigation experiences.
        
8. **📁 File System Access API:**
    
    * Allows web applications to read or save files on the user's device.
        
    * Example: Accessing and modifying local files securely.
        
9. **🎮 Gamepad API:**
    
    * Provides access to game controllers connected to the device.
        
    * Example: Implementing game controls for browser-based games.
        
10. **🚀 WebAssembly (Wasm):**
    
    * Executes low-level code written in languages like C and C++ in the browser.
        
    * Example: Boosting performance by running computationally intensive tasks in WebAssembly.
        
11. **🔑 WebCrypto API:**
    
    * Offers cryptographic operations in the browser.
        
    * Example: Encrypting and decrypting data securely in a web application.
        
12. **🔌 WebUSB API:**
    
    * Enables communication with USB devices.
        
    * Example: Interfacing with hardware devices connected via USB.
        
13. **🛠️ Service Workers API:**
    
    * Acts as a proxy between web applications and the network, enabling offline capabilities.
        
    * Example: Caching resources for offline access.
        
14. **🔄 WebSocket API:**
    
    * Facilitates real-time, bidirectional communication between clients and servers.
        
    * Example: Building a live updating dashboard.
        
15. **🎵 Web MIDI API:**
    
    * Provides access to MIDI devices, allowing web applications to interact with musical instruments.
        
    * Example: Creating browser-based music applications.
        

## 🌐 **Hardware-Level JavaScript APIs:**

1. **📡 WebRTC API:**
    
    * Enables real-time communication, including video and audio streaming.
        
    * Example: Implementing video conferencing directly in the browser.
        
2. **🔍 Web NFC API:**
    
    * Allows web applications to interact with Near Field Communication (NFC) devices.
        
    * Example: Reading information from NFC-enabled tags.
        
3. **📳 Vibration API:**
    
    * Controls the device's vibration hardware.
        
    * Example: Providing haptic feedback in response to user actions.
        
4. **🔋 Battery Status API (deprecated):**
    
    * Retrieves information about the device's battery (deprecated in favor of Battery Status API).
        
    * Example: Adjusting power-intensive features based on battery level.
        
5. **🔓 Web Locks API:**
    
    * Allows web applications to request a lock to prevent conflicts in shared resources.
        
    * Example: Synchronizing access to a shared resource in a multi-tab application.
        
6. **🌌 Wake Lock API:**
    
    * Prevents the device from going to sleep, ensuring that the screen remains active.
        
    * Example: Keeping the screen awake during a video playback.
        
7. **📡 Web Serial API:**
    
    * Provides access to serial ports on the user's device.
        
    * Example: Communicating with external hardware through serial connections.
        
8. **🔧 WebHID API:**
    
    * Enables communication with Human Interface Devices (HID) connected to the device.
        
    * Example: Interacting with custom input devices.
        
9. **🗣️ Web Speech API (Speech Recognition):**
    

* Converts spoken language into text.
    
    * Example: Implementing voice commands for hands-free interaction.
        

1. **🔊 Web Audio API (MIDI):**
    
    * Integrates MIDI controllers with web audio applications.
        
    * Example: Creating music using MIDI input in the browser.
        
2. **🔑 Web Authentication API (WebAuthn):**
    
    * Enables password-less authentication using hardware tokens.
        
    * Example: Implementing secure, hardware-backed authentication.
        
3. **🎮 Web Gamepad API:**
    
    * Provides access to game controllers connected to the device.
        
    * Example: Implementing game controls for browser-based games.
        
4. **🌐 WebVR API (deprecated):**
    
    * Deprecated in favor of WebXR API. Provided access to Virtual Reality (VR) devices.
        
    * Example: Building immersive VR experiences using WebVR (deprecated).
        
5. **💡 Ambient Light Sensor API:**
    
    * Retrieves information about the ambient light level around the device.
        
    * Example: Adjusting the display brightness based on ambient light.
        
6. **🔄 Proximity Sensor API:**
    
    * Detects the presence of nearby objects or surfaces.
        
    * Example: Implementing gesture-based controls using proximity sensing.
        
7. **🎤 MediaRecorder API:**
    
    * Records media streams, such as audio and video.
        
    * Example: Implementing a web-based voice recorder or video recorder.