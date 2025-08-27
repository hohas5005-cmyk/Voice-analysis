<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Voicely Chat</title>
<style>
  body { font-family: Arial, sans-serif; background: #f5f5f5; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
  #chat-container { width: 400px; background: #fff; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.1); padding: 20px; }
  #messages { height: 300px; overflow-y: auto; border: 1px solid #ddd; padding: 10px; border-radius: 5px; }
  .message { margin: 5px 0; }
  .user { color: blue; }
  .bot { color: green; }
  #input-container { display: flex; margin-top: 10px; }
  #user-input { flex: 1; padding: 5px; }
  #send-btn { padding: 5px 10px; }
</style>
</head>
<body>
<div id="chat-container">
  <h3>Voicely Analysis</h3>
  <div id="messages"></div>
  <div id="input-container">
    <input type="text" id="user-input" placeholder="اكتب رسالتك هنا...">
    <button id="send-btn">إرسال</button>
  </div>
</div>
<script>
  const messages = document.getElementById('messages');
  const input = document.getElementById('user-input');
  const sendBtn = document.getElementById('send-btn');function addMessage(text, sender) { const msgDiv = document.createElement('div'); msgDiv.classList.add('message', sender); msgDiv.textContent = text; messages.appendChild(msgDiv); messages.scrollTop = messages.scrollHeight; }

function botReply(userMsg) { if(userMsg.toLowerCase().includes('تحليل صوت')){ addMessage('لرفع ملف صوتي، يرجى الضغط على الرابط التالي: [رفع الملف]', 'bot'); } else if(userMsg.toLowerCase().includes('سعر')){ addMessage('سعر التقرير الأساسي: 1.99$، والتقرير الكامل: 4.99$', 'bot'); } else { addMessage('مرحباً! يمكنك رفع ملف صوتك للحصول على التحليل النفسي.', 'bot'); } }

sendBtn.addEventListener('click', () => { const userMsg = input.value.trim(); if(userMsg === '') return; addMessage(userMsg, 'user'); input.value = ''; setTimeout(() => botReply(userMsg), 500); }); </script>

</body>
</html>
