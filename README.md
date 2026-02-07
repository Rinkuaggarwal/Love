
<html lang="en">
<head>
<meta charset="UTF-8">
<title>2 Years of Togetherness</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ff9a9e,#fad0c4);
    font-family:'Segoe UI',sans-serif;
}

/* Envelope */
.envelope{
    width:320px;
    height:220px;
    background:#e91e63;
    position:relative;
    cursor:pointer;
    border-radius:10px;
    box-shadow:0 15px 40px rgba(0,0,0,0.3);
}

.flap{
    position:absolute;
    top:0;
    width:100%;
    height:100%;
    background:#ff5f8a;
    clip-path:polygon(0 0,50% 60%,100% 0);
    transform-origin:top;
    transition:1s;
}

.envelope.open .flap{
    transform:rotateX(180deg);
}

/* Card */
.card{
    position:absolute;
    top:10px;
    left:10px;
    width:300px;
    height:400px;
    background:white;
    border-radius:15px;
    padding:20px;
    display:none;
    flex-direction:column;
    justify-content:space-between;
    animation:slideUp 1s ease;
}

.envelope.open .card{
    display:flex;
}

@keyframes slideUp{
    from{transform:translateY(100px);opacity:0;}
    to{transform:translateY(0);opacity:1;}
}

.page{
    display:none;
    text-align:center;
}

.page.active{
    display:block;
}

h1{
    color:#e91e63;
}

p{
    color:#555;
    font-size:15px;
    line-height:1.6;
}

.photo-box{
    width:100%;
    height:180px;
    border:2px dashed #e91e63;
    border-radius:12px;
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;
}

.photo-box img{
    width:100%;
    height:100%;
    object-fit:cover;
    display:none;
}

button{
    background:#e91e63;
    color:white;
    border:none;
    padding:10px 20px;
    border-radius:25px;
    cursor:pointer;
    margin-top:10px;
}

button:hover{
    background:#c2185b;
}

.heart{
    font-size:30px;
    animation:beat 1.2s infinite;
}

@keyframes beat{
    0%{transform:scale(1);}
    50%{transform:scale(1.3);}
    100%{transform:scale(1);}
}
</style>
</head>

<body>

<!-- Background Music -->
<audio id="music" loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<div class="envelope" onclick="openEnvelope()">
    <div class="flap"></div>

    <div class="card">

        <!-- Page 1 -->
        <div class="page active">
            <h1>❤️ 2 Years of Togetherness ❤️</h1>
            <p>
                Two beautiful years, countless memories, and a love that grows deeper every day.
            </p>
            <div class="heart">💖</div>
            <button onclick="nextPage(event)">Next ➜</button>
        </div>

        <!-- Page 2 -->
        <div class="page">
            <h1>Our Moments 💑</h1>

            <div class="photo-box">
                <span id="text">Add Your Photo</span>
                <img id="img">
            </div>

            <input type="file" accept="image/*" onchange="loadImg(event)">
            <button onclick="nextPage(event)">Next ➜</button>
        </div>

        <!-- Page 3 -->
        <div class="page">
            <h1>Forever Us ✨</h1>
            <p>
                Thank you for being my smile, my peace, and my safe place.  
                Here’s to many more years of love, laughter, and togetherness.
            </p>
            <div class="heart">💞</div>
            <p><i>Always & Forever</i></p>
        </div>

    </div>
</div>

<script>
let opened=false;
let pageIndex=0;
const pages=document.querySelectorAll('.page');

function openEnvelope(){
    if(!opened){
        document.querySelector('.envelope').classList.add('open');
        document.getElementById('music').play();
        opened=true;
    }
}

function nextPage(e){
    e.stopPropagation();
    pages[pageIndex].classList.remove('active');
    pageIndex++;
    pages[pageIndex].classList.add('active');
}

function loadImg(e){
    const img=document.getElementById('img');
    const text=document.getElementById('text');
    img.src=URL.createObjectURL(e.target.files[0]);
    img.style.display="block";
    text.style.display="none";
}
</script>

</body>
</html>

    
