<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Фракталы: Геометрия Природы</title>
    <style>
        /* Базовые стили */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            line-height: 1.6;
            color: #333;
        }
        header {
            background: #2c3e50;
            color: white;
            padding: 20px 0;
            text-align: center;
        }
        nav {
            background: #34495e;
            padding: 10px;
            text-align: center;
        }
        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
        }
        .container {
            padding: 20px;
        }
        .fractal-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 15px;
        }
        .fractal-item {
            border: 1px solid #ddd;
            padding: 15px;
            text-align: center;
        }
        .fractal-item img {
            max-width: 100%;
            height: auto;
        }
        /* Анимированный фон */
        .hero {
            background: url('https://images.unsplash.com/photo-1534972195531-d756b9bfa9f2') no-repeat center center fixed;
            background-size: cover;
            height: 400px;
            position: relative;
        }
        .hero-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: white;
            text-align: center;
        }
    </style>
</head>
<body>
    <header>
        <div class="hero">
            <div class="hero-content">
                <h1>Фракталы</h1>
                <p>Геометрия хаоса и бесконечности</p>
            </div>
        </div>
        <nav>
            <a href="#theory">Теория</a>
            <a href="#applications">Применение</a>
            <a href="#gallery">Галерея</a>
            <a href="#generator">Генератор</a>
        </nav>
    </header>

    <div class="container" id="theory">
        <h2>Теоретическая часть</h2>
        
        <section>
            <h3>История фракталов</h3>
            <div class="timeline">
                <div class="event">
                    <h4>1883: Георг Кантор</h4>
                    <p>Открыл множество Кантора - первый математический фрактал</p>
                </div>
                <div class="event">
                    <h4>1975: Бенуа Мандельброт</h4>
                    <p>Ввел термин "фрактал" и опубликовал книгу "Фрактальная геометрия природы"</p>
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
                <p>Генерация реалистичных ландшафтов и текстур</p>
            </div>
            <div class="app-card">
                <h3>Медицина</h3>
                <p>Анализ МРТ-снимков и моделирование сосудов</p>
            </div>
            <div class="app-card">
                <h3>Финансы</h3>
                <p>Прогнозирование рыночных тенденций</p>
            </div>
        </div>
    </div>

    <div class="container" id="gallery">
        <h2>Галерея</h2>
        <div class="fractal-gallery">
            <div class="fractal-item">
                <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/21/Mandel_zoom_00_mandelbrot_set.jpg/800px-Mandel_zoom_00_mandelbrot_set.jpg" alt="Множество Мандельброта">
                <p>Множество Мандельброта</p>
            </div>
            <div class="fractal-item">
                <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/Koch_snowflake_7th_iteration.svg/1200px-Koch_snowflake_7th_iteration.svg.png" alt="Кривая Коха">
                <p>Снежинка Коха</p>
            </div>
        </div>
    </div>

    <div class="container" id="generator">
        <h2>Генератор фракталов</h2>
        <div>
            <label for="iterations">Количество итераций:</label>
            <input type="range" id="iterations" min="1" max="6" value="3">
            <span id="iterValue">3</span>
            <canvas id="kochCanvas" width="600" height="200"></canvas>
        </div>
    </div>

    <script>
        // Пример генератора кривой Коха
        const canvas = document.getElementById('kochCanvas');
        const ctx = canvas.getContext('2d');

        function drawKoch(iterations, ctx) {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.beginPath();
            ctx.moveTo(0, canvas.height/2);
            
            function kochCurve(len, angle, iterations) {
                if (iterations === 0) {
                    ctx.lineTo(ctx.currentX + len * Math.cos(angle),
                              ctx.currentY + len * Math.sin(angle));
                    return;
                }
                len /= 3;
                kochCurve(len, angle, iterations-1);
                angle += Math.PI/3;
                kochCurve(len, angle, iterations-1);
                angle -= 2*Math.PI/3;
                kochCurve(len, angle, iterations-1);
                angle += Math.PI/3;
                kochCurve(len, angle, iterations-1);
            }
            
            kochCurve(canvas.width, 0, iterations);
            ctx.stroke();
        }

        document.getElementById('iterations').addEventListener('input', (e) => {
            const value = parseInt(e.target.value);
            document.getElementById('iterValue').textContent = value;
            drawKoch(value, ctx);
        });

        // Инициализация
        drawKoch(3, ctx);
    </script>
</body>
</html>
