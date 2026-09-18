<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>Kaye Liguey</title>

<style>
*{box-sizing:border-box;margin:0;padding:0;font-family:Arial,sans-serif}
body{background:#f4f7fb;color:#172033}
header{background:#0b63ce;color:white;padding:15px;display:flex;justify-content:space-between;align-items:center;gap:10px;flex-wrap:wrap}
.logo{font-size:23px;font-weight:bold}
nav{display:flex;gap:7px;flex-wrap:wrap}
nav button{border:0;background:white;color:#0b63ce;padding:9px 12px;border-radius:8px;cursor:pointer;font-weight:bold}
main{max-width:1000px;margin:auto;padding:20px}
.page{display:none}.page.active{display:block}
.card{background:white;padding:20px;margin-bottom:18px;border-radius:14px;box-shadow:0 3px 12px rgba(0,0,0,.08)}
.hero{text-align:center;padding:40px 20px}
.hero h1{font-size:34px;color:#0b63ce;margin-bottom:10px}
.hero p{color:#667085;margin-bottom:25px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:15px}
.btn{border:0;padding:12px 16px;border-radius:9px;cursor:pointer;font-weight:bold;margin:4px}
.blue{background:#0b63ce;color:white}.green{background:#16a34a;color:white}
.red{background:#dc2626;color:white}.gray{background:#e5e7eb;color:#172033}
input,textarea{width:100%;padding:12px;margin:7px 0 13px;border:1px solid #ccd3df;border-radius:8px;font-size:16px}
label{font-weight:bold}h2{margin-bottom:18px}h3{margin-bottom:8px}
.info{line-height:1.8}
.badge{display:inline-block;padding:5px 9px;border-radius:20px;background:#e8f1ff;color:#0b63ce;font-size:13px;margin:3px}
.empty{text-align:center;padding:25px;color:#777}
</style>
</head>

<body>

<header>
<div class="logo">💼 Kaye Liguey</div>
<nav id="nav"></nav>
</header>

<main>

<section id="home" class="page">
<div id="homeContent"></div>
</section>

<section id="candidateRegister" class="page">
<div class="card">
<h2>👤 Créer un compte candidat</h2>

<label>Nom complet</label>
<input id="candidateName" type="text" placeholder="Votre nom complet">

<label>Email</label>
<input id="candidateEmail" type="email" placeholder="Votre email">

<label>Téléphone</label>
<input id="candidatePhone" type="tel" placeholder="Votre numéro">

<label>Mot de passe</label>
<input id="candidatePassword" type="password" placeholder="Votre mot de passe">

<button class="btn blue" type="button" onclick="registerCandidate()">Créer mon compte</button>
<button class="btn gray" type="button" onclick="showPage('login')">J'ai déjà un compte</button>
</div>
</section>

<section id="companyRegister" class="page">
<div class="card">
<h2>🏢 Créer un compte entreprise</h2>

<label>Nom de l'entreprise</label>
<input id="companyName" type="text" placeholder="Nom de votre entreprise">

<label>Email</label>
<input id="companyEmail" type="email" placeholder="Email de l'entreprise">

<label>Téléphone</label>
<input id="companyPhone" type="tel" placeholder="Numéro de téléphone">

<label>Adresse</label>
<input id="companyAddress" type="text" placeholder="Adresse">

<label>Mot de passe</label>
<input id="companyPassword" type="password" placeholder="Votre mot de passe">

<button class="btn blue" type="button" onclick="registerCompany()">Créer mon compte</button>
<button class="btn gray" type="button" onclick="showPage('login')">J'ai déjà un compte</button>
</div>
</section>

<section id="login" class="page">
<div class="card">
<h2>🔐 Se connecter</h2>

<label>Email</label>
<input id="loginEmail" type="email" placeholder="Votre email">

<label>Mot de passe</label>
<input id="loginPassword" type="password" placeholder="Votre mot de passe">

<button class="btn blue" type="button" onclick="login()">Se connecter</button>
<button class="btn gray" type="button" onclick="showPage('candidateRegister')">Créer un compte candidat</button>
<button class="btn gray" type="button" onclick="showPage('companyRegister')">Créer un compte entreprise</button>
</div>
</section>

<section id="candidateDashboard" class="page">
<h2>👤 Mon espace candidat</h2>
<div id="candidateDashboardContent"></div>
</section>

<section id="jobs" class="page">
<h2>💼 Offres d'emploi</h2>
<div id="jobsList"></div>
</section>

<section id="favorites" class="page">
<h2>⭐ Mes favoris</h2>
<div id="favoritesList"></div>
</section>

<section id="applications" class="page">
<h2>📄 Mes candidatures</h2>
<div id="applicationsList"></div>
</section>

<section id="messages" class="page">
<h2>💬 Mes messages</h2>
<div id="msgList"></div>
</section>

<section id="profile" class="page">
<h2>👤 Mon profil</h2>
<div id="profileContent"></div>
</section>

<section id="companyDashboard" class="page">
<h2>🏢 Mon espace entreprise</h2>
<div id="companyDashboardContent"></div>
</section>

<section id="publishJob" class="page">
<div class="card">
<h2>➕ Publier une offre</h2>

<label>Titre du poste</label>
<input id="jobTitle" type="text" placeholder="Ex : Développeur web">

<label>Description</label>
<textarea id="jobDescription" rows="5" placeholder="Décrivez le poste"></textarea>

<label>Lieu</label>
<input id="jobLocation" type="text" placeholder="Ex : Dakar">

<label>Salaire</label>
<input id="jobSalary" type="text" placeholder="Ex : 150 000 FCFA">

<button class="btn blue" type="button" onclick="publishJob()">Publier l'offre</button>
</div>
</section>

<section id="myJobs" class="page">
<h2>📋 Mes offres</h2>
<div id="myJobsList"></div>
</section>

<section id="companyApplications" class="page">
<h2>👥 Mes candidats</h2>
<div id="companyApplicationsList"></div>
</section>

<section id="companyMessages" class="page">
<h2>💬 Messages avec mes candidats</h2>
<div id="companyMsgList"></div>
</section>

<section id="companyProfile" class="page">
<h2>🏢 Mon entreprise</h2>
<div id="companyProfileContent"></div>
</section>

</main>

<script>

const KEY={
 users:"kl_users",
 jobs:"kl_jobs",
 apps:"kl_apps",
 favs:"kl_favs",
 msgs:"kl_msgs",
 me:"kl_me"
};

function getData(key){
 try{
  return JSON.parse(localStorage.getItem(key))||[];
 }catch(e){
  return [];
 }
}

function saveData(key,data){
 localStorage.setItem(key,JSON.stringify(data));
}

function getMe(){
 try{
  return JSON.parse(localStorage.getItem(KEY.me));
 }catch(e){
  return null;
 }
}

function setMe(user){
 localStorage.setItem(KEY.me,JSON.stringify(user));
}

function uid(){
 return Date.now().toString(36)+Math.random().toString(36).slice(2);
}

function escapeHTML(text){
 return String(text??"")
 .replace(/&/g,"&amp;")
 .replace(/</g,"&lt;")
 .replace(/>/g,"&gt;")
 .replace(/"/g,"&quot;")
 .replace(/'/g,"&#039;");
}


/* =========================
   NAVIGATION
========================= */

function updateNav(){

 const nav=document.getElementById("nav");
 const me=getMe();

 if(!me){

  nav.innerHTML=`
   <button onclick="showPage('home')">🏠 Accueil</button>
   <button onclick="showPage('jobs')">💼 Jobs</button>
   <button onclick="showPage('candidateRegister')">👤 Candidat</button>
   <button onclick="showPage('companyRegister')">🏢 Entreprise</button>
   <button onclick="showPage('login')">🔐 Connexion</button>
  `;

  return;
 }

 if(me.role==="candidate"){

  nav.innerHTML=`
   <button onclick="showPage('home')">🏠 Accueil</button>
   <button onclick="showPage('jobs')">💼 Jobs</button>
   <button onclick="showPage('applications')">📄 Candidatures</button>
   <button onclick="showPage('favorites')">⭐ Favoris</button>
   <button onclick="showPage('messages')">💬 Messages</button>
   <button onclick="showPage('profile')">👤 Profil</button>
   <button onclick="logout()">🚪 Déconnexion</button>
  `;

 }else{

  nav.innerHTML=`
   <button onclick="showPage('home')">🏠 Accueil</button>
   <button onclick="showPage('myJobs')">📋 Mes offres</button>
   <button onclick="showPage('publishJob')">➕ Publier</button>
   <button onclick="showPage('companyApplications')">👥 Mes candidats</button>
   <button onclick="showPage('companyMessages')">💬 Messages</button>
   <button onclick="showPage('companyProfile')">🏢 Mon entreprise</button>
   <button onclick="logout()">🚪 Déconnexion</button>
  `;
 }
}


/* =========================
   AFFICHER UNE PAGE
========================= */

function showPage(id){

 const me=getMe();

 if(
  me &&
  (
   id==="candidateRegister"||
   id==="companyRegister"||
   id==="login"
  )
 ){
  id="home";
 }

 document.querySelectorAll(".page").forEach(p=>{
  p.classList.remove("active");
 });

 const page=document.getElementById(id);

 if(!page)return;

 page.classList.add("active");

 updateNav();

 if(id==="home")renderHome();
 if(id==="jobs")renderJobs();
 if(id==="favorites")renderFavorites();
 if(id==="applications")renderApplications();
 if(id==="messages")renderMsgs();
 if(id==="profile")renderProfile();
 if(id==="candidateDashboard")renderCandidateDashboard();
 if(id==="companyDashboard")renderCompanyDashboard();
 if(id==="publishJob"){}
 if(id==="myJobs")renderMyJobs();
 if(id==="companyApplications")renderCompanyApplications();
 if(id==="companyMessages")renderCompanyMessages();
 if(id==="companyProfile")renderCompanyProfile();
}


/* =========================
   ACCUEIL
========================= */

function renderHome(){

 const box=document.getElementById("homeContent");
 const me=getMe();

 /* PERSONNE CONNECTÉE */

 if(!me){

  box.innerHTML=`

   <div class="card hero">

    <h1>Bienvenue sur Kaye Liguey</h1>

    <p>
     La plateforme qui met en relation
     les candidats et les entreprises.
    </p>

    <button class="btn blue"
     onclick="showPage('candidateRegister')">
     👤 Créer un compte candidat
    </button>

    <button class="btn green"
     onclick="showPage('companyRegister')">
     🏢 Créer un compte entreprise
    </button>

    <button class="btn gray"
     onclick="showPage('login')">
     🔐 Se connecter
    </button>

   </div>

   <div class="card">

    <h2>💼 Les offres</h2>

    <p>
     Consultez les offres disponibles.
    </p>

    <button class="btn blue"
     onclick="showPage('jobs')">
     Voir les offres
    </button>

   </div>
  `;

  return;
 }


 /* =========================
    ACCUEIL CANDIDAT
    LE CANDIDAT VOIT TOUTES
    LES ENTREPRISES
 ========================= */

 if(me.role==="candidate"){

  const users=getData(KEY.users);
  const jobs=getData(KEY.jobs);

  const companies=users.filter(
   u=>u.role==="company"
  );

  let html=`

   <div class="card">

    <h2>Bonjour ${escapeHTML(me.name)} 👋</h2>

    <p class="info">
     👤 ${escapeHTML(me.name)}<br>
     📧 ${escapeHTML(me.email)}<br>
     📞 ${escapeHTML(me.phone)}
    </p>

   </div>

   <h2>🏢 Toutes les entreprises</h2>
  `;


  if(!companies.length){

   html+=`
    <div class="card empty">
     Aucune entreprise inscrite pour le moment.
    </div>
   `;

  }else{

   companies.forEach(company=>{

    const offers=jobs.filter(
     j=>j.companyId===company.id
    );

    html+=`

     <div class="card">

      <h3>
       🏢 ${escapeHTML(company.name)}
      </h3>

      <p class="info">
       📧 ${escapeHTML(company.email)}<br>
       📞 ${escapeHTML(company.phone||"Non renseigné")}<br>
       📍 ${escapeHTML(company.address||"Non renseignée")}
      </p>

      <h4 style="margin-top:12px">
       💼 Offres de cette entreprise
      </h4>
    `;


    if(!offers.length){

     html+=`
      <p class="empty">
       Cette entreprise n'a pas encore publié d'offre.
      </p>
     `;

    }else{

     offers.forEach(job=>{

      html+=`

       <div class="job"
        style="border:1px solid #e1e6ef;
        padding:15px;
        border-radius:12px;
        margin-top:10px">

        <h3>${escapeHTML(job.title)}</h3>

        <p>
         ${escapeHTML(job.description)}
        </p>

        <p>
         📍 ${escapeHTML(job.location)}
        </p>

        <p>
         💰 ${escapeHTML(job.salary||"Non précisé")}
        </p>

        <button class="btn blue"
         onclick="applyJob('${job.id}')">
         📩 Postuler
        </button>

        <button class="btn gray"
         onclick="toggleFavorite('${job.id}')">
         ⭐ Favori
        </button>

       </div>
      `;
     });
    }

    html+=`</div>`;
   });
  }

  box.innerHTML=html;

  return;
 }


 /* =========================
    ACCUEIL ENTREPRISE
    L'ENTREPRISE VOIT
    UNIQUEMENT ELLE-MÊME
 ========================= */

 if(me.role==="company"){

  renderCompanyHome(box,me);

 }
}


/* =========================
   ACCUEIL PRIVÉ ENTREPRISE
========================= */

function renderCompanyHome(box,me){

 /*
  IMPORTANT :

  On utilise UNIQUEMENT me.id.

  Donc Paul & Frères ne voit
  jamais les autres entreprises.
 */

 const jobs=getData(KEY.jobs)
  .filter(j=>j.companyId===me.id);

 const apps=getData(KEY.apps)
  .filter(a=>a.companyId===me.id);

 const users=getData(KEY.users);


 let html=`

  <div class="card">

   <h2>🏢 ${escapeHTML(me.name)}</h2>

   <p class="info">
    📧 ${escapeHTML(me.email)}<br>
    📞 ${escapeHTML(me.phone)}<br>
    📍 ${escapeHTML(me.address||"Non renseignée")}
   </p>

   <p style="margin-top:15px">
    🔒 Vous êtes connecté uniquement à votre espace entreprise.
   </p>

  </div>

  <div class="grid">

   <div class="card">
    <h3>💼 Mes offres</h3>
    <p>${jobs.length}</p>
   </div>

   <div class="card">
    <h3>👥 Mes candidats</h3>
    <p>${apps.length}</p>
   </div>

  </div>

  <div class="card">

   <h2>👥 Candidats de ${escapeHTML(me.name)}</h2>
 `;


 if(!apps.length){

  html+=`
   <div class="empty">
    Aucun candidat n'a encore postulé à vos offres.
   </div>
  `;

 }else{

  apps.forEach(app=>{

   const candidate=users.find(
    u=>u.id===app.candidateId
   );

   const job=jobs.find(
    j=>j.id===app.jobId
   );

   if(!candidate||!job)return;

   html+=`

    <div style="
     border:1px solid #e1e6ef;
     padding:15px;
     border-radius:12px;
     margin-bottom:10px">

     <h3>
      👤 ${escapeHTML(candidate.name)}
     </h3>

     <p>
      📄 Offre :
      <strong>${escapeHTML(job.title)}</strong>
     </p>

     <p>
      📧 ${escapeHTML(candidate.email)}
     </p>

     <p>
      📞 ${escapeHTML(candidate.phone)}
     </p>

     <span class="badge">
      ${escapeHTML(app.status||"En attente")}
     </span>

    </div>
   `;
  });
 }

 html+=`</div>`;

 box.innerHTML=html;
}


/* =========================
   INSCRIPTION CANDIDAT
========================= */

function registerCandidate(){

 const name=document.getElementById("candidateName").value.trim();
 const email=document.getElementById("candidateEmail").value.trim();
 const phone=document.getElementById("candidatePhone").value.trim();
 const password=document.getElementById("candidatePassword").value;

 if(!name||!email||!phone||!password){

  alert("Veuillez remplir tous les champs.");

  return;
 }

 const users=getData(KEY.users);

 const exists=users.find(
  u=>u.email.toLowerCase()===email.toLowerCase()
 );

 if(exists){

  alert("Un compte existe déjà avec cet email.");

  return;
 }

 const user={
  id:uid(),
  role:"candidate",
  name,
  email,
  phone,
  password,
  createdAt:new Date().toISOString()
 };

 users.push(user);

 saveData(KEY.users,users);

 setMe(user);

 alert("✅ Compte candidat créé avec succès !");

 showPage("home");
}


/* =========================
   INSCRIPTION ENTREPRISE
========================= */

function registerCompany(){

 const name=document.getElementById("companyName").value.trim();
 const email=document.getElementById("companyEmail").value.trim();
 const phone=document.getElementById("companyPhone").value.trim();
 const address=document.getElementById("companyAddress").value.trim();
 const password=document.getElementById("companyPassword").value;

 if(!name||!email||!phone||!password){

  alert("Veuillez remplir tous les champs obligatoires.");

  return;
 }

 const users=getData(KEY.users);

 const exists=users.find(
  u=>u.email.toLowerCase()===email.toLowerCase()
 );

 if(exists){

  alert("Un compte existe déjà avec cet email.");

  return;
 }

 const user={
  id:uid(),
  role:"company",
  name,
  email,
  phone,
  address,
  password,
  createdAt:new Date().toISOString()
 };

 users.push(user);

 saveData(KEY.users,users);

 setMe(user);

 alert("✅ Compte entreprise créé avec succès !");

 showPage("home");
}


/* =========================
   CONNEXION
========================= */

function login(){

 const email=document.getElementById("loginEmail").value.trim();
 const password=document.getElementById("loginPassword").value;

 if(!email||!password){

  alert("Veuillez remplir tous les champs.");

  return;
 }

 const users=getData(KEY.users);

 const user=users.find(
  u=>
   u.email.toLowerCase()===email.toLowerCase()&&
   u.password===password
 );

 if(!user){

  alert("❌ Email ou mot de passe incorrect.");

  return;
 }

 setMe(user);

 alert("✅ Connexion réussie !");

 showPage("home");
}


/* =========================
   DECONNEXION
========================= */

function logout(){

 localStorage.removeItem(KEY.me);

 updateNav();

 showPage("home");
}


/* =========================
   PUBLIER UNE OFFRE
========================= */

function publishJob(){

 const me=getMe();

 if(!me||me.role!=="company"){

  alert("Vous devez être connecté comme entreprise.");

  return;
 }

 const title=document.getElementById("jobTitle").value.trim();
 const description=document.getElementById("jobDescription").value.trim();
 const location=document.getElementById("jobLocation").value.trim();
 const salary=document.getElementById("jobSalary").value.trim();

 if(!title||!description||!location){

  alert("Veuillez remplir les champs obligatoires.");

  return;
 }

 const jobs=getData(KEY.jobs);

 jobs.push({

  id:uid(),

  companyId:me.id,

  companyName:me.name,

  title,

  description,

  location,

  salary,

  createdAt:new Date().toISOString()

 });

 saveData(KEY.jobs,jobs);

 document.getElementById("jobTitle").value="";
 document.getElementById("jobDescription").value="";
 document.getElementById("jobLocation").value="";
 document.getElementById("jobSalary").value="";

 alert("✅ Offre publiée avec succès !");

 showPage("myJobs");
}


/* =========================
   TOUTES LES OFFRES
========================= */

function renderJobs(){

 const box=document.getElementById("jobsList");
 const jobs=getData(KEY.jobs);

 if(!jobs.length){

  box.innerHTML=`
   <div class="card empty">
    Aucune offre disponible.
   </div>
  `;

  return;
 }

 box.innerHTML=jobs.map(job=>`

  <div class="card">

   <h3>${escapeHTML(job.title)}</h3>

   <p>🏢 ${escapeHTML(job.companyName)}</p>

   <p>📍 ${escapeHTML(job.location)}</p>

   <p>💰 ${escapeHTML(job.salary||"Non précisé")}</p>

   <p style="margin-top:10px">
    ${escapeHTML(job.description)}
   </p>

   <button class="btn blue"
    onclick="applyJob('${job.id}')">
    📩 Postuler
   </button>

   <button class="btn gray"
    onclick="toggleFavorite('${job.id}')">
    ⭐ Favori
   </button>

  </div>

 `).join("");
}


/* =========================
   POSTULER
========================= */

function applyJob(jobId){

 const me=getMe();

 if(!me){

  alert("Connectez-vous pour postuler.");

  showPage("login");

  return;
 }

 if(me.role!=="candidate"){

  alert("Seuls les candidats peuvent postuler.");

  return;
 }

 const jobs=getData(KEY.jobs);

 const job=jobs.find(
  j=>j.id===jobId
 );

 if(!job)return;

 const apps=getData(KEY.apps);

 const already=apps.find(
  a=>
   a.jobId===jobId&&
   a.candidateId===me.id
 );

 if(already){

  alert("Vous avez déjà postulé à cette offre.");

  return;
 }

 apps.push({

  id:uid(),

  jobId:job.id,

  companyId:job.companyId,

  candidateId:me.id,

  status:"En attente",

  createdAt:new Date().toISOString()

 });

 saveData(KEY.apps,apps);

 alert("✅ Candidature envoyée !");

 showPage("applications");
}


/* =========================
   CANDIDATURES CANDIDAT
========================= */

function renderApplications(){

 const box=document.getElementById("applicationsList");
 const me=getMe();

 if(!me||me.role!=="candidate"){

  box.innerHTML=`
   <div class="card empty">
    Connectez-vous comme candidat.
   </div>
  `;

  return;
 }

 const apps=getData(KEY.apps)
  .filter(a=>a.candidateId===me.id);

 const jobs=getData(KEY.jobs);

 if(!apps.length){

  box.innerHTML=`
   <div class="card empty">
    Vous n'avez envoyé aucune candidature.
   </div>
  `;

  return;
 }

 box.innerHTML=apps.map(app=>{

  const job=jobs.find(
   j=>j.id===app.jobId
  );

  if(!job)return"";

  return`

   <div class="card">

    <h3>${escapeHTML(job.title)}</h3>

    <p>
     🏢 ${escapeHTML(job.companyName)}
    </p>

    <p>
     📍 ${escapeHTML(job.location)}
    </p>

    <p>
     Statut :
     <span class="badge">
      ${escapeHTML(app.status)}
     </span>
    </p>

   </div>
  `;

 }).join("");
}


/* =========================
   FAVORIS
========================= */

function toggleFavorite(jobId){

 const me=getMe();

 if(!me){

  alert("Connectez-vous d'abord.");

  showPage("login");

  return;
 }

 let favs=getData(KEY.favs);

 const exists=favs.find(
  f=>f.userId===me.id&&f.jobId===jobId
 );

 if(exists){

  favs=favs.filter(
   f=>!(f.userId===me.id&&f.jobId===jobId)
  );

 }else{

  favs.push({
   id:uid(),
   userId:me.id,
   jobId
  });
 }

 saveData(KEY.favs,favs);

 alert(exists?"Retiré des favoris.":"Ajouté aux favoris.");

}


/* =========================
   FAVORIS
========================= */

function renderFavorites(){

 const box=document.getElementById("favoritesList");
 const me=getMe();

 if(!me){

  box.innerHTML=`
   <div class="card empty">
    Connectez-vous pour voir vos favoris.
   </div>
  `;

  return;
 }

 const favs=getData(KEY.favs)
  .filter(f=>f.userId===me.id);

 const jobs=getData(KEY.jobs);

 const list=favs
  .map(f=>jobs.find(j=>j.id===f.jobId))
  .filter(Boolean);

 if(!list.length){

  box.innerHTML=`
   <div class="card empty">
    Aucun favori.
   </div>
  `;

  return;
 }

 box.innerHTML=list.map(job=>`

  <div class="card">

   <h3>${escapeHTML(job.title)}</h3>

   <p>🏢 ${escapeHTML(job.companyName)}</p>

   <p>📍 ${escapeHTML(job.location)}</p>

   <button class="btn blue"
    onclick="applyJob('${job.id}')">
    Postuler
   </button>

  </div>

 `).join("");
}


/* =========================
   MES OFFRES ENTREPRISE
========================= */

function renderMyJobs(){

 const box=document.getElementById("myJobsList");
 const me=getMe();

 if(!me||me.role!=="company"){

  box.innerHTML=`
   <div class="card empty">
    Accès réservé aux entreprises.
   </div>
  `;

  return;
 }

 /*
  SEULEMENT LES OFFRES DE CETTE ENTREPRISE
 */

 const jobs=getData(KEY.jobs)
  .filter(j=>j.companyId===me.id);

 if(!jobs.length){

  box.innerHTML=`
   <div class="card empty">

    Vous n'avez aucune offre.

    <br>

    <button class="btn blue"
     onclick="showPage('publishJob')">
     Publier une offre
    </button>

   </div>
  `;

  return;
 }

 box.innerHTML=jobs.map(job=>`

  <div class="card">

   <h3>${escapeHTML(job.title)}</h3>

   <p>${escapeHTML(job.description)}</p>

   <p>📍 ${escapeHTML(job.location)}</p>

   <p>💰 ${escapeHTML(job.salary)}</p>

   <button class="btn blue"
    onclick="showJobApplicants('${job.id}')">
    👥 Voir mes candidats
   </button>

   <button class="btn red"
    onclick="deleteJob('${job.id}')">
    🗑 Supprimer
   </button>

  </div>

 `).join("");
}


/* =========================
   CANDIDATS D'UNE OFFRE
========================= */

function showJobApplicants(jobId){

 const me=getMe();

 if(!me||me.role!=="company")return;

 /*
  VÉRIFICATION :
  l'offre doit appartenir à cette entreprise.
 */

 const jobs=getData(KEY.jobs);

 const job=jobs.find(
  j=>j.id===jobId&&j.companyId===me.id
 );

 if(!job){

  alert("Vous n'avez pas accès à cette offre.");

  return;
 }

 const apps=getData(KEY.apps)
  .filter(
   a=>
    a.jobId===jobId&&
    a.companyId===me.id
  );

 const users=getData(KEY.users);

 if(!apps.length){

  alert("Aucun candidat n'a encore postulé.");

  return;
 }

 let message=
  "CANDIDATS POUR : "+job.title+"\n\n";

 apps.forEach(app=>{

  const candidate=users.find(
   u=>u.id===app.candidateId
  );

  if(candidate){

   message+=
    "👤 "+candidate.name+
    "\n📧 "+candidate.email+
    "\n📞 "+candidate.phone+
    "\n\n";

  }

 });

 alert(message);
}


/* =========================
   MES CANDIDATS
========================= */

function renderCompanyApplications(){

 const box=document.getElementById(
  "companyApplicationsList"
 );

 const me=getMe();

 if(!me||me.role!=="company"){

  box.innerHTML=`
   <div class="card empty">
    Accès réservé aux entreprises.
   </div>
  `;

  return;
 }

 /*
  RÈGLE PRINCIPALE :

  companyId === me.id

  Donc l'entreprise ne voit
  QUE ses propres candidatures.
 */

 const apps=getData(KEY.apps)
  .filter(a=>a.companyId===me.id);

 const users=getData(KEY.users);

 const jobs=getData(KEY.jobs)
  .filter(j=>j.companyId===me.id);

 if(!apps.length){

  box.innerHTML=`
   <div class="card empty">
    Aucun candidat n'a postulé à vos offres.
   </div>
  `;

  return;
 }

 box.innerHTML=apps.map(app=>{

  const candidate=users.find(
   u=>u.id===app.candidateId
  );

  const job=jobs.find(
   j=>j.id===app.jobId
  );

  if(!candidate||!job)return"";

  return`

   <div class="card">

    <h3>
     👤 ${escapeHTML(candidate.name)}
    </h3>

    <p>
     📄 Offre :
     <strong>${escapeHTML(job.title)}</strong>
    </p>

    <p>
     📧 ${escapeHTML(candidate.email)}
    </p>

    <p>
     📞 ${escapeHTML(candidate.phone)}
    </p>

    <span class="badge">
     ${escapeHTML(app.status)}
    </span>

    <br>

    <button class="btn blue"
     onclick="openConversation('${candidate.id}')">
     💬 Contacter
    </button>

   </div>

  `;

 }).join("");
}


/* =========================
   SUPPRIMER UNE OFFRE
========================= */

function deleteJob(jobId){

 const me=getMe();

 if(!me||me.role!=="company")return;

 let jobs=getData(KEY.jobs);

 const job=jobs.find(
  j=>j.id===jobId&&j.companyId===me.id
 );

 if(!job){

  alert("Vous ne pouvez pas supprimer cette offre.");

  return;
 }

 if(!confirm("Voulez-vous supprimer cette offre ?"))
  return;

 jobs=jobs.filter(
  j=>j.id!==jobId
 );

 saveData(KEY.jobs,jobs);

 let apps=getData(KEY.apps);

 apps=apps.filter(
  a=>a.jobId!==jobId
 );

 saveData(KEY.apps,apps);

 alert("✅ Offre supprimée.");

 renderMyJobs();
}


/* =========================
   MESSAGES
========================= */

function addMessage(receiverId,textMessage){

 const me=getMe();

 if(!me)return;

 const msgs=getData(KEY.msgs);

 msgs.push({

  id:uid(),

  senderId:me.id,

  receiverId,

  text:textMessage,

  createdAt:new Date().toISOString()

 });

 saveData(KEY.msgs,msgs);
}


/* =========================
   ENTREPRISE → CANDIDAT
========================= */

function companyCanContactCandidate(candidateId){

 const me=getMe();

 if(!me||me.role!=="company")
  return false;

 const apps=getData(KEY.apps);

 /*
  L'entreprise peut contacter
  uniquement un candidat qui
  a postulé à SES offres.
 */

 return apps.some(
  a=>
   a.companyId===me.id&&
   a.candidateId===candidateId
 );
}


function openConversation(candidateId){

 const me=getMe();

 if(!me||me.role!=="company")
  return;

 if(!companyCanContactCandidate(candidateId)){

  alert(
   "❌ Vous pouvez contacter uniquement les candidats qui ont postulé à vos offres."
  );

  return;
 }

 const users=getData(KEY.users);

 const candidate=users.find(
  u=>u.id===candidateId
 );

 if(!candidate)return;

 const message=prompt(
  "Message pour "+candidate.name+":"
 );

 if(!message||!message.trim())
  return;

 addMessage(
  candidate.id,
  message.trim()
 );

 alert("✅ Message envoyé.");

 showPage("companyMessages");
}


/* =========================
   MESSAGES CANDIDAT
========================= */

function renderMsgs(){

 const box=document.getElementById("msgList");
 const me=getMe();

 if(!me){

  box.innerHTML=`
   <div class="card empty">
    Connectez-vous pour voir vos messages.
   </div>
  `;

  return;
 }

 const msgs=getData(KEY.msgs)
  .filter(
   m=>
    m.senderId===me.id||
    m.receiverId===me.id
  );

 const users=getData(KEY.users);

 if(!msgs.length){

  box.innerHTML=`
   <div class="card empty">
    Aucun message.
   </div>
  `;

  return;
 }

 box.innerHTML=msgs.map(m=>{

  const otherId=
   m.senderId===me.id
   ?m.receiverId
   :m.senderId;

  const other=users.find(
   u=>u.id===otherId
  );

  return`

   <div class="card">

    <h3>
     ${escapeHTML(other?.name||"Utilisateur")}
    </h3>

    <p>${escapeHTML(m.text)}</p>

   </div>
  `;

 }).join("");
}


/* =========================
   MESSAGES ENTREPRISE
========================= */

function renderCompanyMessages(){

 const box=document.getElementById(
  "companyMsgList"
 );

 const me=getMe();

 if(!me||me.role!=="company"){

  box.innerHTML=`
   <div class="card empty">
    Accès réservé aux entreprises.
   </div>
  `;

  return;
 }

 const msgs=getData(KEY.msgs)
  .filter(
   m=>
    m.senderId===me.id||
    m.receiverId===me.id
  );

 const users=getData(KEY.users);

 /*
  IMPORTANT :
  On garde seulement les conversations
  avec les candidats qui ont postulé
  à CETTE entreprise.
 */

 const allowed=msgs.filter(m=>{

  const otherId=
   m.senderId===me.id
   ?m.receiverId
   :m.senderId;

  return companyCanContactCandidate(otherId);
 });

 if(!allowed.length){

  box.innerHTML=`
   <div class="card empty">
    Aucun message avec vos candidats.
   </div>
  `;

  return;
 }

 box.innerHTML=allowed.map(m=>{

  const otherId=
   m.senderId===me.id
   ?m.receiverId
   :m.senderId;

  const other=users.find(
   u=>u.id===otherId
  );

  return`

   <div class="card">

    <h3>
     👤 ${escapeHTML(other?.name||"Candidat")}
    </h3>

    <p>${escapeHTML(m.text)}</p>

   </div>
  `;

 }).join("");
}


/* =========================
   PROFIL CANDIDAT
========================= */

function renderProfile(){

 const box=document.getElementById("profileContent");
 const me=getMe();

 if(!me){

  box.innerHTML=`
   <div class="card empty">
    Vous n'êtes pas connecté.
   </div>
  `;

  return;
 }

 box.innerHTML=`

  <div class="card">

   <h3>👤 ${escapeHTML(me.name)}</h3>

   <p class="info">

    📧 ${escapeHTML(me.email)}<br>

    📞 ${escapeHTML(me.phone)}

   </p>

  </div>
 `;
}


/* =========================
   PROFIL ENTREPRISE
========================= */

function renderCompanyProfile(){

 const box=document.getElementById(
  "companyProfileContent"
 );

 const me=getMe();

 if(!me||me.role!=="company"){

  box.innerHTML=`
   <div class="card empty">
    Accès réservé aux entreprises.
   </div>
  `;

  return;
 }

 box.innerHTML=`

  <div class="card">

   <h2>🏢 ${escapeHTML(me.name)}</h2>

   <p class="info">

    📧 ${escapeHTML(me.email)}<br>

    📞 ${escapeHTML(me.phone)}<br>

    📍 ${escapeHTML(me.address||"Non renseignée")}

   </p>

   <p style="margin-top:15px">
    🔒 Cet espace appartient uniquement à votre entreprise.
   </p>

  </div>
 `;
}


/* =========================
   TABLEAU CANDIDAT
========================= */

function renderCandidateDashboard(){

 const box=document.getElementById(
  "candidateDashboardContent"
 );

 const me=getMe();

 if(!me||me.role!=="candidate"){

  box.innerHTML=`
   <div class="card empty">
    Accès réservé aux candidats.
   </div>
  `;

  return;
 }

 const apps=getData(KEY.apps)
  .filter(a=>a.candidateId===me.id);

 box.innerHTML=`

  <div class="card">

   <h3>
    Bienvenue ${escapeHTML(me.name)} 👋
   </h3>

   <p class="info">

    📧 ${escapeHTML(me.email)}<br>

    📞 ${escapeHTML(me.phone)}

   </p>

   <p style="margin-top:10px">
    📄 Candidatures :
    <strong>${apps.length}</strong>
   </p>

  </div>
 `;
}


/* =========================
   TABLEAU ENTREPRISE
========================= */

function renderCompanyDashboard(){

 const box=document.getElementById(
  "companyDashboardContent"
 );

 const me=getMe();

 if(!me||me.role!=="company"){

  box.innerHTML=`
   <div class="card empty">
    Accès réservé aux entreprises.
   </div>
  `;

  return;
 }

 const jobs=getData(KEY.jobs)
  .filter(j=>j.companyId===me.id);

 const apps=getData(KEY.apps)
  .filter(a=>a.companyId===me.id);

 box.innerHTML=`

  <div class="card">

   <h2>
    🏢 ${escapeHTML(me.name)}
   </h2>

   <p class="info">

    📧 ${escapeHTML(me.email)}<br>

    📞 ${escapeHTML(me.phone)}<br>

    📍 ${escapeHTML(me.address||"Non renseignée")}

   </p>

  </div>

  <div class="grid">

   <div class="card">
    <h3>💼 Mes offres</h3>
    <p>${jobs.length}</p>
   </div>

   <div class="card">
    <h3>👥 Mes candidats</h3>
    <p>${apps.length}</p>
   </div>

  </div>
 `;
}


/* =========================
   DEMARRAGE
========================= */

function init(){

 updateNav();

 showPage("home");

}

init();

</script>

</body>
</html>
