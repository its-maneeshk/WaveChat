# Offline Messaging & Calling App

## Overview
This project is a mobile application that enables offline messaging and calling without relying on mobile networks. It utilizes **Wi-Fi Direct** and **Bluetooth** for peer-to-peer (P2P) communication and allows **opportunistic syncing** when an internet connection is available.

## Tech Stack
- **Frontend**: React Native (for mobile), TailwindCSS (for styling)
- **Backend**: Node.js with Express (for optional cloud syncing)
- **Database**: Local Storage (AsyncStorage) + Firebase (for online backup)
- **Networking**: Wi-Fi Direct, Bluetooth, WebRTC (optional for internet-based syncing)

---
## App Architecture
The app follows a **modular structure**, focusing on different layers:

1. **UI Layer (Frontend)**: Manages the user interface and interactions.
2. **Network Layer**: Handles P2P communication via Wi-Fi Direct and Bluetooth.
3. **Data Layer**: Stores messages locally and syncs them when online.
4. **Backend API (Optional)**: If cloud sync is enabled, this API facilitates message backup and retrieval.

```
📂 project-root/
 ├── 📂 src/
 │   ├── 📂 components/     # Reusable UI components (buttons, inputs, etc.)
 │   ├── 📂 screens/        # Home, Chat, Call, Settings screens
 │   ├── 📂 services/       # Wi-Fi Direct & Bluetooth connection handlers
 │   ├── 📂 utils/          # Helper functions for networking & storage
 │   ├── App.js            # Main entry point
 ├── 📂 backend/           # Optional cloud syncing backend
 ├── README.md             # Project Documentation
```

---
## UI Flow
### **1. Welcome Screen**
- Displays app logo and a "Get Started" button.
- On click, navigates to the **Home Screen**.

### **2. Home Screen**
- Lists nearby users detected via **Wi-Fi Direct / Bluetooth**.
- Shows recent conversations.
- Allows starting a **new chat** or **calling a user**.

### **3. Chat Screen**
- Displays conversation history.
- Users can send text messages via **P2P communication**.
- Messages are marked as **Sent, Delivered, or Pending** based on connection status.

### **4. Call Screen**
- Enables direct VoIP calls over **Wi-Fi Direct**.
- Includes **Mute, Speaker, and End Call** buttons.

### **5. Settings Screen**
- Toggle **Wi-Fi Direct / Bluetooth**.
- Enable **message syncing** when an internet connection is available.
- View app version and about information.

---
## Installation & Setup
1. **Clone the Repository:**
   ```sh
   git clone https://github.com/your-repo/offline-messaging-app.git
   cd offline-messaging-app
   ```
2. **Install Dependencies:**
   ```sh
   npm install  # or yarn install
   ```
3. **Run the App:**
   ```sh
   npm start  # Starts the app
   ```

---
## Future Enhancements
- **File Sharing** via Wi-Fi Direct
- **Group Chats** using Mesh Networking
- **End-to-End Encryption** for secure messaging

🚀 **Contributions are welcome! Feel free to open an issue or submit a PR.**
