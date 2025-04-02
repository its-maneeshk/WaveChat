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



Below is a visual wireframe in a text-based diagram format for your offline messaging and calling app. You can use these diagrams as a blueprint to create high-fidelity mockups later.

1. Welcome Screen
sql
Copy
Edit
+---------------------------------------------------+
|                   [App Logo]                      |
|                                                   |
|         "Chat and call without mobile             |
|             networks!" (Tagline)                   |
|                                                   |
|                  [Get Started]                    |
|                                                   |
|         [Small Settings Icon] (Top-right)         |
+---------------------------------------------------+
Notes:

A clear introduction with the logo and tagline immediately informs the user.

The “Get Started” button is central, prompting progression.

A settings icon is available for initial configuration.

2. Home Screen
sql
Copy
Edit
+---------------------------------------------------+
| [Hamburger/Menu Icon]      [App Logo]   [Profile] |
+---------------------------------------------------+
|  Nearby Users                                     |
|  --------------------                             |
|  [Avatar]  User1   (Wi-Fi)   →                     |
|  [Avatar]  User2   (Bluetooth) →                   |
|  [Avatar]  User3   (Wi-Fi)   →                     |
|  ...                                              |
|                                                   |
|  Active Chats                                     |
|  --------------------                             |
|  [Avatar]  User1: "Last message preview..."  (unread)|
|  [Avatar]  User4: "Hey, are you..."               |
|  ...                                              |
+---------------------------------------------------+
|             [Start New Chat] (Floating Button)    |
+---------------------------------------------------+
|  Navigation Bar:  Home | Chats | Calls | Settings   |
+---------------------------------------------------+
Notes:

The top bar includes a menu for further navigation and quick access to profile settings.

The “Nearby Users” section auto-lists devices discovered via Wi-Fi Direct/Bluetooth, with visual indicators for connection type.

The Active Chats section shows recent conversations, including an unread message badge if applicable.

The bottom navigation bar gives quick access to key screens.

3. Chat Screen
mathematica
Copy
Edit
+---------------------------------------------------+
|  [Back]   [User's Profile Pic] User Name          |
+---------------------------------------------------+
|  Chat History                                     |
|  ------------------------------------------------ |
|  [Sent] "Hi there!"         [Time]                |
|           ------------------                      |
|  [Received] "Hello!"        [Time]                |
|           ------------------                      |
|  (Messages aligned left/right for sender/receiver)|
|  Status Icons: Pending (🕒), Sent (✔), Delivered (✔✔)|
|  ------------------------------------------------ |
+---------------------------------------------------+
|  [Text Input Field]   [Send Button]   [Voice Call]  |
+---------------------------------------------------+
Notes:

The header shows the chat partner’s profile and a back button to return to the previous screen.

The conversation area displays messages with clear status indicators.

At the bottom, users can type messages, send them, or initiate a voice call.

4. Call Screen
sql
Copy
Edit
+---------------------------------------------------+
|           [Back]   Call with User Name            |
+---------------------------------------------------+
|              Call Status: Ringing...              |
|                                                   |
|                    [Timer]                        |
|                                                   |
|      [Mute Button]   [Speaker Button]             |
|                                                   |
|                   [End Call]                      |
+---------------------------------------------------+
Notes:

The header allows returning to the previous screen and confirms who is on the call.

The call status, duration timer, and control buttons (mute, speaker, and end call) are prominent.

5. Settings Screen
pgsql
Copy
Edit
+---------------------------------------------------+
|             [Back]     Settings                   |
+---------------------------------------------------+
|  Connectivity Controls:                           |
|  -----------------------                          |
|  [ ] Wi-Fi Direct   (Toggle)                      |
|  [ ] Bluetooth      (Toggle)                      |
|  [ ] Sync Messages  (Toggle: On/Off)              |
|                                                   |
|  User Profile:                                    |
|  -----------------------                          |
|  [Avatar]  Nickname: [Edit Field]                 |
|  Status Message: [Edit Field]                     |
|                                                   |
|  App Theme:  [Light / Dark Mode Toggle]           |
|                                                   |
|  About:                                           |
|  -----------------------                          |
|  Version: 1.0                                     |
|  Developer Info, Contact, etc.                    |
+---------------------------------------------------+
Notes:

The settings screen is divided into sections for connectivity, user profile, theme, and app information.

Toggles for Wi-Fi Direct, Bluetooth, and message syncing allow the user to customize their connectivity options.

Navigation Flow Diagram
csharp
Copy
Edit
[Welcome Screen]
       |
       v
[Home Screen] <-------------------------------
       |                                      |
       v                                      |
[Chat Screen] <--> [Active Chats]              |
       |                                      |
       v                                      |
[Call Screen] ---------------------> [Call Logs]
       |
       v
[Settings Screen] <--------------------------
Flow Description:

Welcome Screen: User lands on this screen and taps "Get Started".

Home Screen: Displays Nearby Users and Active Chats. User selects a nearby user to open the Chat Screen.

Chat Screen: Users exchange messages; can also initiate a call by tapping the Voice Call button.

Call Screen: Manages the live call session with mute, speaker, and end call functions.

Settings Screen: Accessible via the navigation bar to adjust connectivity and profile settings.