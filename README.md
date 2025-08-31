# 5s-class-revisions
Revision site for 5S Class of 2025.  

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>5S CLASS OF 2025 REVISIONS</title>
<style>
body {
  margin:0;
  font-family: Arial, sans-serif;
  background: radial-gradient(ellipse at bottom, #0a0a0a 0%, #0d1b2a 100%);
  color: #fff;
  overflow-x: hidden;
  perspective: 800px;
  transition: background 0.5s;
}
.star,.planet,.satellite{position:absolute;border-radius:50%;opacity:0.8;}
.star{background:white;}
.planet{background:radial-gradient(circle at top left,#ffcc33,#ff6600);box-shadow:0 0 15px rgba(255,200,0,0.6);}
.satellite{width:15px;height:15px;background:gray;border-radius:3px;box-shadow:0 0 5px #ccc;}

header {background: rgba(0,0,0,0.7);padding:15px;text-align:center;z-index:100;position:relative;}
header h1 { margin:0; font-size:2em; }
nav { display:flex; flex-wrap:wrap; justify-content:center; gap:10px; background:rgba(0,0,0,0.6); padding:10px; z-index:100; position:relative; }
nav button { padding:8px 12px; border:none; border-radius:5px; background:#3498db; color:#fff; cursor:pointer; transition:0.3s; }
nav button:hover { background:#2980b9; }
.container { display:none; padding:20px; background: rgba(0,0,0,0.7); margin:20px; border-radius:10px; animation: fadeIn 0.8s ease-in-out; z-index:100; position:relative; }
.active { display:block; }
.card { background: rgba(255,255,255,0.1); padding:15px; margin:10px 0; border-radius:8px; }
.card a { color:#ffcc00; text-decoration:none; }
.like-btn { cursor:pointer; color: #ffcc00; margin-left: 10px; }
input, select, textarea { width:100%; padding:8px; margin:5px 0 10px 0; border-radius:5px; border:none; }
footer { text-align:center; padding:10px; background: rgba(0,0,0,0.7); margin-top:20px; z-index:100; position:relative; }
.star-rating span{cursor:pointer;font-size:20px;color:#555;margin-right:5px;}
.star-rating span.active{color:gold;}
@keyframes fadeIn { from {opacity:0;} to {opacity:1;} }
</style>
</head>
<body>

<header>
  <h1>📘 5S CLASS OF 2025 REVISIONS</h1>
  <p>Created by Owen</p>
</header>

<nav>
  <button onclick="showTab('subjects')">Subjects</button>
  <button onclick="showTab('tips')">Study Tips</button>
  <button onclick="showTab('uploads')">Upload Notes</button>
  <button onclick="showTab('links')">Useful Links</button>
  <button onclick="showTab('youtube')">YouTube Lessons</button>
  <button onclick="showTab('dashboard')">Dashboard</button>
  <button onclick="showTab('backgrounds')">Change Background</button>
</nav>

<!-- Subjects Menu -->
<div id="subjects" class="container active">
  <h2>📚 Subjects (BGCSE)</h2>
  <select id="subjectSelect" onchange="filterSubject()">
    <option value="All">All Subjects</option>
    <option value="Mathematics">Mathematics</option>
    <option value="Additional Mathematics">Additional Mathematics</option>
    <option value="Setswana">Setswana</option>
    <option value="Science">Science</option>
    <option value="English">English</option>
    <option value="Social Studies">Social Studies</option>
    <option value="ICT">ICT / Computer Studies</option>
    <option value="History">History</option>
    <option value="Geography">Geography</option>
    <option value="Religious Education">Religious Education</option>
    <option value="Accounting">Accounting</option>
    <option value="Statistics">Statistics</option>
    <option value="Agriculture">Agriculture</option>
  </select>
</div>

<!-- Study Tips -->
<div id="tips" class="container">
  <h2>💡 Share Study Tips</h2>
  <textarea id="tipInput" rows="3" placeholder="Write your study tip..."></textarea>
  <select id="tipSubject">
    <option value="Mathematics">Mathematics</option>
    <option value="Additional Mathematics">Additional Mathematics</option>
    <option value="Setswana">Setswana</option>
    <option value="Science">Science</option>
    <option value="English">English</option>
    <option value="Social Studies">Social Studies</option>
    <option value="ICT">ICT / Computer Studies</option>
    <option value="History">History</option>
    <option value="Geography">Geography</option>
    <option value="Religious Education">Religious Education</option>
    <option value="Accounting">Accounting</option>
    <option value="Statistics">Statistics</option>
    <option value="Agriculture">Agriculture</option>
  </select>
  <button onclick="addTip()">Post Tip</button>
  <div id="tipsList"></div>
</div>

<!-- Upload Notes -->
<div id="uploads" class="container">
  <h2>📤 Upload Notes (Images, Videos, Documents, YouTube)</h2>
  <input type="file" id="fileInput" accept="image/*,video/*,.pdf,.doc,.docx"><br>
  <input type="text" id="ytInput" placeholder="Paste YouTube video link"><br>
  <select id="uploadSubject">
    <option value="Mathematics">Mathematics</option>
    <option value="Additional Mathematics">Additional Mathematics</option>
    <option value="Setswana">Setswana</option>
    <option value="Science">Science</option>
    <option value="English">English</option>
    <option value="Social Studies">Social Studies</option>
    <option value="ICT">ICT / Computer Studies</option>
    <option value="History">History</option>
    <option value="Geography">Geography</option>
    <option value="Religious Education">Religious Education</option>
    <option value="Accounting">Accounting</option>
    <option value="Statistics">Statistics</option>
    <option value="Agriculture">Agriculture</option>
  </select>
  <button onclick="uploadContent()">Upload</button>
  <div id="uploadsList"></div>
</div>

<!-- Useful Links -->
<div id="links" class="container">
  <h2>🔗 Useful Links</h2>
  <ul>
    <li><a href="https://www.papacambridge.com" target="_blank">PapaCambridge</a></li>
    <li><a href="https://www.bec.co.bw" target="_blank">Botswana Examinations Council (BEC)</a></li>
    <li><a href="https://www.khanacademy.org" target="_blank">Khan Academy</a></li>
    <li><a href="https://www.coursera.org" target="_blank">Coursera</a></li>
  </ul>
</div>

<!-- YouTube Lessons -->
<div id="youtube" class="container">
  <h2>🎥 YouTube Lessons</h2>
  <input type="text" id="ytLinkInput" placeholder="Paste YouTube link">
  <button onclick="addYouTube()">Add Video</button>
  <div id="youtubeList"></div>
</div>

<!-- Dashboard -->
<div id="dashboard" class="container">
  <h2>📊 Dashboard - Top Content</h2>
  <div id="dashboardContent"></div>
</div>

<!-- Background Selector -->
<div id="backgrounds" class="container">
  <h2>🎨 Customize Background</h2>
  <select id="bgSelect" onchange="changeBackground()">
    <option value="space">Space (Default)</option>
    <option value="library">Library</option>
    <option value="students">Students Reading</option>
    <option value="galaxy">Galaxy</option>
  </select>
  <input type="file" id="bgUpload" accept="image/*" onchange="uploadBackground(this)">
</div>

<footer>
  <p>&copy; 2025 Owen | 5S CLASS OF 2025 REVISIONS</p>
</footer>

<script>
let tips=[], uploads=[], youtubeVideos=[], likedTips=new Set(), likedUploads=new Set();

/* Tabs */
function showTab(tabId){
  document.querySelectorAll('.container').forEach(c=>c.classList.remove('active'));
  document.getElementById(tabId).classList.add('active'); 
  if(tabId==='dashboard') updateDashboard();
}

/* Study Tips */
function addTip(){
  const text=document.getElementById('tipInput').value.trim(); 
  const subject=document.getElementById('tipSubject').value; 
  if(text==='') return; 
  tips.unshift({text,subject,likes:0,id:Date.now(),rating:0}); 
  document.getElementById('tipInput').value=''; 
  renderTips();
}
function renderTips(){
  const list=document.getElementById('tipsList'); list.innerHTML='';
  tips.forEach(t=>{
    const div=document.createElement('div'); div.className='card';
    div.innerHTML=`[${t.subject}] ${t.text} <br>👍 <span>${t.likes}</span> <span class="like-btn" onclick="likeTip(${t.id})">[Like]</span>
    <div class="star-rating">${[1,2,3,4,5].map(i=>`<span data-id="${t.id}" data-star="${i}" onclick="rateTip(event)">${i<=t.rating?'★':'☆'}</span>`).join('')}</div>`;
    list.appendChild(div);
  });
}
function likeTip(id){if(likedTips.has(id)) return; const tip=tips.find(t=>t.id===id); if(tip){tip.likes++; likedTips.add(id); renderTips();}}
function rateTip(e){const id=+e.target.dataset.id; const star=+e.target.dataset.star; const tip=tips.find(t=>t.id===id); if(tip){tip.rating=star; renderTips();}}

/* Upload Notes */
function uploadContent(){
  const file=document.getElementById('fileInput').files[0]; 
  const yt=document.getElementById('ytInput').value.trim(); 
  const subject=document.getElementById('uploadSubject').value; 
  if(!file && yt==='') return; 
  const upload={id:Date.now(),likes:0,subject,rating:0}; 
  if(file){
    const reader=new FileReader(); 
    reader.onload=function(e){
      const ext=file.name.split('.').pop().toLowerCase();
      if(file.type.startsWith("video/")) upload.type='video', upload.content=e.target.result;
      else if(file.type.startsWith("image/")) upload.type='image', upload.content=e.target.result;
      else if(ext==='pdf'||ext==='doc'||ext==='docx') upload.type='doc', upload.content=e.target.result, upload.filename=file.name;
      uploads.unshift(upload); renderUploads();
    }; 
    reader.readAsDataURL(file);
  } else if(yt!==''){upload.type='youtube'; upload.content=yt; uploads.unshift(upload); renderUploads();}
  document.getElementById('fileInput').value=''; document.getElementById('ytInput').value='';
}
function renderUploads(){
  const list=document.getElementById('uploadsList'); list.innerHTML='';
  uploads.forEach(u=>{
    const div=document.createElement('div'); div.className='card'; 
    let html=''; 
    if(u.type==='image') html=`<img src="${u.content}" width="300"><br>`; 
    else if(u.type==='video') html=`<video controls width="300"><source src="${u.content}"></video><br>`; 
    else if(u.type==='doc') html=`📄 <a href="${u.content}" download="${u.filename}">${u.filename}</a><br>`; 
    else if(u.type==='youtube') html=`<iframe width="300" height="200" src="${u.content.replace("watch?v=","embed/")}" frameborder="0" allowfullscreen></iframe><br>`; 
    html+=`👍 <span>${u.likes}</span> <span class="like-btn" onclick="likeUpload(${u.id})">[Like]</span>
    <div class="star-rating">${[1,2,3,4,5].map(i=>`<span data-id="${u.id}" data-star="${i}" onclick="rateUpload(event)">${i<=u.rating?'★':'☆'}</span>`).join('')}</div>`;
    div.innerHTML=html; list.appendChild(div);
  });
}
function likeUpload(id){if(likedUploads.has(id)) return; const u=uploads.find(x=>x.id===id); if(u){u.likes++; likedUploads.add(id); renderUploads();}}
function rateUpload(e){const id=+e.target.dataset.id; const star=+e.target.dataset.star; const u=uploads.find(t=>t.id===id); if(u){u.rating=star; renderUploads();}}

/* YouTube */
function addYouTube(){const link=document.getElementById('ytLinkInput').value.trim(); if(link==='') return; youtubeVideos.unshift(link); document.getElementById('ytLinkInput').value=''; renderYouTube();}
function renderYouTube(){const list=document.getElementById('youtubeList'); list.innerHTML=''; youtubeVideos.forEach(v=>{const div=document.createElement('div'); div.className='card'; div.innerHTML=`<iframe width="300" height="200" src="${v.replace("watch?v=","embed/")}" frameborder="0" allowfullscreen></iframe>`; list.appendChild(div);});}

/* Dashboard */
function updateDashboard(){
  const dash=document.getElementById('dashboardContent'); dash.innerHTML='';
  const topTips=[...tips].sort((a,b)=>b.likes-a.likes).slice(0,5);
  const topUploads=[...uploads].sort((a,b)=>b.likes-a.likes).slice(0,5);
  dash.innerHTML+='<h3>⭐ Top Tips</h3>'; 
  topTips.forEach(t=>dash.innerHTML+=`<div class="card">[${t.subject}] ${t.text} (👍 ${t.likes}) ★ ${t.rating}</div>`);
  dash.innerHTML+='<h3>⭐ Top Uploads</h3>'; 
  topUploads.forEach(u=>{
    let html=''; 
    if(u.type==='image') html=`<img src="${u.content}" width="200"><br>`; 
    else if(u.type==='video') html=`<video controls width="200"><source src="${u.content}"></video><br>`; 
    else if(u.type==='doc') html=`📄 <a href="${u.content}" download="${u.filename}">${u.filename}</a><br>`; 
    else if(u.type==='youtube') html=`<iframe width="200" height="150" src="${u.content.replace("watch?v=","embed/")}" frameborder="0" allowfullscreen></iframe><br>`; 
    html+=`(👍 ${u.likes}) ★ ${u.rating}`; dash.innerHTML+=`<div class="card">${html}</div>`;
  });
}

/* Filter subjects */
function filterSubject(){const sel=document.getElementById('subjectSelect').value; document.querySelectorAll('#tipsList .card').forEach(card=>{card.style.display = (sel==='All' || card.innerHTML.includes(`[${sel}]`)) ? 'block' : 'none';});}

/* Background Selector */
function changeBackground(){
  const theme=document.getElementById('bgSelect').value;
  const body=document.body;
  switch(theme){
    case 'space': body.style.background='radial-gradient(ellipse at bottom, #0a0a0a 0%, #0d1b2a 100%)'; break;
    case 'library': body.style.background='url(https://i.ibb.co/2kR1Z9v/library.jpg) center/cover no-repeat'; break;
    case 'students': body.style.background='url(https://i.ibb.co/2c2jGvX/students.jpg) center/cover no-repeat'; break;
    case 'galaxy': body.style.background='url(https://i.ibb.co/2tYk4X9/galaxy.jpg) center/cover no-repeat'; break;
  }
}
function uploadBackground(input){
  if(input.files && input.files[0]){
    const reader=new FileReader();
    reader.onload=function(e){document.body.style.background=`url(${e.target.result}) center/cover no-repeat`;};
    reader.readAsDataURL(input.files[0]);
  }
}

/* Animated Space Background */
const numStars=80, numPlanets=3, numSatellites=5;
for(let i=0;i<numStars;i++){const s=document.createElement('div'); s.className='star'; s.style.width=s.style.height=Math.random()*3+1+'px'; s.style.top=Math.random()*100+'%'; s.style.left=Math.random()*100+'%'; document.body.appendChild(s);}
for(let i=0;i<numPlanets;i++){const p=document.createElement('div'); p.className='planet'; p.style.width=p.style.height=(Math.random()*60+30)+'px'; p.style.top=Math.random()*80+'%'; p.style.left=Math.random()*80+'%'; document.body.appendChild(p);}
for(let i=0;i<numSatellites;i++){const sat=document.createElement('div'); sat.className='satellite'; sat.style.top=Math.random()*90+'%'; sat.style.left=Math.random()*90+'%'; document.body.appendChild(sat);}
document.addEventListener('mousemove', e=>{const x=e.clientX/window.innerWidth-0.5; const y=e.clientY/window.innerHeight-0.5; document.querySelectorAll('.star').forEach(s=>s.style.transform=`translate(${x*10}px,${y*10}px)`); document.querySelectorAll('.planet').forEach(p=>p.style.transform=`translate(${x*5}px,${y*5}px)`); document.querySelectorAll('.satellite').forEach(s=>s.style.transform=`translate(${x*8}px,${y*8}px)`);});
</script>

</body>
</html>
