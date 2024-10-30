<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Room Cleaning Status</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 20px;
    }
    .room {
      display: flex;
      align-items: center;
      margin: 10px;
    }
    .room span {
      font-size: 1.2em;
      margin-right: 10px;
    }
    button {
      padding: 8px 15px;
      font-size: 1em;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #45a049;
    }
    .count {
      margin-left: 10px;
      font-size: 0.9em;
      color: #555;
    }
  </style>
</head>
<body>

  <div class="room">
    <span>Kitchen</span>
    <button onclick="recordClick('kitchen')">Cleaned</button>
    <span class="count" id="kitchen-count">0</span>
  </div>

  <div class="room">
    <span>Living Room</span>
    <button onclick="recordClick('livingRoom')">Cleaned</button>
    <span class="count" id="livingRoom-count">0</span>
  </div>

  <script>
    // Function to record the click and update the count
    function recordClick(room) {
      // Get the current count from localStorage or set to 0 if it doesn't exist
      let count = parseInt(localStorage.getItem(room) || '0', 10);
      count++;
      localStorage.setItem(room, count); // Save updated count to localStorage

      // Update the count display
      document.getElementById(`${room}-count`).textContent = count;
    }

    // Function to load the initial counts from localStorage on page load
    function loadCounts() {
      ['kitchen', 'livingRoom'].forEach(room => {
        let count = localStorage.getItem(room) || '0';
        document.getElementById(`${room}-count`).textContent = count;
      });
    }

    // Load counts when the page is loaded
    window.onload = loadCounts;
  </script>

</body>
</html>
