<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Фракталы: Геометрия Природы</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            color: #333;
        }
        header {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)),
                        url('https://images.unsplash.com/photo-1534972195531-d756b9bfa9f2') no-repeat center center fixed;
            background-size: cover;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: white;
            text-align: center;
        }
        nav {
            background: #2c3e50;
            padding: 1rem;
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-weight: bold;
        }
        .container {
            padding: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        .timeline {
            position: relative;
            max-width: 1200px;
            margin: 0 auto;
        }
        .timeline::after {
            content: '';
            position: absolute;
            width: 6px;
            background-color: #34495e;
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -3px;
        }
        .event {
            padding: 10px 40px;
            position: relative;
            background-color: inherit;
            width: 50%;
        }
        .event.left {
            left: 0;
        }
        .event.right {
            left: 50%;
        }
        .event::after {
            content: '';
            position: absolute;
            width: 25px;
            height: 25px;
            right: -17px;
            background-color: #fff;
            border: 4px solid #34495e;
            top: 15px;
            border-radius: 50%;
            z-index: 1;
        }
        .left::after {
            left: -16px;
        }
        .right::after {
            right: -17px;
        }
        .fractal-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1rem;
        }
        .fractal-item {
            border: 1px solid #ddd;
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.3s;
        }
        .fractal-item:hover {
            transform: scale(1.05);
        }
        .tabs {
            margin: 2rem 0;
        }
        .tablink {
            background-color: #34495e;
            color: white;
            padding: 12px 24px;
            border: none;
            cursor: pointer;
            margin: 5px;
            transition: 0.3s;
        }
        .tablink:hover {
            background-color: #2c3e50;
        }
        .tabcontent {
            display: none;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 0 0 8px 8px;
        }
        canvas {
            border: 1px solid #34495e;
            border-radius: 8px;
        }
        @media (max-width: 768px) {
            .timeline::after {
                left: 31px;
            }
            .event {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }
            .event.right {
                left: 0%;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>Фракталы: Геометрия Природы</h1>
        <p>Социальный проект Гусева Дмитрия, 10А класс</p>
    </header>

    <nav>
        <a href="#theory">Теория</a>
        <a href="#applications">Применение</a>
        <a href="#gallery">Галерея</a>
        <a href="#generator">Генератор</a>
        <a href="#literature">Литература</a>
    </nav>

    <div class="container" id="theory">
        <h2>Теоретическая часть</h2>
        
        <section>
            <h3>История фракталов</h3>
            <div class="timeline">
                <div class="event left">
                    <h4>1883: Георг Кантор</h4>
                    <p>Создание множества Кантора - первого математического фрактала</p>
                </div>
                <div class="event right">
                    <h4>1904: Хельге фон Кох</h4>
                    <p>Разработка кривой Коха</p>
                </div>
                <div class="event left">
                    <h4>1975: Бенуа Мандельброт</h4>
                    <p>Введение термина "фрактал" и публикация основополагающей работы</p>
                </div>
            </div>
        </section>
        
        <section>
            <h3>Классификация фракталов</h3>
            <div class="tabs">
                <button class="tablink" onclick="openTab('geometric')">Геометрические</button>
                <button class="tablink" onclick="openTab('algebraic')">Алгебраические</button>
                
                <div id="geometric" class="tabcontent">
                    <h4>Примеры:</h4>
                    <ul>
                        <li>Множество Кантора</li>
                        <li>Кривая Коха</li>
                        <li>Треугольник Серпинского</li>
                        <li>Кривая Пеано</li>
                    </ul>
                </div>
                
                <div id="algebraic" class="tabcontent">
                    <h4>Примеры:</h4>
                    <ul>
                        <li>Множество Мандельброта</li>
                        <li>Множество Жюлиа</li>
                    </ul>
                </div>
            </div>
        </section>
    </div>

    <div class="container" id="applications">
        <h2>Применение фракталов</h2>
        <div class="applications-grid">
            <div class="app-card">
                <h3>Компьютерная графика</h3>
                <p>Генерация ландшафтов, текстур и спецэффектов</p>
            </div>
            <div class="app-card">
                <h3>Медицина</h3>
                <p>Моделирование сосудов и анализ МРТ-снимков</p>
            </div>
            <div class="app-card">
                <h3>Финансы</h3>
                <p>Прогнозирование рыночных колебаний</p>
            </div>
            <div class="app-card">
                <h3>Телекоммуникации</h3>
                <p>Фрактальные антенны нового поколения</p>
            </div>
        </div>
    </div>

    <div class="container" id="gallery">
        <h2>Галерея фракталов</h2>
        <div class="fractal-gallery">
            <div class="fractal-item">
                <img src="https://images.unsplash.com/photo-1541746972996-4e0b0f4d34d0" alt="Романеско">
                <p>Романеско - природный фрактал</p>
            </div>
            <div class="fractal-item">
                <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/21/Mandel_zoom_00_mandelbrot_set.jpg/800px-Mandel_zoom_00_mandelbrot_set.jpg" alt="Множество Мандельброта">
                <p>Множество Мандельброта</p>
            </div>
            <div class="fractal-item">
                <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/Koch_snowflake_7th_iteration.svg/1200px-Koch_snowflake_7th_iteration.svg.png" alt="Снежинка Коха">
                <p>Кривая Коха (7 итераций)</p>
            </div>
            <div class="fractal-item">
                <img src="https://live.staticflickr.com/7090/7302882376_9d8f34d1c5_b.jpg" alt="Множество Жюлиа">
                <p>Множество Жюлиа</p>
            </div>
        </div>
    </div>

    <div class="container" id="generator">
        <h2>Генератор фракталов</h2>
        <div>
            <label for="iterations">Итерации:</label>
            <input type="range" id="iterations" min="1" max="6" value="3">
            <span id="iterValue">3</span>
            <canvas id="kochCanvas" width="600" height="200"></canvas>
        </div>
    </div>

    <div class="container" id="literature">
        <h2>Список литературы</h2>
        <ul>
            <li>Мандельброт Б. Фрактальная геометрия природы, 2002</li>
            <li>Балханов В.К. Основы фрактальной геометрии, 2013</li>
            <li>Федер Е. Фракталы, 1991</li>
        </ul>
    </div>

    <script>
        function openTab(tabName) {
            const tabs = document.getElementsByClassName("tabcontent");
            for (let tab of tabs) tab.style.display = "none";
            document.getElementById(tabName).style.display = "block";
        }

        const canvas = document.getElementById('kochCanvas');
        const ctx = canvas.getContext('2d');

        function drawKoch(iterations) {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.beginPath();
            ctx.moveTo(0, canvas.height/2);
            
            function koch(len, angle, depth) {
                if (depth === 0) {
                    ctx.lineTo(ctx.currentX + len * Math.cos(angle),
                              ctx.currentY + len * Math.sin(angle));
                    return;
                }
                len /= 3;
                koch(len, angle, depth-1);
                angle += Math.PI/3;
                koch(len, angle, depth-1);
                angle -= 2*Math.PI/3;
                koch(len, angle, depth-1);
                angle += Math.PI/3;
                koch(len, angle, depth-1);
            }
            
            koch(canvas.width, 0, iterations);
            ctx.stroke();
        }

        document.getElementById('iterations').addEventListener('input', (e) => {
            const value = parseInt(e.target.value);
            document.getElementById('iterValue').textContent = value;
            drawKoch(value);
        });

        document.querySelectorAll('.tablink')[0].click();
        drawKoch(3);
    </script>
</body>
</html>
