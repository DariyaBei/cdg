<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Свадебное приглашение</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display&family=Montserrat&display=swap" rel="stylesheet">

<style>
body {
    margin:0;
    font-family:'Montserrat', sans-serif;
    background:#f3f3f3;
    color:#222;
}

h1,h2 {
    font-family:'Playfair Display', serif;
}

section {
    padding:60px 20px;
    text-align:center;
}

/* ОБЛОЖКА */
.hero {
    height:100vh;
    background:url('https://drive.google.com/file/d/1rnHhPRFA5JbGUZxCi33648fJEuYD8QXT/view?usp=drive_link') center/cover no-repeat;

    display:flex;
    flex-direction:column;
    justify-content:center;
    color:white;
    position:relative;
}

.hero::after {
    content:"";
    position:absolute;
    inset:0;
    background:rgba(0,0,0,0.4);
}

.hero * {
    position:relative;
    z-index:1;
}

/* СЕРЫЙ ФОН */
.gray {
    background:#e7e7e7;
}

/* ФОТО ДАТЫ */
.date img {
    width:150px;
    margin-top:15px;
    border-radius:14px;
}

/* ТАЙМЕР */
.timer {
    margin-top:15px;
    font-size:20px;
}

/* ТАЙМИНГ */
.timeline {
    display:flex;
    flex-wrap:wrap;
    justify-content:center;
    gap:10px;
    margin-top:30px;
}

.step {
    background:white;
    padding:12px 16px;
    border-radius:30px;
}

.arrow {
    font-size:18px;
}

/* КАРТА */
.map iframe {
    width:100%;
    height:260px;
    border:none;
    border-radius:14px;
}

/* ДРЕСС-КОД */
.dress {
    background:url('https://drive.google.com/file/d/1H4_Iyioa52-RHiCb6Nzaqj34i2PI_j4A/view?usp=drive_link') center/cover no-repeat;
    color:white;
}

.colors {
    display:flex;
    justify-content:center;
    gap:12px;
    flex-wrap:wrap;
    margin-top:20px;
}

.color {
    width:55px;
    height:55px;
    border-radius:50%;
    border:2px solid white;
}

/* КНОПКА */
button {
    padding:15px;
    width:90%;
    max-width:320px;
    border:none;
    border-radius:30px;
    background:black;
    color:white;
}

/* АНИМАЦИЯ */
.fade {
    opacity:0;
    transform:translateY(40px);
    transition:1s;
}

.fade.show {
    opacity:1;
    transform:translateY(0);
}
</style>
</head>

<body>

<!-- ОБЛОЖКА -->
<section class="hero">
    <h1>Дарья & Сергей</h1>
    <p>
        Дорогие наши родные и друзья!<b
       Приглашаем вас на нашу свадьбу
    </p>
</section>

<!-- ДАТА -->
<section class="gray date fade">
    <h2>20 августа 2026</h2>
    <img src="https://drive.google.com/file/d/1LK3IIja6OupMa-0ykw8tbYjfm3PZFzIx/view?usp=drive_link">

    <div class="timer" id="timer"></div>
</section>

<!-- ТАЙМИНГ -->
<section class="fade">
    <h2>Тайминг</h2>
    <div class="timeline">
        <div class="step">12:00<br
емония</div>
        <div class="arrow">→</div>
        <div class="step">13:00<br
о</div>
        <div class="arrow">→</div>
        <div class="step">17:00<br
н</div>
        <div class="arrow">→</div>
        <div class="step">23:00<br
ал</div>
    </div>
</section>

<!-- МЕСТО -->
<section class="gray map fade">
    <h2>Место проведения</h2>
    <p>Управление ЗАГС</p>

    <!-- карта -->
    <iframe src="https://maps.google.com/maps?q=Белгород%20Попова%2014&output=embed"></iframe>
</section>

<!-- ДРЕСС-КОД -->
<section class="dress fade">
    <h2>Дресс-код</h2>
    <p>Поддержите цветовую гамму праздника</p>

    <div class="colors">
        <div class="color" style="background:#f8c8dc"></div>
        <div class="color" style="background:#cde7ff"></div>
        <div class="color" style="background:#fff5ba"></div>
        <div class="color" style="background:#d4f5d0"></div>
        <div class="color" style="background:#808000"></div>
    </div>
</section>

<!-- КНОПКА -->
<section class="gray fade">
    <button onclick="window.location.href='https://forms.gle/wBGfkj6pEau3Drqj9'">
        Подтвердить присутствие
    </button>
</section>

<!-- ФИНАЛ -->
<section class="fade">
    <h2>С нетерпением ждём вас!</h2>
</section>

<script>
/* таймер */
const date = new Date("Aug 20, 2026 00:00:00").getTime();

setInterval(() => {
    const now = new Date().getTime();
    const diff = date - now;
onst d = Math.floor(diff/(1000*60*60*24));
    const h = Math.floor((diff%(1000*60*60*24))/(1000*60*60));
    const m = Math.floor((diff%(1000*60*60))/(1000*60));

    document.getElementById("timer").innerHTML =
        d+" дней "+h+" ч "+m+" мин";
},1000);

/* анимации */
const elements = document.querySelectorAll('.fade');

const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
        if(entry.isIntersecting){
            entry.target.classList.add('show');
        }
    });
});

elements.forEach(el => observer.observe(el));
</script>

</body>
</html> 
