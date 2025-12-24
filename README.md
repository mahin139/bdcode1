<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Birthday Surprise 🎉</title>

<style>
body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    font-family:'Segoe UI',sans-serif;
    background:linear-gradient(135deg,#6a11cb,#2575fc);
    overflow:hidden;
    color:white;
}

#intro{
    text-align:center;
    animation:fadeIn 1.5s ease;
}

#intro button{
    padding:15px 35px;
    font-size:1.3em;
    border:none;
    border-radius:10px;
    background:rgba(255,255,255,0.2);
    color:white;
    cursor:pointer;
    text-shadow:0 0 5px #000;
    transition:0.3s;
}
#intro button:hover{
    background:rgba(255,255,255,0.4);
}

.card{
    display:none;
    text-align:center;
    padding:45px 65px;
    border-radius:25px;
    background:rgba(255,255,255,0.2);
    backdrop-filter:blur(12px);
    box-shadow:0 20px 40px rgba(0,0,0,0.25);
    animation:zoom 1.4s ease;
    color:white;
}

h1{
    font-size:3em;
    margin-bottom:15px;
    text-shadow:0 0 25px rgba(255,255,255,0.8);
}

p{
    font-size:1.2em;
    line-height:1.6;
    opacity:0;
    animation:fade 2s forwards;
    animation-delay:1.2s;
    margin-bottom:20px;
}

.signature{
    font-size:1em;
    opacity:0.8;
    font-style:italic;
    animation:fade 2s forwards;
    animation-delay:2.5s;
}

/* Floating hearts */
.heart{
    position:absolute;
    bottom:-30px;
    font-size:22px;
    animation:floatUp 6s linear infinite;
    opacity:0.8;
}

@keyframes floatUp{
    from{transform:translateY(0);opacity:1;}
    to{transform:translateY(-120vh);opacity:0;}
}

@keyframes zoom{
    from{transform:scale(0);opacity:0;}
    to{transform:scale(1);opacity:1;}
}
@keyframes fade{
    to{opacity:1;}
}
@keyframes fadeIn{
    from{opacity:0;}
    to{opacity:1;}
}
</style>
</head>

<body>

<div id="intro">
    <h2>🎁 wanna see something? 🎁</h2>
    <p>Click the button to open </p>
    <button onclick="openCard()">Open 🎉</button>
</div>

<div class="card" id="card">
    <h1>🎂 Happy Birthday! 🎉 Billal vai er chele💖</h1>
    <p>
        
        Wishing you a day full of laughter and joy,<br>
        and a year ahead filled with amazing moments.<br>
        Hope all your dreams come true! ✨<br>
        Sorry for the late ,by the way 
        i made this with the help of chat gpt 😁<br>
    </p>
    <div class="signature">From Mahin</div>
</div>

<script>
function openCard(){
    document.getElementById("intro").style.display="none";
    const card=document.getElementById("card");
    card.style.display="block";
    
    // Floating hearts
    setInterval(()=>{
        const heart=document.createElement("div");
        heart.className="heart";
        heart.innerHTML="❤️";
        heart.style.left=Math.random()*100+"vw";
        heart.style.animationDuration=(Math.random()*3+4)+"s";
        document.body.appendChild(heart);
        setTimeout(()=>heart.remove(),6000);
    },500);
}
</script>

</body>
</html>
