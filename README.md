<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Riya 💖</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;}

body{
  height:100vh;
  background:
    radial-gradient(circle at top, rgba(255,255,255,0.15), transparent 60%),
    linear-gradient(180deg,#0f0c29,#302b63,#24243e);
  overflow:hidden;
  display:flex;
  justify-content:center;
  align-items:center;
  font-family:'Georgia',serif;
  color:white;
  text-align:center;
}

body::after{
  content:"";
  position:absolute;
  inset:0;
  background:radial-gradient(circle, transparent 60%, rgba(0,0,0,0.7));
  pointer-events:none;
}

.container{
  z-index:2;
  max-width:420px;
  padding:20px;
  animation:cinematicFade 3s ease forwards;
}

h1{font-size:2.2rem;margin-bottom:8px;letter-spacing:1px;}

#typing{
  margin-top:15px;
  font-size:1.1rem;
  line-height:1.7;
  min-height:140px;
}

/* Teddy */
.teddy-wrap{
  position:relative;
  margin-top:30px;
  opacity:0;
  transform:translateY(40px);
  animation:teddyReveal 2.8s ease forwards;
  animation-delay:9s;
}

.teddy{font-size:96px;z-index:2;position:relative;}

.teddy-heart{
  position:absolute;
  font-size:42px;
  left:50%;
  top:60%;
  transform:translate(-50%,-50%);
  z-index:3;
  animation:heartBeat 1.6s infinite ease-in-out;
  filter:drop-shadow(0 0 12px rgba(255,60,100,0.8));
}

/* Ending */
.footer{
  margin-top:18px;
  font-size:0.95rem;
  opacity:0;
  animation:fadeIn 3s ease forwards;
  animation-delay:12s;
}

/* Hearts */
.heart{
  position:absolute;
  width:14px;
  height:14px;
  background:#ff4b7d;
  transform:rotate(45deg);
  animation:float linear infinite;
}

.heart::before,.heart::after{
  content:"";
  width:14px;
  height:14px;
  background:#ff4b7d;
  border-radius:50%;
  position:absolute;
}

.heart::before{top:-7px;}
.heart::after{left:-7px;}

/* Confetti */
.confetti{
  position:fixed;
  top:50%;
  left:50%;
  width:8px;
  height:14px;
  border-radius:2px;
  opacity:0.9;
  animation:confettiPhysics linear forwards;
}

/* Animations */
@keyframes float{
  from{transform:translateY(110vh) rotate(45deg);}
  to{transform:translateY(-10vh) rotate(45deg);}
}

@keyframes cinematicFade{
  from{opacity:0;transform:scale(1.05);}
  to{opacity:1;transform:scale(1);}
}

@keyframes teddyReveal{to{opacity:1;transform:translateY(0);}}
@keyframes fadeIn{to{opacity:1;}}

@keyframes heartBeat{
  0%,100%{transform:translate(-50%,-50%) scale(1);}
  50%{transform:translate(-50%,-50%) scale(1.15);}
}

@keyframes confettiPhysics{
  from{transform:translate(0,0) rotate(0deg);opacity:1;}
  to{transform:translate(var(--x),var(--y)) rotate(var(--r));opacity:0;}
}
</style>
</head>

<body>

<div class="container">
  <h1>Happy Valentine’s Day</h1>
  <h1>Riya 🌸</h1>

  <div id="typing"></div>

  <div class="teddy-wrap">
    <div class="teddy">🧸</div>
    <div class="teddy-heart">❤️</div>
  </div>

  <div class="footer">
    Some bonds are not explained…<br>
    they are simply felt 🤍<br><br>
    — Sahil 🐶❤️
  </div>
</div>

<script>
const textLines=[
  "Some people come into our lives quietly…",
  "and suddenly become our comfort 🤍",
  "",
  "Riya, you are that calm place for me.",
  "My smile. My strength.",
  "My forever person 🌸"
];

let line=0,char=0;
const typing=document.getElementById("typing");

function typeScene(){
  if(line<textLines.length){
    if(char<textLines[line].length){
      typing.innerHTML+=textLines[line][char++];
      setTimeout(typeScene,80);
    }else{
      typing.innerHTML+="<br>";
      char=0;line++;
      setTimeout(typeScene,600);
    }
  }else{confettiBlast();}
}
setTimeout(typeScene,1500);

function createHeart(){
  const h=document.createElement("div");
  h.className="heart";
  h.style.left=Math.random()*100+"vw";
  h.style.animationDuration=(Math.random()*5+5)+"s";
  h.style.opacity=Math.random();
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),10000);
}
setInterval(createHeart,400);

function confettiBlast(){
  const colors=["#ff4b7d","#ffd166","#9bf6ff","#c77dff","#ffd6e0","#ffffff"];
  for(let i=0;i<280;i++){
    const c=document.createElement("div");
    c.className="confetti";
    const size=Math.random()*6+6;
    c.style.width=size+"px";
    c.style.height=size*1.4+"px";
    c.style.background=colors[Math.floor(Math.random()*colors.length)];
    const a=Math.random()*Math.PI*2,d=Math.random()*700+300;
    c.style.setProperty("--x",Math.cos(a)*d+"px");
    c.style.setProperty("--y",Math.sin(a)*d+500+"px");
    c.style.setProperty("--r",(Math.random()*1440)+"deg");
    c.style.animationDuration=(Math.random()*2+3)+"s";
    document.body.appendChild(c);
    setTimeout(()=>c.remove(),5000);
  }
}
</script>

</body>
</html># Happy-Valentine-s-Day-
Html code
