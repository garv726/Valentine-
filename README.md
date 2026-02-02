# Valentine-<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #fce4ec;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            text-align: center;
        }

        h1 {
            color: #d81b60;
            font-size: 2.0rem; /* Slightly smaller for mobile */
            margin-bottom: 20px;
            padding: 0 10px;
        }

        img {
            max-width: 250px; /* Slightly smaller for mobile */
            border-radius: 15px;
            margin-bottom: 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .buttons {
            display: flex;
            gap: 20px;
        }

        button {
            padding: 15px 30px;
            font-size: 1.2rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
        }

        #yesBtn {
            background-color: #e91e63;
            color: white;
            font-weight: bold;
            box-shadow: 0 4px 10px rgba(233, 30, 99, 0.4);
        }

        #noBtn {
            background-color: #ffffff;
            color: #333;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            position: absolute; /* IMPORTANT fix for mobile jumping */
        }
    </style>
</head>
<body>

    <div id="container">
        <img id="mainImage" src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2QyZzZ5eW84dG55eW84dG55eW84dG55eW84dG55eW84dG55eS9z/3oriO0OEd9QIDdllqo/giphy.gif" alt="Cute Valentine"> 
        
        <h1>Will you be my Valentine Bubu?</h1>
        
        <div class="buttons">
            <button id="yesBtn">Yes</button>
            <button id="noBtn" style="position: relative;">No</button>
        </div>
    </div>

    <script>
        const yesBtn = document.getElementById('yesBtn');
        const noBtn = document.getElementById('noBtn');
        const mainImage = document.getElementById('mainImage');
        const headerText = document.querySelector('h1');

        // This function moves the button
        function moveButton() {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth - 20);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight - 20);
            
            noBtn.style.position = 'absolute';
            noBtn.style.left = `${x}px`;
            noBtn.style.top = `${y}px`;
        }

        // Move on hover (computer)
        noBtn.addEventListener('mouseover', moveButton);
        
        // Move on touch (phone)
        noBtn.addEventListener('touchstart', (e) => {
            e.preventDefault(); // Stop it from actually clicking
            moveButton();
        });

        // Click Yes
        yesBtn.addEventListener('click', () => {
            headerText.innerHTML = "YAY! I knew it! 🎉";
            // Replace this link with your 'Happy' image link
            mainImage.src = "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2QyZzZ5eW84dG55eW84dG55eW84dG55eW84dG55eS9z/T86i6yDyOYz7J6v9cx/giphy.gif"; 
            
            // Hide buttons
            yesBtn.style.display = 'none';
            noBtn.style.display = 'none';
            
            document.body.style.backgroundColor = "#ffc1e3";
        });
    </script>
</body>
</html>
