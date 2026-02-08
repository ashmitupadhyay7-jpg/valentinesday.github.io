# valentines-day
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Propose Day ❤️</title>

<style>
body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(135deg, #ff758c, #ff7eb3);
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: 'Segoe UI', sans-serif;
    overflow: hidden;
}

/* Proposal Card */
.card {
    background: white;
    padding: 30px;
    border-radius: 20px;
    text-align: center;
    box-shadow: 0 10px 30px rgba(0,0,0,0.3);
    max-width: 360px;
    z-index: 2;
}

h1 {
    color: #ff4d6d;
}

p {
    font-size: 18px;
    color: #333;
}

/* Main Photo */
.main-photo {
    width: 200px;
    height: 200px;
    border-radius: 15px;
    object-fit: cover;
    margin: 15px 0;
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

/* Buttons */
button {
    padding: 10px 22px;
    font-size: 16px;
    border: none;
    border-radius: 20px;
    cursor: pointer;
    margin: 10px;
}

#yes {
    background: #ff4d6d;
    color: white;
}

#no {
    background: #ddd;
}

/* Flying Memory Photos */
.memory {
    position: absolute;
    width: 120px;
    height: 120px;
    object-fit: cover;
    border-radius: 15px;
    animation: fly 6s linear infinite;
    box-shadow: 0 6px 20px rgba(0,0,0,0.3);
    z-index: 1;
}

@keyframes fly {
    0% {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
    }
    100% {
        transform: translateY(-900px) rotate(360deg);
        opacity: 0;
    }
}
</style>
</head>

<body>

<!-- PROPOSAL CARD -->
<div class="card" id="card">
    <h1>Happy Propose Day ❤️</h1>

    <!-- 🔴 YAHAN APNI PHOTO RAKHO -->
    <img src="main.jpg" alt="My Favorite Person" class="main-photo">

    <p>
        I don’t know when it happened, but you became my favorite person.
        Will you be my boyfriend and choose me every day? 💕
    </p>

    <button id="yes" onclick="yesClick()">YES 💖</button>
    <button id="no" onmouseover="moveNo()">NO 🙈</button>
</div>

<!-- MEMORY PHOTOS CONTAINER -->
<div id="memories"></div>

<script>
function yesClick() {
    document.getElementById("card").innerHTML = `
        <h1>Yaaay! 💕🥹</h1>
        <p style="font-size:20px;">
            These memories are just the beginning of our forever ❤️
        </p>
    `;

    // 🔴 YAHAN APNI MEMORY PHOTOS KE NAAM DALO
    const photos = [
        "pic1.jpg",
        "pic2.jpg",
        "pic3.jpg",
        "pic4.jpg"
    ];

    setInterval(() => {
        const img = document.createElement("img");
        img.src = photos[Math.floor(Math.random() * photos.length)];
        img.className = "memory";
        img.style.left = Math.random() * 90 + "vw";
        img.style.bottom = "0px";

        document.getElementById("memories").appendChild(img);

        setTimeout(() => img.remove(), 6000);
    }, 500);
}

function moveNo() {
    const noBtn = document.getElementById("no");
    noBtn.style.position = "absolute";
    noBtn.style.top = Math.random() * 80 + "%";
    noBtn.style.left = Math.random() * 80 + "%";
}
</script>

</body>
</html>
