<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Static Buttons with Menu Specific Actions</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f0f0f0;
    }
    .menu-container {
      display: flex;
      gap: 20px;
      margin-bottom: 20px;
    }
    .menu {
      background-color: #fff;
      border: 1px solid #ccc;
      border-radius: 5px;
      width: 150px;
      text-align: center;
      padding: 10px;
    }
    .buttons {
      display: flex;
      gap: 8px;
    }
    button {
      padding: 10px 20px;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 3px;
      cursor: pointer;
    }
    #menu1-forward {
        width: 170px;
    }
    #menu2-forward {
        width: 82px;
    }
    #menu2-backward {
        width: 82px;
    }
    #menu3-backward {
        width: 170px;
    }
    button:hover {
      background-color: #0056b3;
    }
  </style>
</head>
<body>
  <div class="menu-container" id="menuContainer">
    <div class="menu-1">
      <div class="menu" id="menu1">Menu 1</div>
      <button id="menu1-forward" onclick="moveForward('menu1')">&#8594;</button>
    </div>
    <div class="menu-2">
      <div class="menu" id="menu2">Menu 2</div>
      <button id="menu2-backward" onclick="moveBackward('menu2')">&#8592;</button>
      <button id="menu2-forward" onclick="moveForward('menu2')">&#8594;</button>
    </div>
    <div class="menu-3">
      <div class="menu" id="menu3">Menu 3</div>
      <button id="menu3-backward" onclick="moveBackward('menu3')">&#8592;</button>
    </div>
  </div>
  <script>
    function moveForward(menuId) {
      const container = document.getElementById('menuContainer');
      const menu = document.getElementById(menuId);

      if (menu.parentElement.nextElementSibling) {
        container.insertBefore(menu.parentElement.nextElementSibling, menu.parentElement);
      }
    }

    function moveBackward(menuId) {
      const container = document.getElementById('menuContainer');
      const menu = document.getElementById(menuId);

      if (menu.parentElement.previousElementSibling) {
        container.insertBefore(menu.parentElement, menu.parentElement.previousElementSibling);
      }
    }
  </script>
</body>
</html>
