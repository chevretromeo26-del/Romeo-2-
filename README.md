# Romeo-2-
Se trata de una carta para una persona para 
'<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Solo para Ludmina 💖</title>

<style>

body{
    margin:0;
    background:black;
    font-family:'Georgia', serif;
    color:white;
    overflow:hidden;
    text-align:center;
}

/* PANTALLA BLOQUEO */
#lockScreen{
    position:absolute;
    width:100%;
    height:100vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    background:black;
}

input{
    padding:10px;
    border-radius:20px;
    border:none;
    margin-top:10px;
}

button{
    padding:10px 20px;
    border:none;
    border-radius:20px;
    margin-top:10px;
    background:#ff4da6;
    color:white;
    cursor:pointer;
}

/* CONTENIDO */
#content{
    display:none;
}

/* CARTA */
.letter{
    position:absolute;
    top:15%;
    width:90%;
    left:5%;
    font-size:20px;
    line-height:1.6;
    color:#ffd1dc;
    min-height:120px;
}

/* FOTOS */
.photos{
    position:absolute;
    bottom:25%;
    width:100%;
}

.photos img{
    width:90px;
    height:90px;
    border-radius:20px;
    margin:8px;
    box-shadow:0 0 20px #ff4da6;
    animation: float 3s ease-in-out infinite;
}

@keyframes float{
    0%{transform:translateY(0);}
    50%{transform:translateY(-10px);}
    100%{transform:translateY(0);}
}

/* MENSAJE FINAL */
.final{
    position:absolute;
    bottom:8%;
    width:100%;
    font-size:30px;
    color:#ff4da6;
    opacity:0;
    transition:2s;
}

/* ESTRELLAS */
.star{
    position:absolute;
    width:2px;
    height:2px;
    background:white;
    animation: twinkle 2s infinite alternate;
}

@keyframes twinkle{
    from{opacity:0.2;}
    to{opacity:1;}
}

/* CORAZONES */
.heart{
    position:absolute;
    color:#ff4da6;
    font-size:20px;
    animation: fall 5s linear infinite;
}

@keyframes fall{
    0%{transform:translateY(-10vh);}
    100%{transform:translateY(110vh);}
}

</style>
</head>

<body>

<div id="lockScreen">
    <h2>🔐 Solo Ludmina puede entrar</h2>
    <input type="password" id="password" placeholder="Ingresa la contraseña">
    <button onclick="checkPassword()">Entrar</button>
</div>

<div id="content">

    <div class="letter" id="letter"></div>

    <div class="photos">
        <img src="foto1.jpg">
        <img src="foto2.jpg">
        <img src="foto3.jpg">
    </div>

    <div class="final" id="finalMessage">
        ¿Quieres estar conmigo para siempre? ❤️
    </div>

    <audio autoplay loop>
        <source src="music.mp3" type="audio/mpeg">
    </audio>

</div>

<script>

const correctPassword = "01022026";

const text = "💍 ¿Te quedarías conmigo...?\n💖 ¿Seguirías eligiéndome cada día?\n🌹 ¿Me permites amarte siempre?";

function checkPassword(){
    const input = document.getElementById("password").value;

    if(input === correctPassword){
        document.getElementById("lockScreen").style.display = "none";
        document.getElementById("content").style.display = "block";

        typeWriter();
        createStars();
        createHearts();

        setTimeout(()=>{
            document.getElementById("finalMessage").style.opacity = "1";
        },6000);

    }else{
        alert("Contraseña incorrecta 💔");
    }
}

/* EFECTO MAQUINA DE ESCRIBIR */
function typeWriter(){
    let i = 0;
    const speed = 60;
    const letter = document.getElementById("letter");

    function typing(){
        if(i < text.length){
            letter.innerHTML += text.charAt(i) === "\n" ? "<br>" : text.charAt(i);
            i++;
            setTimeout(typing, speed);
        }
    }

    typing();
}

/* ESTRELLAS */
function createStars(){
    for(let i=0;i<80;i++){
        let star = document.createElement("div");
        star.className = "star";
        star.style.top = Math.random()*100 + "vh";
        star.style.left = Math.random()*100 + "vw";
        document.body.appendChild(star);
    }
}

/* CORAZONES */
function createHearts(){
    setInterval(()=>{
        let heart = document.createElement("div");
        heart.className = "heart";
        heart.innerHTML = "❤";
        heart.style.left = Math.random()*100 + "vw";
        document.body.appendChild(heart);

        setTimeout(()=>heart.remove(),5000);
    },500);
}

</script>

</body>
</html>'
'https://chevretromeo26-del.github.io/Romeo/'
