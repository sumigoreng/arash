<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Happy Birthday</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: 'Poppins', sans-serif;
}

body{
    background:black;
    overflow-x:hidden;
    color:white;
}

section{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    position:relative;
}

.scroll-text{
    font-size:3rem;
    font-weight:bold;
    opacity:0;
    transform:translateY(100px);
    transition:1s ease;
}

.scroll-text.show{
    opacity:1;
    transform:translateY(0);
}

.glow{
    color:white;
    text-shadow:
    0 0 10px white,
    0 0 20px white,
    0 0 40px white,
    0 0 80px white;
}

.number{
    font-size:8rem;
    animation:float 2s infinite ease-in-out;
}

@keyframes float{
    0%{transform:translateY(0px);}
    50%{transform:translateY(-20px);}
    100%{transform:translateY(0px);}
}

.stars{
    position:absolute;
    width:100%;
    height:100%;
    overflow:hidden;
    top:0;
    left:0;
}

.stars span{
    position:absolute;
    width:2px;
    height:100px;
    background:linear-gradient(transparent, white);
    animation:rain 3s linear infinite;
    opacity:0.5;
}

@keyframes rain{
    0%{
        transform:translateY(-100vh);
    }
    100%{
        transform:translateY(100vh);
    }
}

.final-text{
    font-size:4rem;
    text-align:center;
    padding:20px;
}

small{
    margin-top:15px;
    opacity:0.7;
}
</style>
</head>
<body>

<div class="stars"></div>

<section>
    <div class="scroll-text number glow">3</div>
</section>

<section>
    <div class="scroll-text number glow">2</div>
</section>

<section>
    <div class="scroll-text number glow">1</div>
</section>

<section>
    <div class="scroll-text final-text glow">
        Happy Birthday ❤️
        <br>
        Sayangkuu 🎂
        <br>
        <small>scroll lagi hehe ↓</small>
    </div>
</section>

<script>
const texts = document.querySelectorAll('.scroll-text');

window.addEventListener('scroll', () => {
    texts.forEach(text => {
        const position = text.getBoundingClientRect().top;
        const screen = window.innerHeight / 1.3;

        if(position < screen){
            text.classList.add('show');
        }
    });
});

const stars = document.querySelector('.stars');

for(let i = 0; i < 80; i++){
    let star = document.createElement('span');

    star.style.left = Math.random() * 100 + 'vw';
    star.style.animationDuration = (Math.random() * 2 + 2) + 's';
    star.style.animationDelay = Math.random() * 5 + 's';

    stars.appendChild(star);
}
</script>

</body>
</html>
