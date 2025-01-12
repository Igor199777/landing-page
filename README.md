# landing-page
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Перенаправлення...</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 50px;
        }
        button {
            background-color: #4CAF50; /* Зелений колір */
            color: white;
            border: none;
            padding: 15px 32px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            cursor: pointer;
            border-radius: 5px;
        }
        button:hover {
            background-color: #45a049; /* Темніший зелений при наведенні */
        }
    </style>
    <script>
        // Функція для отримання параметрів з URL
        function getQueryParams() {
            const urlParams = new URLSearchParams(window.location.search);
            return {
                sub_id_5: urlParams.get('sub_id_5')
            };
        }

        // Функція для відображення коду та налаштування кнопки
        function setupLandingPage() {
            const params = getQueryParams();

            // Якщо є параметр sub_id_5, показуємо його на сторінці
            if (params.sub_id_5) {
                document.getElementById('code').textContent = params.sub_id_5;

                // Генерація нового URL для кнопки
                const mainSiteUrl = `https://goldfms.store/7fykv1?sub_id_5=${params.sub_id_5}`;

                // Налаштування посилання для кнопки
                document.getElementById('redirectButton').onclick = function() {
                    window.location.href = mainSiteUrl;
                };
            } else {
                // Якщо параметр відсутній, показуємо повідомлення
                document.body.innerHTML = "<h1>Некоректний код. Спробуйте ще раз.</h1>";
            }
        }

        // Запуск функції при завантаженні сторінки
        window.onload = setupLandingPage;
    </script>
</head>
<body>
    <h1>Вітаємо! Ваш код:</h1>
    <p id="code" style="font-size: 24px; font-weight: bold;">Завантаження коду...</p>
    <p>Клацніть на кнопку нижче для переходу:</p>
    <button id="redirectButton">Перейти на сайт</button>
</body>
</html>
