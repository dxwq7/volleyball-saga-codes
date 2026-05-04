<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Volleyball Saga Hub</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap');

*{margin:0;padding:0;box-sizing:border-box;font-family:Inter,sans-serif;}

body{
background: radial-gradient(circle at top,#0b1224,#050816 60%);
color:#e2e8f0;
overflow-x:hidden;
}

#particles{
position:fixed;
inset:0;
z-index:-1;
}

/* sidebar */
.sidebar{
position:fixed;
left:0;
top:0;
width:270px;
height:100%;
padding:22px;
background:linear-gradient(180deg,#0f172a,#020617);
border-right:1px solid rgba(255,255,255,0.08);
}

.navItem{
padding:12px;
margin:10px 0;
border-radius:12px;
cursor:pointer;
background:rgba(255,255,255,0.03);
transition:0.2s;
}

.navItem:hover{
background:#3b82f6;
transform:scale(1.05);
}

/* profile */
.profileBar{
position:absolute;
bottom:20px;
left:50%;
transform:translateX(-50%);
width:85%;
padding:10px;
border-radius:14px;
display:flex;
align-items:center;
gap:10px;
cursor:pointer;
background:rgba(255,255,255,0.04);
border:1px solid rgba(255,255,255,0.1);
transition:0.2s;
}

.profileBar:hover{
transform:translateX(-50%) scale(1.05);
background:rgba(59,130,246,0.2);
}

.pfp{
width:38px;
height:38px;
border-radius:50%;
object-fit:cover;
background:#1f2937;
}

.username{font-weight:600;font-size:14px;}

/* main */
.main{
margin-left:290px;
padding:30px;
}

.page{display:none;}
.page.active{display:block;}

.card{
background:rgba(255,255,255,0.05);
padding:18px;
border-radius:14px;
margin-bottom:15px;
border:1px solid rgba(255,255,255,0.08);
backdrop-filter:blur(12px);
}

h1{font-size:38px;font-weight:800;}
h2{margin:18px 0;color:#93c5fd;}
p{line-height:1.6;color:#cbd5e1;}

/* codes */
.codes{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
gap:10px;
}

.codeBox{
background:rgba(255,255,255,0.06);
padding:10px;
border-radius:10px;
display:flex;
justify-content:space-between;
align-items:center;
transition:0.2s;
}

.codeBox:hover{
transform:scale(1.03);
background:rgba(59,130,246,0.25);
}

.copyBtn{
padding:4px 8px;
border:none;
border-radius:8px;
cursor:pointer;
background:linear-gradient(135deg,#3b82f6,#2563eb);
color:white;
font-size:12px;
font-weight:600;
letter-spacing:0.3px;
width:55px;
display:flex;
align-items:center;
justify-content:center;
transition:0.25s ease;
box-shadow:0 4px 12px rgba(59,130,246,0.25);
position:relative;
overflow:hidden;
}

/* hover effect */
.copyBtn:hover{
transform:translateY(-2px) scale(1.05);
box-shadow:0 8px 18px rgba(59,130,246,0.4);
background:linear-gradient(135deg,#60a5fa,#3b82f6);
}

/* click animation */
.copyBtn:active{
transform:scale(0.95);
box-shadow:0 3px 10px rgba(59,130,246,0.2);
}

/* subtle shine animation */
.copyBtn::after{
content:"";
position:absolute;
top:0;
left:-75%;
width:50%;
height:100%;
background:rgba(255,255,255,0.25);
transform:skewX(-20deg);
transition:0.4s;
}

.copyBtn:hover::after{
left:130%;
}

/* modal */
.modal{
position:fixed;
inset:0;
display:none;
justify-content:center;
align-items:center;
background:rgba(0,0,0,0.6);
backdrop-filter:blur(10px);
}

.modalBox{
width:340px;
background:#0b1224;
padding:18px;
border-radius:16px;
border:1px solid rgba(255,255,255,0.1);
}

input{
width:100%;
padding:10px;
margin:6px 0;
border-radius:10px;
border:none;
background:rgba(255,255,255,0.06);
color:white;
}

button{
width:100%;
padding:10px;
border:none;
border-radius:10px;
background:#3b82f6;
color:white;
cursor:pointer;
margin-top:6px;
}

.signOutBtn{background:#ef4444;}
.backBtn{background:#64748b;}

</style>
</head>

<body>

<canvas id="particles"></canvas>

<div class="sidebar">
<h2>🏐 VBS</h2>
<div class="navItem" onclick="show('home')">🏠 Home</div>
<div class="navItem" onclick="show('codes')">🎮 Codes</div>
<div class="navItem" onclick="show('updates')">📢 Updates</div>
<div id="profileArea"></div>
</div>

<div class="main">

<!-- HOME (UNCHANGED EXACT CONTENT) -->
<div id="home" class="page active">

<div class="card">
<h1>Volleyball Saga Hub</h1>
<p>A competitive volleyball experience built around precision timing, mechanical skill expression, and ranked progression systems inspired by high-level arena gameplay.</p>
</div>

<div class="card">
<h2>🎮 Core Gameplay Systems</h2>
<p>• Timing-based spike combat (perfect hits = bonus velocity)</p>
<p>• Directional serve control with aim prediction</p>
<p>• Blocking system based on reaction frames</p>
<p>• Momentum-based movement physics</p>
<p>• Team synergy mechanics (passes + setups matter)</p>
</div>

<div class="card">
<h2>⚡ Progression System</h2>
<p>Players evolve through matches by unlocking:</p>
<p>• Styles (change movement + attack behavior)</p>
<p>• Stats (jump height, speed, reaction time)</p>
<p>• Powers (burst abilities during rallies)</p>
<p>• Ranked tiers with seasonal resets</p>
</div>

<div class="card">
<h2>🏆 Competitive Structure</h2>
<p>• Ranked matchmaking (ELO-based system)</p>
<p>• Casual queue for practice</p>
<p>• Seasonal leaderboard resets</p>
<p>• Win streak bonuses and performance rewards</p>
</div>

<div class="card">
<h2>🔥 Gameplay Philosophy</h2>
<p>The game rewards mechanical skill over randomness — every spike, block, and pass is timing-based and skill-driven.</p>
</div>

</div>

<!-- CODES -->
<div id="codes" class="page">
<div class="card">
<h2>🔥 Active Codes</h2>

<div class="codes">
<div class="codeBox"><span>30K_VISITS</span><button class="copyBtn" onclick="copy('30K_VISITS')">Copy</button></div>
<div class="codeBox"><span>STATS</span><button class="copyBtn" onclick="copy('STATS')">Copy</button></div>
<div class="codeBox"><span>STYLES</span><button class="copyBtn" onclick="copy('STYLES')">Copy</button></div>
<div class="codeBox"><span>POWERS</span><button class="copyBtn" onclick="copy('POWERS')">Copy</button></div>
</div>
</div>

<div class="card">
<h2>❌ Expired Codes</h2>
<div class="codes">
<div class="codeBox"><span>1K_VISITS</span></div>
<div class="codeBox"><span>OG</span></div>
<div class="codeBox"><span>release</span></div>
</div>
</div>
</div>

<!-- UPDATES (UNCHANGED) -->
<div id="updates" class="page">
<div class="card">
<h2>📢 Development Update Log</h2>

<p><b>v1.00</b> — Initial release of Volleyball Saga Hub with basic UI and navigation system.</p>
<p><b>v1.01</b> — Full UI overhaul introducing modern glass design, improved sidebar layout, and hover interactions.</p>
<p><b>v1.02</b> — Core navigation system rebuilt to support multi-page structure (Home / Codes / Updates).</p>
<p><b>v1.03</b> — Account system introduced with persistent login using localStorage.</p>
<p><b>v1.04</b> — Profile system added with avatar support and dynamic sidebar identity switching.</p>
<p><b>v1.05</b> — UI responsiveness improvements and animation smoothing across all panels.</p>
<p><b>v1.06</b> — Code system expanded and categorized into active and expired groups.</p>
<p><b>v1.07</b> — Performance optimizations for particle background rendering.</p>
<p><b>v1.08</b> — Account persistence improvements and bug fixes for login state handling.</p>
<p><b>v1.09</b> — Sidebar profile integration completed.</p>

</div>
</div>

</div>

<!-- MODAL -->
<div class="modal" id="modal">
<div class="modalBox">

<h3>Account</h3>

<div id="mainMenu">
<button id="loginBtn" onclick="openLogin()">Sign In</button>
<button id="regBtn" onclick="openRegister()">Register</button>
<button id="logoutBtn" class="signOutBtn" onclick="askLogout()">Sign Out</button>
<button onclick="closeModal()">Close</button>
</div>

<div id="loginBox" style="display:none;">
<input id="lUser" placeholder="Username">
<input id="lPass" type="password" placeholder="Password">
<button onclick="login()">Login</button>
<button class="backBtn" onclick="back()">Back</button>
</div>

<div id="regBox" style="display:none;">
<input id="rUser" placeholder="Username">
<input id="rPass" type="password">
<input id="pfp" type="file">
<button onclick="register()">Create</button>
<button class="backBtn" onclick="back()">Back</button>
</div>

</div>
</div>

<script>

/* NAV */
function show(id){
document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"));
document.getElementById(id).classList.add("active");
}

/* MODAL */
const modal=document.getElementById("modal");

function openLogin(){
modal.style.display="flex";
document.getElementById("loginBox").style.display="block";
document.getElementById("regBox").style.display="none";
document.getElementById("mainMenu").style.display="none";
}

function openRegister(){
modal.style.display="flex";
document.getElementById("regBox").style.display="block";
document.getElementById("loginBox").style.display="none";
document.getElementById("mainMenu").style.display="none";
}

function back(){
document.getElementById("mainMenu").style.display="block";
document.getElementById("loginBox").style.display="none";
document.getElementById("regBox").style.display="none";
}

function closeModal(){modal.style.display="none";}

/* USERS */
let users=JSON.parse(localStorage.getItem("users")||"{}");
let current=localStorage.getItem("user");

/* PROFILE */
function updateProfile(){
let area=document.getElementById("profileArea");

let logged=current && users[current];

document.getElementById("loginBtn").style.display = logged ? "none":"block";
document.getElementById("regBtn").style.display = logged ? "none":"block";
document.getElementById("logoutBtn").style.display = logged ? "block":"none";

if(logged){
area.innerHTML=`
<div class="profileBar" onclick="modal.style.display='flex'">
<img class="pfp" src="${users[current].pfp||''}">
<div class="username">${current}</div>
</div>`;
}else{
area.innerHTML=`<div class="profileBar" onclick="modal.style.display='flex'">👤 Account</div>`;
}
}
updateProfile();

/* AUTH */
function register(){
let u=rUser.value;
let p=rPass.value;
let file=pfp.files[0];

let reader=new FileReader();
reader.onload=()=>{
users[u]={pass:p,pfp:reader.result};
localStorage.setItem("users",JSON.stringify(users));
}
if(file)reader.readAsDataURL(file);
else{
users[u]={pass:p,pfp:""};
localStorage.setItem("users",JSON.stringify(users));
}
back();
}

function login(){
let u=lUser.value;
let p=lPass.value;

if(users[u]&&users[u].pass===p){
current=u;
localStorage.setItem("user",u);
closeModal();
updateProfile();
}
}

/* LOGOUT CONFIRM */
function askLogout(){
if(confirm("Are you sure you want to log out?")){
localStorage.removeItem("user");
current=null;
updateProfile();
closeModal();
}
}

/* COPY */
function copy(t){
navigator.clipboard.writeText(t);
}

/* PARTICLES */
const c=document.getElementById("particles");
const ctx=c.getContext("2d");
c.width=innerWidth;
c.height=innerHeight;

let p=[];
for(let i=0;i<60;i++){
p.push({x:Math.random()*c.width,y:Math.random()*c.height,r:Math.random()*2});
}

function draw(){
ctx.clearRect(0,0,c.width,c.height);
ctx.fillStyle="rgba(255,255,255,0.4)";
p.forEach(o=>{
ctx.beginPath();
ctx.arc(o.x,o.y,o.r,0,Math.PI*2);
ctx.fill();
o.y-=0.4;
if(o.y<0)o.y=c.height;
});
}
setInterval(draw,30);

</script>

</body>
</html>
