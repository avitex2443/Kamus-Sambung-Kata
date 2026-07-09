<!DOCTYPE html>
<html lang="id">

<head>

<meta charset="UTF-8">

<meta
name="viewport"
content="width=device-width, initial-scale=1.0">

<title>Sambung Kata</title>

<link
rel="stylesheet"
href="style.css">

</head>

<body>

<header>

<h1>

<a
href="https://www.roblox.com/games/130342654546662/CHAOS-Sambung-Kata?gameSetTypeId=100000003&homePageSessionInfo=8e8c1bb8-7f18-4025-b1b3-8e2ae1ac4e93&isAd=false&newGameEnum_analyticsData=0&numberOfLoadedTiles=112&page=homePage&placeId=130342654546662&playContext=homePage&position=0&positionInRow=0&rowOnPage=3&sortPos=2&sortSubId=&universeId=9546331833"
target="_blank">

Sambung Kata

</a>

</h1>

<p>

Kamus Sambung Kata 

</p>

</header>


<div class="search-box">

<div class="input-group">

<label>

Awalan

</label>

<input
type="text"
id="awal"
placeholder="Contoh : ber">

</div>


<div class="input-group">

<label>

Akhiran

</label>

<input
type="text"
id="akhir"
placeholder="Contoh : kan">

</div>

</div>


<div class="toolbar">

<button id="copyPage">

📋 Salin Halaman

</button>

<button id="toggleBg">

🖼 Background ON

</button>

</div>


<p id="jumlah">

0 kata ditemukan

</p>
<!-- =========================
     TABEL HASIL
========================= -->

<div class="table-container">

<table>

<thead>

<tr>

<th>No</th>

<th>Kata</th>

<th>Huruf</th>

<th>Salin</th>

</tr>

</thead>

<tbody id="hasil">

</tbody>

</table>

</div>


<!-- =========================
     INFO HALAMAN
========================= -->

<div class="page-info">

<span id="pageText">

Menampilkan 0 - 0 dari 0 kata

</span>

</div>


<!-- =========================
     PAGINATION
========================= -->

<div class="pagination">

<button id="firstPage">

⏮

</button>

<button id="prevPage">

◀

</button>

<span id="pageNumber">

1/1

</span>

<button id="nextPage">

▶

</button>

<button id="lastPage">

⏭

</button>

</div>


<!-- =========================
     FOOTER
========================= -->

<footer>

<p>

© 2026

<a
href="https://www.youtube.com/@avitex2443"
target="_blank">

<b>Avitex</b>

</a>

</p>

<p>


</a>

</p>

</footer>

<!-- =========================
     VIDEO BUTTON
========================= -->

<button id="videoBtn">

Tombol Rahasia

</button>

<script src="database.js"></script>

<script src="script.js"></script>

</body>

</html>

/* =====================================================
   AVITEX SAMBUNG KATA
===================================================== */

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{

    font-family:Arial,Helvetica,sans-serif;

    color:#ffffff;

    background:#10131c;

    min-height:100vh;

    padding:20px;

}

/* =========================
   BACKGROUND
========================= */

body::before{

    content:"";

    position:fixed;

    inset:0;

    z-index:-2;

    background:
    radial-gradient(circle at top left,#263248 0%,transparent 45%),
    radial-gradient(circle at bottom right,#162238 0%,transparent 45%),
    linear-gradient(135deg,#111827,#0f172a,#111827);

}

body::after{

    content:"";

    position:fixed;

    inset:0;

    z-index:-1;

    opacity:.08;

    background-image:

    repeating-linear-gradient(
    0deg,
    transparent,
    transparent 2px,
    white 3px),

    repeating-linear-gradient(
    90deg,
    transparent,
    transparent 2px,
    white 3px);

}

/* Background OFF */

body.bg-off{

    background:#ffffff;

    color:#111;

}

body.bg-off::before,
body.bg-off::after{

    display:none;

}

/* =========================
   HEADER
========================= */

header{

    text-align:center;

    margin-bottom:25px;

}

header h1{

    font-size:34px;

    margin-bottom:8px;

}

header a{

    color:#4da3ff;

    text-decoration:none;

    transition:.2s;

}

header a:hover{

    color:#7dbdff;

}

header p{

    color:#cccccc;

    font-size:15px;

}
/* =========================
   SEARCH BOX
========================= */

.search-box{

    display:flex;

    gap:15px;

    justify-content:center;

    flex-wrap:wrap;

    margin-bottom:20px;

}

.input-group{

    display:flex;

    flex-direction:column;

    min-width:220px;

}

.input-group label{

    margin-bottom:6px;

    font-weight:bold;

    color:#e5e7eb;

}

.input-group input{

    width:100%;

    padding:12px 14px;

    border:none;

    border-radius:10px;

    outline:none;

    font-size:16px;

    background:#1f2937;

    color:white;

    transition:.25s;

}

.input-group input:focus{

    background:#273449;

    box-shadow:0 0 10px #3b82f6;

}


/* =========================
   TOOLBAR
========================= */

.toolbar{

    display:flex;

    justify-content:center;

    gap:12px;

    flex-wrap:wrap;

    margin-bottom:20px;

}

.toolbar button{

    background:#2563eb;

    color:white;

    border:none;

    padding:11px 18px;

    border-radius:10px;

    cursor:pointer;

    font-size:15px;

    font-weight:bold;

    transition:.25s;

}

.toolbar button:hover{

    background:#1d4ed8;

    transform:translateY(-2px);

}

.toolbar button:active{

    transform:scale(.97);

}


/* =========================
   JUMLAH KATA
========================= */

#jumlah{

    text-align:center;

    margin-bottom:15px;

    font-size:17px;

    font-weight:bold;

    color:#dbeafe;

}


/* =========================
   TABLE CONTAINER
========================= */

.table-container{

    width:100%;

    overflow-x:auto;

    border-radius:12px;

    background:#111827;

    box-shadow:0 0 15px rgba(0,0,0,.35);

}

table{

    width:100%;

    border-collapse:collapse;

}

thead{

    background:#2563eb;

}

thead th{

    padding:13px;

    color:white;

    font-size:15px;

}

tbody tr{

    border-bottom:1px solid #2d3748;

    transition:.15s;

}

tbody tr:hover{

    background:#1e293b;

}

tbody td{

    padding:12px;

    text-align:center;

    color:#f3f4f6;

}


/* =========================
   COPY BUTTON
========================= */

.copy{

    background:#3b82f6;

    color:white;

    border:none;

    border-radius:8px;

    padding:7px 10px;

    cursor:pointer;

    transition:.2s;

}

.copy:hover{

    background:#2563eb;

    transform:scale(1.08);

}
/* =========================
   PAGE INFO
========================= */

.page-info{

    margin-top:18px;

    margin-bottom:15px;

    text-align:center;

    font-size:15px;

    color:#d1d5db;

}


/* =========================
   PAGINATION
========================= */

.pagination{

    display:flex;

    justify-content:center;

    align-items:center;

    gap:10px;

    margin:20px 0;

    flex-wrap:wrap;

}

.pagination button{

    width:42px;

    height:42px;

    border:none;

    border-radius:10px;

    background:#2563eb;

    color:white;

    font-size:18px;

    cursor:pointer;

    transition:.2s;

}

.pagination button:hover:not(:disabled){

    background:#1d4ed8;

    transform:translateY(-2px);

}

.pagination button:active:not(:disabled){

    transform:scale(.95);

}

.pagination button:disabled{

    background:#475569;

    cursor:not-allowed;

    opacity:.6;

}

#pageNumber{

    min-width:90px;

    text-align:center;

    font-weight:bold;

    font-size:18px;

    color:#ffffff;

    background:#1f2937;

    padding:10px 16px;

    border-radius:10px;

}


/* =========================
   FOOTER
========================= */

footer{

    margin-top:35px;

    text-align:center;

    color:#94a3b8;

    font-size:14px;

}

footer b{

    color:#60a5fa;

}


/* =========================
   LIGHT MODE
========================= */

body.bg-off{

    background:#f4f4f4;

    color:#111827;

}

body.bg-off .table-container{

    background:white;

}

body.bg-off table{

    color:#111827;

}

body.bg-off tbody td{

    color:#111827;

}

body.bg-off tbody tr:hover{

    background:#f1f5f9;

}

body.bg-off .input-group input{

    background:white;

    color:#111827;

    border:1px solid #d1d5db;

}

body.bg-off #pageNumber{

    background:white;

    color:#111827;

    border:1px solid #d1d5db;

}

body.bg-off header p{

    color:#374151;

}


/* =========================
   SCROLLBAR
========================= */

::-webkit-scrollbar{

    width:10px;

    height:10px;

}

::-webkit-scrollbar-track{

    background:#0f172a;

}

::-webkit-scrollbar-thumb{

    background:#3b82f6;

    border-radius:20px;

}

::-webkit-scrollbar-thumb:hover{

    background:#2563eb;

}


/* =========================
   MOBILE
========================= */

@media (max-width:768px){

    body{

        padding:12px;

    }

    header h1{

        font-size:28px;

    }

    .input-group{

        width:100%;

    }

    .toolbar{

        flex-direction:column;

    }

    .toolbar button{

        width:100%;

    }

    table{

        font-size:14px;

    }

    th,td{

        padding:10px 6px;

    }

    #pageNumber{

        min-width:75px;

        font-size:16px;

    }

}


/* =========================
   VIDEO BUTTON
========================= */

#videoBtn{

position:fixed;

right:335px;

bottom:2px;

width:62px;

height:60px;

border:none;

border-radius:50%;

background:#000;

color:white;

font-size:15px;

cursor:pointer;

z-index:9999;

opacity:0;

pointer-events:none;

transition:opacity .3s;

}

#videoBtn.show{

opacity:1;

pointer-events:auto;

}

let database = [
"aba",
"abad
];

/* =========================
   ELEMENT
========================= */

const awalInput =
document.getElementById("awal");

const akhirInput =
document.getElementById("akhir");

const hasilBody =
document.getElementById("hasil");

const jumlah =
document.getElementById("jumlah");

const pageText =
document.getElementById("pageText");

const firstPage =
document.getElementById("firstPage");

const prevPage =
document.getElementById("prevPage");

const nextPage =
document.getElementById("nextPage");

const lastPage =
document.getElementById("lastPage");

/* =========================
   PAGINATION
========================= */

const perPage = 100;

let currentPage = 1;

let filtered = [...database];

/* =========================
   EVENT
========================= */

awalInput.addEventListener("input",function(){

    /* Jangan mencari jika sedang mengetik command */

    if(awalInput.value.startsWith(";")){

        return;

    }

    cari();

});

akhirInput.addEventListener("input",cari);

/* =========================
   SEARCH
========================= */

function cari(){

    const awal =
    awalInput.value
    .trim()
    .toLowerCase();

    const akhir =
    akhirInput.value
    .trim()
    .toLowerCase();

    filtered =
    database.filter(function(kata){

        const k =
        kata.toLowerCase();

        if(
            awal!=="" &&
            akhir!==""
        ){

            return k.startsWith(awal)
            &&
            k.endsWith(akhir);

        }

        if(awal!==""){

            return k.startsWith(awal);

        }

        if(akhir!==""){

            return k.endsWith(akhir);

        }

        return true;

    });

    currentPage = 1;

    render();

}

/* =========================
   TOTAL PAGE
========================= */

function totalPage(){

    return Math.max(
        1,
        Math.ceil(filtered.length / perPage)
    );

}

/* =========================
   UPDATE PAGINATION
========================= */

function updatePagination(){

    const total = totalPage();

    pageText.textContent =
    currentPage + "/" + total;

    firstPage.disabled =
    currentPage === 1;

    prevPage.disabled =
    currentPage === 1;

    nextPage.disabled =
    currentPage === total;

    lastPage.disabled =
    currentPage === total;

}

/* =========================
   RENDER
========================= */

function render(){

    hasilBody.innerHTML = "";

    jumlah.textContent =
    filtered.length +
    " kata ditemukan";

    const start =
    (currentPage - 1) * perPage;

    const end =
    Math.min(
        start + perPage,
        filtered.length
    );

    for(let i = start; i < end; i++){

        const kata = filtered[i];

        const tr =
        document.createElement("tr");

        tr.innerHTML =

        `
        <td>${i+1}</td>

        <td>${kata}</td>

        <td>${kata.length}</td>

        <td>

        <button
        class="copy"
        onclick="copyWord('${kata}')">

        📋

        </button>

        </td>
        `;

        hasilBody.appendChild(tr);

    }

    updatePagination();

}

/* =========================
   PAGINATION BUTTON
========================= */

firstPage.onclick = function(){

    currentPage = 1;

    render();

};

prevPage.onclick = function(){

    if(currentPage > 1){

        currentPage--;

        render();

    }

};

nextPage.onclick = function(){

    if(currentPage < totalPage()){

        currentPage++;

        render();

    }

};

lastPage.onclick = function(){

    currentPage = totalPage();

    render();

};

/* =========================
   COPY WORD
========================= */

function copyWord(kata){

    navigator.clipboard
    .writeText(kata);

    alert(
        "Berhasil disalin\n\n" +
        kata
    );

}

/* =========================
   COPY PAGE
========================= */

const copyPage =
document.getElementById("copyPage");

copyPage.onclick = function(){

    if(filtered.length === 0){

        alert(
            "Tidak ada kata untuk disalin."
        );

        return;

    }

    const start =
    (currentPage - 1) * perPage;

    const end =
    Math.min(
        start + perPage,
        filtered.length
    );

    let text = "";

    for(let i = start; i < end; i++){

        text += filtered[i];

        if(i < end - 1){

            text += "\n";

        }

    }

    navigator.clipboard
    .writeText(text);

    alert(

        "Berhasil menyalin "

        + (end - start)

        + " kata."

    );

};

/* =========================
   BACKGROUND
========================= */

const toggleBg =
document.getElementById("toggleBg");

let bgOn = true;

toggleBg.onclick = function(){

    bgOn = !bgOn;

    document.body.classList.toggle(
        "bg-off",
        !bgOn
    );

    toggleBg.textContent =

    bgOn

    ? "🖼 Background"

    : "🖼 Background OFF";

};

/* =========================
   VIDEO
========================= */

const videoBtn =
document.getElementById("videoBtn");

/* Ganti link ini dengan video YouTube Anda */

const youtubeLink =
"https://youtu.be/RxAltZ1On_A?si=a-zdDzvlnHQHwuvC";

videoBtn.onclick = function(){

    window.open(
        youtubeLink,
        "_blank"
    );

};

/* =========================
   TAMPILKAN TOMBOL VIDEO
   SAAT SUDAH MENTOK BAWAH
========================= */

window.addEventListener("scroll", function(){

    const bawah =

    window.innerHeight +

    window.scrollY >=

    document.documentElement.scrollHeight - 5;

    if(bawah){

        videoBtn.classList.add("show");

    }else{

        videoBtn.classList.remove("show");

    }

});

/* =========================
   START
========================= */

render();
