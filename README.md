# Valentine-<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #fce4ec;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            text-align: center;
            overflow: hidden;
        }
        img {
            max-width: 280px;
            border-radius: 15px;
            margin-bottom: 15px;
        }
        h1 {
            color: #d81b60;
        }
        .buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
        }
        button {
            padding: 12px 25px;
            border: none;
            border-radius: 30px;
            font-size: 1.1rem;
            cursor: pointer;
        }
        #yesBtn {
            background: #e91e63;
            color: white;
        }
        #noBtn {
            background: white;
        }
    </style>
</head>
<body>

<div>
    <img id="mainImage" src="ask.gif" alt="Valentine">
    <h1>Will you be my Valentine Bubu?</h1>

    <div class="buttons">
        <button id="yesBtn">Yes</button>
        <button id="noBtn">No</button>
    </div>
</div>

<script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const img = document.getElementById("mainImage");
    const text = document.querySelector("h1");

    function moveNo() {
        const x = Math.random() * (window.innerWidth - 100);
        const y = Math.random() * (window.innerHeight - 100);
        noBtn.style.position = "absolute";
        noBtn.style.left = x + "px";
        noBtn.style.top = y + "px";
    }

    noBtn.addEventListener("mouseover", moveNo);
    noBtn.addEventListener("touchstart", moveNo);

    yesBtn.addEventListener("click", () => {
        text.innerHTML = "YAY! I knew it ❤️";
        img.src = "yes.jpg";
        document.querySelector(".buttons").style.display = "none";
        document.body.style.background = "#ffc1e3";
    });
</script>

</body>
</html>
