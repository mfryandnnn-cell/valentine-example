<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Valentine 💖</title>
<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins', sans-serif;
}

body{
    background: linear-gradient(135deg,#ff4e8a,#ff9ecf);
    overflow:hidden;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    color:white;
}

/* Floating Hearts */
.heart{
    position:absolute;
    width:20px;
    height:20px;
    background:red;
    transform:rotate(45deg);
    animation: fall linear infinite;
}
.heart::before,
.heart::after{
    content:'';
    position:absolute;
    width:20px;
    height:20px;
    background:red;
    border-radius:50%;
}
.heart::before{ top:-10px; left:0; }
.heart::after{ left:-10px; top:0; }

@keyframes fall{
    0%{ transform:translateY(-10vh) rotate(45deg); opacity:1;}
    100%{ transform:translateY(110vh) rotate(360deg); opacity:0;}
}

/* Container */
.container{
    text-align:center;
    z-index:10;
    animation: fadeIn 2s ease;
}

@keyframes fadeIn{
    from{opacity:0; transform:scale(0.8);}
    to{opacity:1; transform:scale(1);}
}

/* Slider */
.slider{
    width:350px;
    height:200px;
    margin:20px auto;
    position:relative;
    overflow:hidden;
    border-radius:20px;
    box-shadow:0 0 20px rgba(255,255,255,0.6);
}

.slide{
    position:absolute;
    width:100%;
    height:100%;
    display:flex;
    justify-content:center;
    align-items:center;
    font-size:22px;
    font-weight:bold;
    opacity:0;
    transition:opacity 1s ease;
}

.slide.active{
    opacity:1;
}

/* Button */
button{
    margin-top:20px;
    padding:10px 25px;
    border:none;
    border-radius:30px;
    background:white;
    color:#ff4e8a;
    font-weight:bold;
    cursor:pointer;
    transition:0.3s;
}

button:hover{
    transform:scale(1.1);
    background:#ffe0ef;
}
</style>
</head>
<body>

<div class="container">
    <h1>Happy Valentine 💕</h1>
    
    <div class="slider">
        <div class="slide active">Kamu adalah alasan senyumku 😊</div>
        <div class="slide">Terima kasih sudah hadir di hidupku 💖</div>
        <div class="slide">Semoga cinta kita selalu abadi 🌹</div>
    </div>

    <button onclick="alert('I Love You 💘')">Klik Aku 💌</button>
</div>

<script>
// SLIDER
let slides = document.querySelectorAll(".slide");
let index = 0;

function showSlide(){
    slides.forEach(s => s.classList.remove("active"));
    index = (index + 1) % slides.length;
    slides[index].classList.add("active");
}
setInterval(showSlide, 3000);

// FLOATING HEARTS
function createHeart(){
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 5000);
}
setInterval(createHeart, 300);
</script>

</body>
</html>
