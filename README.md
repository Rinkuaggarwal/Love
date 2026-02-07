
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
    overflow:hidden;
}

/* Floating hearts */
.heart-float{
    position:absolute;
    color:rgba(255,255,255,0.6);
    font-size:20px;
    animation:float 6s infinite linear;
}

@keyframes float{
    0%{transform:translateY(100vh);opacity:0;}
    20%{opacity:1;}
    100%{transform:translateY(-10vh);opacity:0;}
}

/* Envelope */
.envelope{
    width:320px;
    height:220px;
    background:#e91e63;
    position:relative;
    cursor:pointer;
    border-radius:12px;
    box-shadow:0 15px 40px rgba(0,0,0,0.35);
    z-index:10;
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
    height:420px;
    background:white;
    border-radius:18px;
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
    from{transform:translateY(120px);opacity:0;}
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
    margin-bottom:10px;
}

p{
    color:#555;
    font-size:15px;
    line-height:1.6;
}

button{
    background:#e91e63;
    color:white;
    border:none;
    padding:10px 22px;
    border-radius:30px;
    cursor:pointer;
    margin-top:15px;
}

button:hover{
    background:#c2185b;
}

.heart{
    font-size:32px;
    animation:beat 1.2s infinite;
}

@keyframes beat{
    0%{transform:scale(1);}
    50%{transform:scale(1.3);}
    100%{transform:scale(1);}
}

/* Creative Art */
.art{
    margin:20px 0;
    font-size:42px;
}

.ring{
    font-size:36px;
    margin:10px 0;
}
</style>
</head>

<body>

<!-- Floating hearts -->
<span class="heart-float" style="left:10%;">💖</span>
<span class="heart-float" style="left:30%; animation-delay:2s;">💗</span>
<span class="heart-float" style="left:60%; animation-delay:4s;">💕</span>
<span class="heart-float" style="left:80%; animation-delay:1s;">💞</span>

<!-- 🎵 Let Me Love You -->
<iframe id="ytMusic"
    width="0"
    height="0"
    src="https://www.youtube.com/embed/SMs0GnYze34?enablejsapi=1"
    frameborder="0"
    allow="autoplay">
</iframe>

<div class="envelope" onclick="openEnvelope()">
    <div class="flap"></div>

    <div class="card">

        <!-- Page 1 -->
        <div class="page active">
            <h1>❤️ 2 Years of Togetherness ❤️</h1>
            <p>
                Two beautiful years, countless memories,  
                and a love that grows stronger every day.
            </p>
            <div class="art">🧸💑🧸</div>
            <div class="heart">💖</div>
            <button onclick="nextPage(event)">Next ➜</button>
        </div>

        <!-- Page 2 -->
        <div class="page">
            <h1>Our Love Story 💕</h1>
            <p>
                From small smiles to endless laughs,  
                every moment with you feels magical.
            </p>
            <div class="ring">💍❤️💍</div>
            <div class="art">✨💞✨</div>
            <button onclick="nextPage(event)">Next ➜</button>
        </div>

        <!-- Page 3 -->
        <div class="page">
            <h1>Forever Us ✨</h1>
            <p>
                Thank you for being my smile, my peace,  
                and my safe place.  
                Here’s to forever… together ❤️
            </p>
            <div class="art">🧸❤️🧸</div>
            <div class="heart">💞</div>
            <p><i>Let me love you… always.</i></p>
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

        const iframe=document.getElementById("ytMusic");
        iframe.src += "&autoplay=1";

        opened=true;
    }
}

function nextPage(e){
    e.stopPropagation();
    pages[pageIndex].classList.remove('active');
    pageIndex++;
    pages[pageIndex].classList.add('active');
}
</script>

</body>
</html>

