<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>OP MAIL - Temporary Email</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #121212;
      color: #fff;
      text-align: center;
      padding: 2rem;
    }
    .container {
      background-color: #1e1e1e;
      padding: 2rem;
      border-radius: 10px;
      max-width: 600px;
      margin: auto;
    }
    .email-box {
      background: #333;
      padding: 1rem;
      margin-bottom: 1rem;
      border-radius: 5px;
      font-weight: bold;
      font-size: 1.2rem;
    }
    button {
      padding: 0.5rem 1rem;
      margin: 0.5rem;
      font-size: 1rem;
      cursor: pointer;
      border: none;
      border-radius: 5px;
      background-color: #00bcd4;
      color: white;
    }
    .message-box {
      background: #2e2e2e;
      padding: 1rem;
      margin: 0.5rem 0;
      border-radius: 5px;
      text-align: left;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>OP MAIL</h1>
    <p>Your Temporary Email Address:</p>
    <div class="email-box" id="emailBox">loading@opmail.com</div>
    <button onclick="copyEmail()">Copy Email</button>
    <button onclick="generateEmail()">New Email</button>
    <button onclick="loadInbox()">Refresh Inbox</button><h2>Inbox</h2>
<div id="inbox"></div>

  </div>  <script>
    function generateRandomEmail() {
      const chars = 'abcdefghijklmnopqrstuvwxyz1234567890';
      let username = '';
      for (let i = 0; i < 10; i++) {
        username += chars.charAt(Math.floor(Math.random() * chars.length));
      }
      return `${username}@opmail.com`;
    }

    function generateEmail() {
      const email = generateRandomEmail();
      document.getElementById("emailBox").innerText = email;
      loadInbox();
    }

    function copyEmail() {
      const email = document.getElementById("emailBox").innerText;
      navigator.clipboard.writeText(email);
      alert("
