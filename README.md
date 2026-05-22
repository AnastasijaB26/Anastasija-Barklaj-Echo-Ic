<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>The Infinite Echo</title>

<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;700&family=Cormorant+Garamond:wght@300;500;700&display=swap" rel="stylesheet">

<style>

/* ========================= */
/* RESET */
/* ========================= */

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

:root{

    --bg:#050816;
    --bg2:#0f1328;

    --text:#f4f4f4;

    --glass:rgba(255,255,255,.06);

    --accent:#7ef9ff;
    --purple:#9f7bff;
    --gold:#ffcc70;
}

body.light{

    --bg:#eef4ff;
    --bg2:#d8e5ff;

    --text:#111;

    --glass:rgba(255,255,255,.5);

    --accent:#005eff;
    --purple:#6b42ff;
    --gold:#ff9f1c;
}

body{

    background:
    radial-gradient(circle at top,var(--bg2),var(--bg));

    color:var(--text);

    font-family:'Space Grotesk',sans-serif;

    overflow-x:hidden;

    transition:1s;
}

/* ========================= */
/* STARS */
/* ========================= */

.stars{

    position:fixed;
    inset:0;

    overflow:hidden;

    z-index:-5;
}

.star{

    position:absolute;

    width:2px;
    height:2px;

    background:white;

    border-radius:50%;

    opacity:.4;

    animation:float linear infinite;
}

@keyframes float{

    from{
        transform:translateY(100vh);
    }

    to{
        transform:translateY(-100vh);
    }
}

/* ========================= */
/* INTERACTIVE BG */
/* ========================= */

.interactive-bg{

    position:fixed;
    inset:0;

    overflow:hidden;

    z-index:-4;
}

.energy{

    position:absolute;

    width:500px;
    height:500px;

    border-radius:50%;

    background:
    radial-gradient(circle,
    rgba(126,249,255,.13),
    transparent 70%);

    filter:blur(60px);

    pointer-events:none;

    transition:transform .15s linear;
}

/* ========================= */
/* GLOW */
/* ========================= */

.glow{

    position:fixed;

    width:300px;
    height:300px;

    border-radius:50%;

    background:
    radial-gradient(circle,
    rgba(126,249,255,.18),
    transparent 70%);

    pointer-events:none;

    transform:translate(-50%,-50%);

    z-index:-3;
}

/* ========================= */
/* NAV */
/* ========================= */

nav{

    position:fixed;

    top:20px;
    left:50%;

    transform:translateX(-50%);

    width:92%;
    max-width:1300px;

    padding:18px 28px;

    display:flex;
    justify-content:space-between;
    align-items:center;

    background:var(--glass);

    backdrop-filter:blur(18px);

    border:
    1px solid rgba(255,255,255,.08);

    border-radius:25px;

    z-index:999;
}

.logo{

    color:var(--accent);

    font-weight:700;

    letter-spacing:2px;

    font-size:1.3rem;
}

nav ul{

    display:flex;
    gap:25px;

    list-style:none;
}

nav a{

    text-decoration:none;

    color:var(--text);

    position:relative;
}

nav a::after{

    content:"";

    position:absolute;

    left:0;
    bottom:-5px;

    width:0%;
    height:2px;

    background:
    linear-gradient(to right,
    var(--accent),
    var(--purple));

    transition:.4s;
}

nav a:hover::after{

    width:100%;
}

.nav-buttons{

    display:flex;
    gap:12px;
}

.icon-btn{

    width:42px;
    height:42px;

    border:none;

    border-radius:50%;

    background:var(--glass);

    color:var(--text);

    cursor:pointer;

    transition:.4s;
}

.icon-btn:hover{

    transform:
    rotate(10deg)
    scale(1.1);
}

/* ========================= */
/* HERO */
/* ========================= */

.hero{

    min-height:100vh;

    display:flex;
    align-items:center;
    justify-content:center;

    text-align:center;

    position:relative;

    overflow:hidden;
}

.hero img{

    position:absolute;

    width:100%;
    height:100%;

    object-fit:cover;

    opacity:.14;
}

.hero-content{

    position:relative;

    z-index:5;

    max-width:900px;

    padding:20px;
}

.hero h1{

    font-size:clamp(4rem,8vw,8rem);

    line-height:.9;

    margin-bottom:25px;

    font-family:'Cormorant Garamond',serif;

    background:
    linear-gradient(to right,
    white,
    var(--accent));

    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;

    animation:floatText 6s ease infinite;
}

@keyframes floatText{

    0%,100%{
        transform:translateY(0);
    }

    50%{
        transform:translateY(-12px);
    }
}

.hero p{

    line-height:1.9;

    opacity:.8;

    margin-bottom:35px;

    font-size:1.1rem;
}

.hero button{

    padding:16px 36px;

    border:none;

    border-radius:40px;

    background:
    linear-gradient(135deg,
    var(--accent),
    var(--purple));

    color:#08111e;

    font-weight:700;

    cursor:pointer;

    transition:.4s;
}

.hero button:hover{

    transform:
    scale(1.08);
}

/* ========================= */
/* SECTIONS */
/* ========================= */

section{

    width:90%;
    max-width:1200px;

    margin:auto;

    padding:120px 0;
}

.section-title{

    font-size:3rem;

    color:var(--gold);

    margin-bottom:40px;

    font-family:'Cormorant Garamond',serif;
}

/* ========================= */
/* GLASS */
/* ========================= */

.glass{

    background:var(--glass);

    backdrop-filter:blur(18px);

    border:
    1px solid rgba(255,255,255,.08);

    border-radius:25px;

    padding:35px;

    transition:.5s;
}

.glass:hover{

    transform:
    translateY(-10px);
}

/* ========================= */
/* ABOUT */
/* ========================= */

.about-grid{

    display:grid;

    grid-template-columns:1fr 1fr;

    gap:30px;
}

/* ========================= */
/* GALLERY */
/* ========================= */

.gallery{

    display:grid;

    grid-template-columns:
    repeat(auto-fit,minmax(250px,1fr));

    gap:25px;
}

.card{

    position:relative;

    height:350px;

    border-radius:25px;

    overflow:hidden;

    cursor:pointer;

    transition:.6s;
}

.card:hover{

    transform:
    translateY(-10px)
    rotate(-1deg);
}

.card img{

    width:100%;
    height:100%;

    object-fit:cover;

    transition:1s;
}

.card:hover img{

    transform:scale(1.1);
}

.overlay{

    position:absolute;

    inset:0;

    background:
    linear-gradient(to top,
    rgba(0,0,0,.8),
    transparent);

    display:flex;
    flex-direction:column;
    justify-content:flex-end;

    padding:30px;

    opacity:0;

    transition:.6s;
}

.card:hover .overlay{

    opacity:1;
}

/* ========================= */
/* ORB */
/* ========================= */

.orb{

    width:320px;
    height:320px;

    margin:120px auto;

    border-radius:50%;

    position:relative;

    overflow:hidden;

    cursor:pointer;

    background:
    radial-gradient(circle at 30% 30%,
    rgba(255,255,255,.35),
    rgba(126,249,255,.15),
    rgba(159,123,255,.08),
    transparent 75%);

    backdrop-filter:blur(20px);

    border:
    1px solid rgba(255,255,255,.15);

    box-shadow:
    0 0 80px rgba(126,249,255,.15),
    inset 0 0 50px rgba(255,255,255,.08);

    display:flex;
    align-items:center;
    justify-content:center;

    text-align:center;

    padding:45px;

    line-height:1.5;

    font-size:1.45rem;

    font-family:'Cormorant Garamond',serif;

    animation:
    orbFloat 8s ease-in-out infinite;

    transition:1s;
}

.orb::before{

    content:"";

    position:absolute;

    inset:-25px;

    border-radius:50%;

    border:
    1px solid rgba(255,255,255,.1);

    animation:
    spin 25s linear infinite;
}

.orb::after{

    content:"";

    position:absolute;

    width:120%;
    height:120%;

    background:
    conic-gradient(
    transparent,
    rgba(126,249,255,.2),
    transparent,
    rgba(159,123,255,.2),
    transparent);

    animation:
    rotateGlow 10s linear infinite;

    opacity:.4;
}

.orb span{

    position:relative;

    z-index:5;
}

.orb:active{

    transform:scale(.95);
}

@keyframes orbFloat{

    0%,100%{

        transform:
        translateY(0)
        rotate(0deg);
    }

    50%{

        transform:
        translateY(-12px)
        rotate(1deg);
    }
}

@keyframes rotateGlow{

    from{
        transform:rotate(0deg);
    }

    to{
        transform:rotate(360deg);
    }
}

@keyframes spin{

    from{
        transform:rotate(0deg);
    }

    to{
        transform:rotate(360deg);
    }
}

/* ========================= */
/* CONTACT */
/* ========================= */

.contact-grid{

    display:grid;

    grid-template-columns:1fr 1fr;

    gap:30px;
}

input,
textarea{

    width:100%;

    background:
    rgba(255,255,255,.08);

    border:none;

    border-radius:15px;

    padding:18px;

    margin-bottom:18px;

    color:var(--text);

    font-size:1rem;

    outline:none;
}

textarea{

    min-height:150px;

    resize:none;
}

.send-btn{

    padding:15px 30px;

    border:none;

    border-radius:30px;

    background:
    linear-gradient(to right,
    var(--gold),
    var(--accent));

    color:#08111e;

    font-weight:700;

    cursor:pointer;
}

/* ========================= */
/* NOTES */
/* ========================= */

.note{

    margin-top:18px;

    background:
    rgba(255,255,255,.06);

    padding:18px;

    border-radius:18px;
}

.small-btn{

    margin-top:12px;

    padding:8px 14px;

    border:none;

    border-radius:20px;

    cursor:pointer;
}

/* ========================= */
/* SIDE PANEL */
/* ========================= */

.side-panel{

    position:fixed;

    top:50%;
    right:-420px;

    transform:translateY(-50%);

    width:420px;
    height:82vh;

    background:
    rgba(8,12,28,.92);

    backdrop-filter:blur(28px);

    border:
    1px solid rgba(255,255,255,.12);

    border-right:none;

    border-radius:
    30px 0 0 30px;

    box-shadow:
    -20px 0 60px rgba(0,0,0,.4),
    0 0 80px rgba(126,249,255,.08);

    transition:.9s cubic-bezier(.19,1,.22,1);

    z-index:998;
}

.side-panel.active{

    right:0;
}

.panel-toggle{

    position:absolute;

    left:-70px;
    top:45px;

    width:70px;
    height:70px;

    border-radius:
    24px 0 0 24px;

    background:
    linear-gradient(
    135deg,
    var(--accent),
    var(--purple));

    display:flex;
    align-items:center;
    justify-content:center;

    cursor:pointer;

    font-size:1.7rem;

    color:#08111e;
}

.panel-content{

    padding:45px 35px;

    overflow-y:auto;

    height:100%;
}

.panel-content h2{

    margin-bottom:35px;

    color:var(--accent);

    font-size:2.6rem;

    font-family:'Cormorant Garamond',serif;
}

.panel-slide{

    display:none;

    animation:fadeSlide .7s ease;
}

.panel-slide.active{

    display:block;
}

@keyframes fadeSlide{

    from{

        opacity:0;
        transform:translateX(20px);
    }

    to{

        opacity:1;
        transform:translateX(0);
    }
}

.thought-card{

    padding:22px;

    border-radius:22px;

    background:
    rgba(255,255,255,.08);

    margin-bottom:22px;

    line-height:2;

    font-size:1rem;

    border:
    1px solid rgba(255,255,255,.06);

    transition:.5s;
}

.thought-card:hover{

    transform:
    translateX(-8px)
    scale(1.02);

    background:
    rgba(255,255,255,.12);

    border:
    1px solid rgba(126,249,255,.2);
}

.slide-controls{

    display:flex;

    justify-content:center;

    gap:18px;

    margin-top:35px;
}

.slide-controls button{

    width:52px;
    height:52px;

    border:none;

    border-radius:50%;

    cursor:pointer;

    background:
    linear-gradient(
    135deg,
    var(--accent),
    var(--purple));

    color:#08111e;

    font-size:1.2rem;

    font-weight:bold;
}

/* ========================= */
/* FOOTER */
/* ========================= */

footer{

    text-align:center;

    opacity:.5;

    padding:50px 20px;
}

/* ========================= */
/* MOBILE */
/* ========================= */

@media(max-width:900px){

    .about-grid,
    .contact-grid{

        grid-template-columns:1fr;
    }

    nav ul{

        display:none;
    }

    .side-panel{

        display:none;
    }
}

</style>
</head>

<body>

<div class="stars"></div>
<div class="interactive-bg"></div>
<div class="glow"></div>

<audio id="bgMusic" loop>
<source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_c8c8a73467.mp3?filename=deep-ambient-11157.mp3">
</audio>

<!-- SIDE PANEL -->

<div class="side-panel" id="sidePanel">

<div class="panel-toggle" onclick="togglePanel()">
✦
</div>

<div class="panel-content">

<h2>Cosmic Notes</h2>

<div class="panel-slide active">

<div class="thought-card">
You are seeing the world around 80 milliseconds in the past.
</div>

<div class="thought-card">
Most of the universe is invisible dark matter and dark energy.
</div>

<div class="thought-card">
Your brain predicts reality before experiencing it.
</div>

</div>

<div class="panel-slide">

<div class="thought-card">
The atoms inside your body were born in exploding stars.
</div>

<div class="thought-card">
Every person you meet exists in a different inner universe.
</div>

<div class="thought-card">
Silence changes how humans perceive time.
</div>

</div>

<div class="panel-slide">

<div class="thought-card">
Consciousness still has no complete explanation.
</div>

<div class="thought-card">
Your memories slightly change every time you remember them.
</div>

<div class="thought-card">
Reality might only exist because something observes it.
</div>

</div>

<div class="slide-controls">

<button onclick="prevSlide()">←</button>
<button onclick="nextSlide()">→</button>

</div>

</div>

</div>

<!-- NAV -->

<nav>

<div class="logo">
∞ ECHO
</div>

<ul>

<li><a href="#about">About</a></li>
<li><a href="#gallery">Gallery</a></li>
<li><a href="#contact">Contact</a></li>

</ul>

<div class="nav-buttons">

<button class="icon-btn" onclick="toggleTheme()">
☀
</button>

<button class="icon-btn" onclick="toggleMusic()">
♫
</button>

</div>

</nav>

<!-- HERO -->

<header class="hero">

<img src="https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?q=80&w=2070&auto=format&fit=crop">

<div class="hero-content">

<h1>The Infinite Echo</h1>

<p>
An interactive philosophical experience exploring reality,
consciousness, time, and perception.
</p>

<button onclick="scrollToSection()">
ENTER EXISTENCE
</button>

</div>

</header>

<!-- ABOUT -->

<section id="about">

<h2 class="section-title">
About
</h2>

<div class="about-grid">

<div class="glass">

<p style="line-height:2">
Reality might not be objective —
your brain constantly edits and reconstructs the world.
</p>

</div>

<div class="glass">

<p style="line-height:2">
This website behaves like a living thought:
reactive, flowing, unstable, alive.
</p>

</div>

</div>

</section>

<!-- GALLERY -->

<section id="gallery">

<h2 class="section-title">
Fragments Of Reality
</h2>

<div class="gallery">

<div class="card">

<img src="https://images.unsplash.com/photo-1519681393784-d120267933ba?q=80&w=2070">

<div class="overlay">

<h3>Existence</h3>

<p>
You are the universe experiencing itself.
</p>

</div>

</div>

<div class="card">

<img src="https://images.unsplash.com/photo-1493246507139-91e8fad9978e?q=80&w=2070">

<div class="overlay">

<h3>Identity</h3>

<p>
Memory constantly rewrites who you are.
</p>

</div>

</div>

<div class="card">

<img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?q=80&w=2070">

<div class="overlay">

<h3>Time</h3>

<p>
The present moment may be all that exists.
</p>

</div>

</div>

<div class="card">

<img src="https://images.unsplash.com/photo-1500534623283-312aade485b7?q=80&w=2070">

<div class="overlay">

<h3>Silence</h3>

<p>
Silence is where thought hears itself.
</p>

</div>

</div>

</div>


<div class="orb-container">

    <!-- LEFT ORB -->

    <div class="mini-orb" id="leftOrb">

        <span>
           <center> Memory creates identity.</center>
        </span>

    </div>

    <!-- CENTER ORB -->

    <div class="orb" id="factOrb">

        <span>
            Click me
        </span>

    </div>

    <!-- RIGHT ORB -->

    <div class="mini-orb" id="rightOrb">

        <span>
           <center> Time only exists in perception.</center>
        </span>

    </div>

</div>

</section>

<!-- CONTACT -->

<section id="contact">

<h2 class="section-title">
Mind Transmission
</h2>

<div class="contact-grid">

<div class="glass">

<input type="text" id="name" placeholder="Your name">

<input type="email" placeholder="Your email">

<textarea id="message" placeholder="Write your thoughts..."></textarea>

<button class="send-btn" onclick="saveMessage()">
Save Thought
</button>

<p style="
margin-top:20px;
opacity:.7;
line-height:1.8;
font-size:.95rem;
">
Perhaps one day, we will read your thoughts.
</p>

<div id="journal"></div>

</div>

<div class="glass">

<h3 style="
margin-bottom:20px;
color:var(--accent);
font-size:2rem;
font-family:'Cormorant Garamond',serif;
">
Contact
</h3>

<p style="
line-height:2.1;
opacity:.85;
font-size:1rem;
">

✦ contact@infiniteecho.com<br>
✦ philosophy@voidrealm.net<br>
✦ +00 999 333 777<br>
✦ Somewhere between dreams and reality

</p>

</div>

</div>

</section>

<footer>

The Infinite Echo © 2026

</footer>

<script>

/* SCROLL */

function scrollToSection(){

document.getElementById("about")
.scrollIntoView({behavior:"smooth"});

}

/* STARS */

const stars =
document.querySelector('.stars');

for(let i=0;i<120;i++){

const star =
document.createElement('div');

star.classList.add('star');

star.style.left =
Math.random()*100 + 'vw';

star.style.top =
Math.random()*100 + 'vh';

star.style.animationDuration =
20 + Math.random()*60 + 's';

stars.appendChild(star);

}

/* INTERACTIVE BG */

const bg =
document.querySelector('.interactive-bg');

for(let i=0;i<6;i++){

const energy =
document.createElement('div');

energy.classList.add('energy');

energy.style.left =
Math.random()*100 + 'vw';

energy.style.top =
Math.random()*100 + 'vh';

bg.appendChild(energy);

}

const energies =
document.querySelectorAll('.energy');

document.addEventListener('mousemove',(e)=>{

energies.forEach((energy,index)=>{

const speed =
(index + 1) * 0.015;

const x =
(window.innerWidth/2 - e.clientX) * speed;

const y =
(window.innerHeight/2 - e.clientY) * speed;

energy.style.transform =
`translate(${x}px,${y}px)`;

});

});

/* GLOW */

const glow =
document.querySelector('.glow');

document.addEventListener('mousemove',(e)=>{

glow.style.left =
e.clientX + 'px';

glow.style.top =
e.clientY + 'px';

});

/* ORB */

const orbFacts = [

"Your body replaces most atoms over time.",

"Stars created the atoms inside your body.",

"You are experiencing delayed reality.",

"Memory constantly rewrites itself.",

"The universe may have no true center.",

"Consciousness still has no explanation.",

"Most reality is invisible dark matter.",

"Your brain predicts reality before seeing it."

];

const orb =
document.getElementById('factOrb');

let currentFact = 0;

orb.addEventListener('click',()=>{

orb.style.opacity = .2;

orb.style.transform =
"scale(.92) rotate(6deg)";

setTimeout(()=>{

currentFact++;

if(currentFact >= orbFacts.length){

currentFact = 0;
}

orb.innerHTML =
`<span>${orbFacts[currentFact]}</span>`;

orb.style.opacity = 1;

orb.style.transform =
"scale(1) rotate(0deg)";

},350);

});

/* THEME */

function toggleTheme(){

document.body.classList.toggle('light');

}

/* MUSIC */

const music =
document.getElementById('bgMusic');

let playing = false;

function toggleMusic(){

if(!playing){

music.play();
playing = true;

}else{

music.pause();
playing = false;

}

}

/* NOTES */

let deletedNote = null;

function saveMessage(){

const name =
document.getElementById('name').value;

const text =
document.getElementById('message').value;

if(text.trim() === "") return;

const note =
document.createElement('div');

note.className = 'note';

note.innerHTML = `

<strong>${name || "Anonymous"}</strong>

<p style="margin-top:10px;line-height:1.7">
${text}
</p>

<button class="small-btn"
onclick="deleteNote(this)">
Delete
</button>

`;

document.getElementById('journal')
.prepend(note);

document.getElementById('message').value = "";

}

/* DELETE */

function deleteNote(btn){

deletedNote =
btn.parentElement;

deletedNote.remove();

showRestore();

}

/* RESTORE */

function showRestore(){

const existing =
document.getElementById('restoreBtn');

if(existing) existing.remove();

const restore =
document.createElement('button');

restore.id = 'restoreBtn';

restore.innerText =
'Restore Deleted Thought';

restore.className = 'send-btn';

restore.style.marginTop = '20px';

restore.onclick = ()=>{

if(deletedNote){

document.getElementById('journal')
.prepend(deletedNote);

deletedNote = null;

restore.remove();

}

};

document.getElementById('journal')
.prepend(restore);

}

/* PANEL */

function togglePanel(){

document
.getElementById('sidePanel')
.classList
.toggle('active');

}

/* SLIDES */

const slides =
document.querySelectorAll('.panel-slide');

let currentSlide = 0;

function showSlide(index){

slides.forEach(slide=>{

slide.classList.remove('active');

});

slides[index].classList.add('active');
}

function nextSlide(){

currentSlide++;

if(currentSlide >= slides.length){

currentSlide = 0;
}

showSlide(currentSlide);
}

function prevSlide(){

currentSlide--;

if(currentSlide < 0){

currentSlide = slides.length - 1;
}

showSlide(currentSlide);
}

</script>

</body>
</html>
