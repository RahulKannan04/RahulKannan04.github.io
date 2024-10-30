<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Room Cleaning Access</title>
  <style>
    body {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 50px;
      font-family: Arial, sans-serif;
    }
    input, button {
      padding: 10px;
      font-size: 1em;
      margin-top: 10px;
    }
    button {
      background-color: #4CAF50;
      color: white;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }
    button:hover {
      background-color: #45a049;
    }
  </style>
</head>
<body>

  <h2>Enter Access Code</h2>
  <input type="password" id="accessCode" placeholder="Enter your access code" required>
  <button onclick="checkCode()">Submit</button>

  <script>
    // List of valid access codes
    const validCodes = [
      '1083', '1084', '1085', '1086', '1087', '1088', '1089', '1090', '1091', '1092', '1093', '1094', '1095'
    ];

    // Function to check the entered code
    function checkCode() {
      const code = document.getElementById('accessCode').value;
      if (validCodes.includes(code)) {
        // Redirect to the user's personalized page
        window.location.href = `cleaning.html?code=${code}`;
      } else {
        alert('Invalid access code. Please try again.');
      }
    }
  </script>

</body>
</html>
