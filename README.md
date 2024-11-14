<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Parallax Effect</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h2 class="logo">Moon Parallax</h2>
        <nav class="navigation">
            <a href="#" class="active">Home</a>
            <a href="#">About</a>
            <a href="#">Service</a>
            <a href="#">Contact</a>
        </nav>
    </header>

    <section>
        <img id="bg" src="c:\Users\Hp\OneDrive\Desktop\coding\parallax rest\bg.jpg" alt="bg">
        <img id="moon" src="c:\Users\Hp\OneDrive\Desktop\coding\parallax rest\moon.png" alt="moon">
        <img id="mountains" src="c:\Users\Hp\OneDrive\Desktop\coding\parallax rest\mountain.png" alt="mountains">
        <img id="road" src="c:\Users\Hp\OneDrive\Desktop\coding\parallax rest\road.png" alt="road">
        <h2 id="text">Moon Light</h2>
    </section>

    <script src="script.js"></script>
</body>
</html>



css
*{
    margin: 0;
    padding: 0;
    font-family: 'poppins' sans-serif ;
}

body{
    background:#0a2a43;
    min-height: 1500px;

}

header {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    padding: 30px 100px;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    z-index: 100;
}

.logo {
    font-size: 2em;
    color: #359381;
    font-weight: 600;
    margin-right: 400px;
}

.navigation a {
    text-decoration: none;
    color: #359381;
    padding: 6px 15px;
    border-radius: 20px;
    margin: 0px 10px;
    font-weight: 600;
}

.navigation a:hover, .navigation a.active {
    background: #359381;
    color: white;
}

section{
    position: relative;
    width: 100%;
    height: 100vh;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;

}

section::before{
    content: '';
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 100px;
    background: linear-gradient(to top #0a2a43 , transparent);
    z-index: 10000;
}

section::before{
    content: '';
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 100%;
    background: #0a2a43;
    z-index: 10000;
    mix-blend-mode: color;
}

section img{
    position:absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    pointer-events: none;
}

#text{
    position: relative;
    color: #fff;
    font-size: 10em;
    z-index: 1;
}
#road{
    z-index: 2;
}

js

let bg= document.getElementById("bg");
let moon= document.getElementById("moon");
let mountains= document.getElementById("mountains");
let road= document.getElementById("road");
let text= document.getElementById("text");

window.addEventListener('scroll', function(){
    var value=window.scrollY;
    bg.style.top = value* 0.5 +'px';
    moon.style.left = -value* 0.5 +'px';
    mountains.style.top = -value* 0.15 +'px';
    road.style.top = value* 0.15 +'px';
    text.style.top = value* 1 +'px';
}) 
