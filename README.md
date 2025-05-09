# UTS-Pemrograman-Web-2
# Pembahasan Utama
1. Persiapan Lingkungan Pengembangan
   
• Instal Node.js: Download dan instal Node.js dari nodejs.org.

• Instal Pustaka WebSocket: Jalankan perintah berikut untuk menginstal pustaka WebSocket:
npm install ws

3. Membuat Server WebSocket (server.js)
• Buat file server.js dengan kode berikut :
const WebSocket = require("ws");
const wss = new WebSocket.Server({ port: 8080 });

wss.on("connection", (ws) => {
  console.log("A user connected");

  setInterval(() => {
    const message = `Notifikasi baru pada ${new Date().toLocaleTimeString()}`;
    ws.send(message);
  }, 5000);

  ws.on("close", () => {
    console.log("A user disconnected");
  });
});

console.log("WebSocket server is running on ws://localhost:8080");
