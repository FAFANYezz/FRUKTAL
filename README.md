<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Галерея изображений</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f5f5f5;
        }

        .gallery-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 15px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .gallery-item img {
            width: 100%;
            height: auto;
            display: block;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        .image-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(0,0,0,0.7);
            color: white;
            padding: 10px;
            text-align: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .gallery-item:hover .image-caption {
            opacity: 1;
        }

        @media (max-width: 768px) {
            .gallery-container {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
        }
    </style>
</head>
<body>
    <h1 style="text-align: center; color: #333;">Моя галерея</h1>
    
    <div class="gallery-container">
        <!-- Пример элемента галереи -->
        <div class="gallery-item">
            <img src="https://via.placeholder.com/300x200" alt="Пример изображения 1">
            <div class="image-caption">Описание изображения 1</div>
        </div>
        
        <div class="gallery-item">
            <img src="https://via.placeholder.com/300x200" alt="Пример изображения 2">
            <div class="image-caption">Описание изображения 2</div>
        </div>
        
        <div class="gallery-item">
            <img src="https://via.placeholder.com/300x200" alt="Пример изображения 3">
            <div class="image-caption">Описание изображения 3</div>
        </div>
        
        <!-- Добавьте больше элементов по аналогии -->
    </div>
</body>
</html>
