# index.html
<!DOCTYPE html>
<html lang="ta">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hotel Food Search</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }
        input {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            box-sizing: border-box;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            padding: 10px;
            border-bottom: 1px solid #ccc;
        }
    </style>
</head>
<body>

    <h1>Hotel Food Search</h1>
    <input type="text" id="search" placeholder="உங்கள் உணவை தேடுங்கள்...">
    
    <ul id="food-list">
        <li>சாம்பார் ரைஸ்</li>
        <li>பிரியாணி</li>
        <li>சிட்டி சாப்பாடு</li>
        <li>போன்்டா</li>
        <li>மீன் குழம்பு</li>
        <li>சிக்கன் கிரேவி</li>
    </ul>

    <script>
        const searchInput = document.getElementById('search');
        const foodList = document.getElementById('food-list').getElementsByTagName('li');

        searchInput.addEventListener('keyup', function() {
            let filter = searchInput.value.toLowerCase();
            for (let i = 0; i < foodList.length; i++) {
                let foodItem = foodList[i].textContent.toLowerCase();
                if (foodItem.includes(filter)) {
                    foodList[i].style.display = "";
                } else {
                    foodList[i].style.display = "none";
                }
            }
        });
    </script>

</body>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website</title>
    <script>
        function showAlert() {
            alert('Button clicked! Hello from JavaScript!');
        }
    </script>
</head>
<body>
    <h1>Welcome to My Website</h1>
    <button onclick="showAlert()">Click Me!</button>
</html>
