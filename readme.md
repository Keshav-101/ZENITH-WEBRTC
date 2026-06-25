# 🎥 SecureCall - Peer-to-Peer Video Calling App

A modern, secure, and beautiful peer-to-peer video calling application built with React and WebRTC technology. Connect with anyone instantly without any intermediary servers storing your data.

## ✨ Features

### 🎬 Video Calling
- **HD Video & Audio** - Crystal clear peer-to-peer video calls
- **Real-time Communication** - Low latency WebRTC connections
- **Auto Stream Sync** - Automatic media stream synchronization

### 🎛️ Professional Controls
- **Mute/Unmute Audio** - Toggle your microphone on/off
- **Camera Toggle** - Turn your camera on/off during calls
- **Screen Sharing** - Share your screen with participants
- **End Call** - Gracefully end calls and return to lobby
- **Copy Room Link** - One-click room link sharing

### 🎨 Modern UI/UX
- **Beautiful Gradient Design** - Eye-catching glass-morphism effects
- **Animated Backgrounds** - Smooth pulsing gradient blobs
- **Picture-in-Picture Layout** - Professional video grid layout
- **Connection Status** - Real-time visual connection indicators
- **Responsive Design** - Works perfectly on desktop, tablet, and mobile

### 🔒 Security & Privacy
- **End-to-End Encryption** - WebRTC encrypted peer connections
- **No Data Storage** - No video/audio data stored on servers
- **STUN Servers** - Google and Twilio STUN for NAT traversal
- **Private Rooms** - Join only with room codes

## 🚀 Tech Stack

### Frontend
- **React** - UI library
- **React Router** - Navigation and routing
- **Socket.io Client** - Real-time signaling
- **WebRTC API** - Peer-to-peer connections
- **React Player** - Video stream rendering

### Backend
- **Node.js** - Runtime environment
- **Express** - Web server (implicit)
- **Socket.io** - WebSocket server for signaling

## 📁 Project Structure

```
React-webRTC-main/
│
├── client/                      # Frontend (React)
│   ├── public/
│   │   ├── index.html
│   │   └── ...
│   │
│   ├── src/
│   │   ├── context/
│   │   │   └── SocketProvider.jsx    # Socket.io context
│   │   │
│   │   ├── screens/
│   │   │   ├── Lobby.jsx             # Landing/Join room page
│   │   │   ├── Lobby.css             # Lobby styles
│   │   │   ├── Room.jsx              # Video call room
│   │   │   └── Room.css              # Room styles
│   │   │
│   │   ├── service/
│   │   │   └── peer.js               # WebRTC peer connection logic
│   │   │
│   │   ├── App.js                    # Main app component
│   │   ├── App.css
│   │   ├── index.js                  # React entry point
│   │   └── index.css
│   │
│   └── package.json
│
├── server/                      # Backend (Node.js)
│   ├── index.js                 # Socket.io signaling server
│   └── package.json
│
└── README.md
```

## 🛠️ Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn
- Modern web browser with WebRTC support

### 1. Clone the Repository
```bash
git clone https://github.com/Keshav5339/ZENITH-WEBRTC-.git
cd securecall-webrtc
```

### 2. Install Server Dependencies
```bash
cd server
npm install
```

### 3. Install Client Dependencies
```bash
cd ../client
npm install
```

### 4. Start the Backend Server
```bash
cd server
npm start
```
Server will run on `http://localhost:8000`

### 5. Start the Frontend (In a new terminal)
```bash
cd client
npm start
```
Client will run on `http://localhost:3000`

## 🎮 How to Use

### Starting a Call

1. **Open the App** - Navigate to `http://localhost:3000`
2. **Enter Details**:
   - Your email address
   - Room code (create your own or use an existing one)
3. **Click "Join Room"**
4. **Share the Link** - Copy the room link and send it to others
5. **Wait for Participants** - When someone joins, click "Start Call"

### During a Call

- **🎤 Mute/Unmute** - Click the microphone icon
- **📹 Camera On/Off** - Click the camera icon
- **🖥️ Screen Share** - Click the screen icon to share your display
- **📋 Copy Link** - Click "Copy Link" in header to share
- **❌ End Call** - Click the red phone icon to disconnect

## 🔧 Configuration

### Changing Socket Server URL

In `client/src/context/SocketProvider.jsx`:
```javascript
const socket = useMemo(() => io("localhost:8000"), []);
```
Change to your production URL:
```javascript
const socket = useMemo(() => io("https://your-server.com"), []);
```

### Adding TURN Servers (for better connectivity)

In `client/src/service/peer.js`, add TURN servers:
```javascript
this.peer = new RTCPeerConnection({
  iceServers: [
    {
      urls: [
        "stun:stun.l.google.com:19302",
        "stun:global.stun.twilio.com:3478",
      ],
    },
    {
      urls: "turn:your-turn-server.com:3478",
      username: "username",
      credential: "password"
    }
  ],
});
```

## 🌐 Deployment

### Option 1: Vercel (Frontend) + Render (Backend)

**Frontend (Vercel):**
```bash
cd client
vercel
```

**Backend (Render):**
1. Push code to GitHub
2. Create new Web Service on Render
3. Connect your repo
4. Set build command: `cd server && npm install`
5. Set start command: `node server/index.js`

### Option 2: Railway (Both)

```bash
# Install Railway CLI
npm install -g @railway/cli

# Login
railway login

# Deploy
railway up
```

### Option 3: Heroku

```bash
# Install Heroku CLI
heroku login

# Create apps
heroku create your-app-name-client
heroku create your-app-name-server

# Deploy
git push heroku main
```

## 🐛 Troubleshooting

### Camera/Microphone Not Working
- Check browser permissions
- Ensure HTTPS (required for getUserMedia in production)
- Try a different browser

### Can't Connect to Other User
- Check if both users are on the same network
- Add TURN servers for NAT traversal
- Check firewall settings

### No Audio from Remote User
- Verify remote user's microphone is unmuted
- Check browser audio permissions
- Ensure remote stream is not muted in code

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 Future Enhancements

- [ ] Text chat during calls
- [ ] Group video calls (multiple participants)
- [ ] Call recording feature
- [ ] Virtual backgrounds
- [ ] Noise cancellation
- [ ] User authentication
- [ ] Call history
- [ ] File sharing
- [ ] Hand raise feature
- [ ] Reactions/Emojis


## 👨‍💻 Author

- Keshav Choudhary
- GitHub: [@Keshav-101](https://github.com/Keshav-101)
- LinkedIn: [Keshav choudhary](https://www.linkedin.com/in/keshav-choudhary-746a63248/)
  
## 🙏 Acknowledgments

- WebRTC API documentation
- Socket.io team
- React team
- Google & Twilio for STUN servers

## 📧 Support

If you have any questions or need help, please open an issue or contact me directly.

---

⭐ **Star this repo if you find it helpful!** ⭐

Made with ❤️ using React and WebRTC
