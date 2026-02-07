
<html lang="en">
<head>
<meta charset="UTF-8">
<title>2 Years of Togetherness</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    body {
        margin: 0;
        padding: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        font-family: 'Segoe UI', sans-serif;
    }

    .card {
        background: white;
        width: 350px;
        padding: 25px;
        border-radius: 20px;
        text-align: center;
        box-shadow: 0 15px 40px rgba(0,0,0,0.25);
        animation: fadeIn 1.5s ease;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: scale(0.9); }
        to { opacity: 1; transform: scale(1); }
    }

    h1 {
        color: #e91e63;
        margin-bottom: 10px;
    }

    h2 {
        color: #444;
        margin: 10px 0;
    }

    .photo-box {
        width: 100%;
        height: 200px;
        border: 2px dashed #e91e63;
        border-radius: 15px;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
        margin: 15px 0;
    }

    .photo-box img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        display: none;
    }

    input[type="file"] {
        margin: 10px 0;
    }

    p {
        color: #555;
        font-size: 15px;
        line-height: 1.6;
    }

    .heart {
        font-size: 30px;
        animation: heartbeat 1.2s infinite;
        color: #e91e63;
        margin-top: 10px;
    }

    @keyframes heartbeat {
        0% { transform: scale(1); }
        50% { transform: scale(1.3); }
        100% { transform: scale(1); }
    }

    .footer {
        margin-top: 15px;
        font-style: italic;
        color: #777;
    }
</style>
</head>

<body>

<div class="card">
    <h1>❤️ 2 Years of Togetherness my love ❤️</h1>
    <h2>Forever & Always</h2>

    <div class="photo-box">
        <span id="placeholder">Add Your Beautiful Photo 💑</span>
        <img id="preview">
    </div>

    <input type="file" accept="image/*" onchange="loadImage(event)">

    <p>
        Two years, countless memories, endless smiles, and a love that keeps growing stronger every day.  
        Thank you for being my happiness, my comfort, and my forever.
    </p>

    <div class="heart">💖</div>

    <div class="footer">
        Cheers to many more years of love ✨
    </div>
</div>

<script>
    function loadImage(event) {
        const img = document.getElementById('preview');
        const placeholder = document.getElementById('placeholder');
        img.src = URL.createObjectURL(event.target.files[0]);
        img.style.display = "block";
        placeholder.style.display = "none";
    }
</script>

</body>
</html>
