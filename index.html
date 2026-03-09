const express = require('express');
const app = express();
const http = require('http').Server(app);
const io = require('socket.io')(http);

app.get('/', (req, res) => {
  res.sendFile(__dirname + '/index.html');
});

io.on('connection', (socket) => {
  // रूम जॉइन करना
  socket.on('join', (roomName) => {
    socket.join(roomName);
    socket.to(roomName).emit('ready'); // दूसरे यूजर को बताएं कि हम तैयार हैं
  });

  // वीडियो सिग्नल एक-दूसरे को भेजना
  socket.on('signal', (data) => {
    socket.to(data.room).emit('signal', data.signal);
  });
});

const PORT = process.env.PORT || 3000;
http.listen(PORT, () => console.log('Gola Yaari Server is Live!'));<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gola Yaari - Live Match</title>
    <script src="/socket.io/socket.io.js"></script>
    <style>
        body { background: #000; color: #fff; text-align: center; font-family: sans-serif; margin: 0; }
        .video-box { height: 85vh; display: flex; flex-direction: column; position: relative; }
        video { width: 100%; height: 50%; background: #111; object-fit: cover; }
        #local { width: 120px; height: 160px; position: absolute; bottom: 10px; right: 10px; border: 2px solid #ff4757; z-index: 10; border-radius: 10px; }
        .controls { height: 15vh; display: flex; align-items: center; justify-content: center; background: #222; }
        .btn { background: #28a745; color: white; border: none; padding: 15px 30px; border-radius: 30px; font-size: 18px; cursor: pointer; }
    </style>
</head>
<body>
    <div id="setup">
        <h2 style="margin-top:100px;">Gola Yaari 🎥</h2>
        <button class="btn" onclick="startCall()">कॉल शुरू करें</button>
    </div>

    <div id="call-area" style="display:none;">
        <div class="video-box">
            <video id="remote" autoplay playsinline></video>
            <video id="local" autoplay playsinline muted></video>
        </div>
        <div class="controls">
            <button class="btn" style="background:red;" onclick="location.reload()">End Call</button>
        </div>
    </div>

    <script>
        const socket = io();
        const room = "global_yaari_room";
        let localStream;
        let peerConnection;

        // गूगल के फ्री STUN सर्वर्स (कनेक्शन जोड़ने के लिए)
        const iceServers = {
            iceServers: [{ urls: 'stun:stun.l.google.com:19302' }, { urls: 'stun:stun1.l.google.com:19302' }]
        };

        async function startCall() {
            document.getElementById('setup').style.display = 'none';
            document.getElementById('call-area').style.display = 'block';

            localStream = await navigator.mediaDevices.getUserMedia({ video: true, audio: true });
            document.getElementById('local').srcObject = localStream;

            socket.emit('join', room);
        }

        socket.on('ready', async () => {
            createPeerConnection();
            const offer = await peerConnection.createOffer();
            await peerConnection.setLocalDescription(offer);
            socket.emit('signal', { room, signal: { sdp: offer } });
        });

        socket.on('signal', async (data) => {
            if (!peerConnection) createPeerConnection();

            if (data.sdp) {
                await peerConnection.setRemoteDescription(new RTCSessionDescription(data.sdp));
                if (data.sdp.type === 'offer') {
                    const answer = await peerConnection.createAnswer();
                    await peerConnection.setLocalDescription(answer);
                    socket.emit('signal', { room, signal: { sdp: answer } });
                }
            } else if (data.candidate) {
                await peerConnection.addIceCandidate(new RTCIceCandidate(data.candidate));
            }
        });

        function createPeerConnection() {
            peerConnection = new RTCPeerConnection(iceServers);
            localStream.getTracks().forEach(track => peerConnection.addTrack(track, localStream));

            peerConnection.onicecandidate = (event) => {
                if (event.candidate) {
                    socket.emit('signal', { room, signal: { candidate: event.candidate } });
                }
            };

            peerConnection.ontrack = (event) => {
                document.getElementById('remote').srcObject = event.streams[0];
            };
        }
    </script>
</body>
</html>
