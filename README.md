# RustInsaid
Информация о рейдах в раст
[deepseek_html_20251128_57a75a.html](https://github.com/user-attachments/files/23827726/deepseek_html_20251128_57a75a.html)
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rust Raids - Гайд по рейдам в Rust</title>
    <style>
        :root {
            --primary: #e74c3c;
            --primary-dark: #c0392b;
            --secondary: #2c3e50;
            --light: #ecf0f1;
            --dark: #1a1a1a;
            --success: #27ae60;
            --warning: #f39c12;
            --gray: #7f8c8d;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--dark);
            color: var(--light);
            line-height: 1.6;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header */
        header {
            background-color: var(--secondary);
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            color: var(--primary);
        }
        
        .logo-img {
            width: 40px;
            height: 40px;
            background-color: var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 20px;
        }
        
        nav a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
            padding: 5px 10px;
            border-radius: 4px;
        }
        
        nav a:hover, nav a.active {
            color: var(--primary);
            background-color: rgba(255, 255, 255, 0.1);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), 
                        #34495e;
            height: 350px;
            display: flex;
            align-items: center;
            text-align: center;
            padding: 0 20px;
        }
        
        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            color: var(--light);
        }
        
        .btn {
            display: inline-block;
            background-color: var(--primary);
            color: white;
            padding: 10px 25px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: var(--primary-dark);
        }
        
        /* Main Content */
        main {
            padding: 3rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 2rem;
            color: var(--primary);
            font-size: 2rem;
        }
        
        .section-subtitle {
            text-align: center;
            margin-bottom: 1.5rem;
            color: var(--warning);
            font-size: 1.5rem;
        }
        
        /* Calculator */
        .calculator {
            background-color: #2d2d2d;
            border-radius: 8px;
            padding: 25px;
            margin-bottom: 3rem;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }
        
        .calculator-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .calculator-item {
            background-color: #3d3d3d;
            padding: 15px;
            border-radius: 5px;
        }
        
        .calculator-item label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: var(--warning);
        }
        
        .calculator-item select, .calculator-item input {
            width: 100%;
            padding: 10px;
            border-radius: 4px;
            border: 1px solid #555;
            background-color: #2d2d2d;
            color: var(--light);
        }
        
        .calculator-results {
            background-color: #3d3d3d;
            padding: 20px;
            border-radius: 5px;
            margin-top: 20px;
        }
        
        .results-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
        }
        
        .result-item {
            text-align: center;
            padding: 10px;
            background-color: #2d2d2d;
            border-radius: 5px;
        }
        
        .result-value {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary);
            margin: 5px 0;
        }
        
        /* Tables */
        .tables-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 3rem;
        }
        
        .table-container {
            background-color: #2d2d2d;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }
        
        .table-header {
            padding: 15px;
            background-color: var(--secondary);
            text-align: center;
            font-weight: bold;
            color: var(--primary);
        }
        
        .table-content {
            padding: 0;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        th, td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #3d3d3d;
        }
        
        th {
            background-color: #3d3d3d;
            color: var(--warning);
        }
        
        tr:hover {
            background-color: #3d3d3d;
        }
        
        /* Strategy Cards */
        .strategy-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 3rem;
        }
        
        .strategy-card {
            background-color: #2d2d2d;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s;
        }
        
        .strategy-card:hover {
            transform: translateY(-5px);
        }
        
        .strategy-header {
            padding: 15px;
            background-color: var(--secondary);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .strategy-title {
            font-size: 1.3rem;
            color: var(--primary);
        }
        
        .strategy-difficulty {
            background-color: var(--warning);
            color: white;
            padding: 5px 10px;
            border-radius: 4px;
            font-weight: bold;
            font-size: 0.8rem;
        }
        
        .strategy-content {
            padding: 20px;
        }
        
        .strategy-features {
            list-style-type: none;
            margin-top: 15px;
        }
        
        .strategy-features li {
            padding: 5px 0;
            border-bottom: 1px solid #3d3d3d;
        }
        
        .strategy-features li:before {
            content: "•";
            color: var(--primary);
            font-weight: bold;
            display: inline-block;
            width: 1em;
            margin-left: -1em;
        }
        
        /* Tips Section */
        .tips-container {
            background-color: #2d2d2d;
            border-radius: 8px;
            padding: 25px;
            margin-bottom: 3rem;
        }
        
        .tips-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .tip-item {
            background-color: #3d3d3d;
            padding: 15px;
            border-radius: 5px;
            border-left: 4px solid var(--primary);
        }
        
        .tip-item h4 {
            color: var(--warning);
            margin-bottom: 10px;
        }
        
        /* Footer */
        footer {
            background-color: var(--secondary);
            padding: 2rem 0;
            text-align: center;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-links a {
            color: var(--light);
            font-size: 1.5rem;
            transition: color 0.3s;
        }
        
        .social-links a:hover {
            color: var(--primary);
        }
        
        .copyright {
            color: #bdc3c7;
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 15px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero h2 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <div class="logo-img">R</div>
                    <h1>Rust Raids</h1>
                </div>
                <nav>
                    <ul>
                        <li><a href="#" class="active">Главная</a></li>
                        <li><a href="#calculator">Калькулятор</a></li>
                        <li><a href="#methods">Методы рейдов</a></li>
                        <li><a href="#strategies">Стратегии</a></li>
                        <li><a href="#tips">Советы</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h2>Полное руководство по рейдам в Rust</h2>
                <p>Узнайте все о рейдах в Rust: методы, расчет ресурсов, стратегии и советы для успешных атак на базы.</p>
                <a href="#calculator" class="btn">Рассчитать ресурсы</a>
            </div>
        </div>
    </section>

    <main class="container">
        <section id="calculator">
            <h2 class="section-title">Калькулятор рейдов</h2>
            <div class="calculator">
                <div class="calculator-grid">
                    <div class="calculator-item">
                        <label for="wall-material">Материал стены:</label>
                        <select id="wall-material">
                            <option value="wood">Дерево</option>
                            <option value="stone">Камень</option>
                            <option value="metal">Металл</option>
                            <option value="armored">Броня</option>
                        </select>
                    </div>
                    <div class="calculator-item">
                        <label for="wall-count">Количество стен:</label>
                        <input type="number" id="wall-count" min="1" max="20" value="1">
                    </div>
                    <div class="calculator-item">
                        <label for="raid-method">Метод рейда:</label>
                        <select id="raid-method">
                            <option value="explosives">Взрывчатка</option>
                            <option value="rockets">Ракеты</option>
                            <option value="c4">C4</option>
                            <option value="satchels">Саше</option>
                            <option value="beancan">Бобовые гранаты</option>
                            <option value="melee">Ближний бой</option>
                        </select>
                    </div>
                </div>
                <button class="btn" style="width: 100%;" onclick="calculateRaid()">Рассчитать</button>
                
                <div class="calculator-results">
                    <h3 style="text-align: center; margin-bottom: 15px; color: var(--warning);">Результаты расчета</h3>
                    <div class="results-grid">
                        <div class="result-item">
                            <div>Нужно предметов:</div>
                            <div class="result-value" id="item-count">0</div>
                        </div>
                        <div class="result-item">
                            <div>Общая стоимость:</div>
                            <div class="result-value" id="total-cost">0</div>
                            <div>серы</div>
                        </div>
                        <div class="result-item">
                            <div>Время рейда:</div>
                            <div class="result-value" id="raid-time">0</div>
                            <div>секунд</div>
                        </div>
                        <div class="result-item">
                            <div>Шумность:</div>
                            <div class="result-value" id="raid-noise">Низкая</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="methods">
            <h2 class="section-title">Методы рейдов</h2>
            <h3 class="section-subtitle">Сравнение эффективности</h3>
            
            <div class="tables-grid">
                <div class="table-container">
                    <div class="table-header">Взрывчатка</div>
                    <div class="table-content">
                        <table>
                            <thead>
                                <tr>
                                    <th>Материал</th>
                                    <th>C4</th>
                                    <th>Ракеты</th>
                                    <th>Саше</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>Дерево</td>
                                    <td>1</td>
                                    <td>2</td>
                                    <td>4</td>
                                </tr>
                                <tr>
                                    <td>Камень</td>
                                    <td>2</td>
                                    <td>4</td>
                                    <td>10</td>
                                </tr>
                                <tr>
                                    <td>Металл</td>
                                    <td>4</td>
                                    <td>8</td>
                                    <td>20</td>
                                </tr>
                                <tr>
                                    <td>Броня</td>
                                    <td>8</td>
                                    <td>16</td>
                                    <td>40</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
                
                <div class="table-container">
                    <div class="table-header">Стоимость (сера)</div>
                    <div class="table-content">
                        <table>
                            <thead>
                                <tr>
                                    <th>Метод</th>
                                    <th>За штуку</th>
                                    <th>Дерево</th>
                                    <th>Камень</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>C4</td>
                                    <td>2200</td>
                                    <td>2200</td>
                                    <td>4400</td>
                                </tr>
                                <tr>
                                    <td>Ракеты</td>
                                    <td>1400</td>
                                    <td>2800</td>
                                    <td>5600</td>
                                </tr>
                                <tr>
                                    <td>Саше</td>
                                    <td>480</td>
                                    <td>1920</td>
                                    <td>4800</td>
                                </tr>
                                <tr>
                                    <td>Бобовые</td>
                                    <td>240</td>
                                    <td>960</td>
                                    <td>2400</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </section>

        <section id="strategies">
            <h2 class="section-title">Стратегии рейдов</h2>
            
            <div class="strategy-cards">
                <div class="strategy-card">
                    <div class="strategy-header">
                        <div class="strategy-title">Ранняя игра</div>
                        <div class="strategy-difficulty">Низкая</div>
                    </div>
                    <div class="strategy-content">
                        <p>Идеально для начала игры, когда ресурсы ограничены.</p>
                        <ul class="strategy-features">
                            <li>Используйте бобовые гранаты</li>
                            <li>Атакуйте деревянные базы</li>
                            <li>Рейдите ночью для скрытности</li>
                            <li>Минимальные затраты серы</li>
                        </ul>
                    </div>
                </div>
                
                <div class="strategy-card">
                    <div class="strategy-header">
                        <div class="strategy-title">Средняя игра</div>
                        <div class="strategy-difficulty">Средняя</div>
                    </div>
                    <div class="strategy-content">
                        <p>Баланс между стоимостью и эффективностью.</p>
                        <ul class="strategy-features">
                            <li>Саше против каменных стен</li>
                            <li>Используйте взрывные патроны</li>
                            <li>Комбинируйте методы</li>
                            <li>Рейдите в небольших группах</li>
                        </ul>
                    </div>
                </div>
                
                <div class="strategy-card">
                    <div class="strategy-header">
                        <div class="strategy-title">Поздняя игра</div>
                        <div class="strategy-difficulty">Высокая</div>
                    </div>
                    <div class="strategy-content">
                        <p>Максимальная эффективность против укрепленных баз.</p>
                        <ul class="strategy-features">
                            <li>Используйте C4 и ракеты</li>
                            <li>Атакуйте металлические и бронированные базы</li>
                            <li>Координированные атаки большой группой</li>
                            <li>Используйте вертолеты и транспорт</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section id="tips">
            <h2 class="section-title">Советы по рейдам</h2>
            
            <div class="tips-container">
                <div class="tips-list">
                    <div class="tip-item">
                        <h4>Разведка</h4>
                        <p>Перед рейдом изучите базу: найдите слабые места, определите активность игроков.</p>
                    </div>
                    <div class="tip-item">
                        <h4>Время атаки</h4>
                        <p>Рейдите, когда владельцы базы наименее активны - рано утром или поздно ночью.</p>
                    </div>
                    <div class="tip-item">
                        <h4>Приоритеты</h4>
                        <p>Сначала уничтожайте турели и ловушки, затем стены к наиболее ценным комнатам.</p>
                    </div>
                    <div class="tip-item">
                        <h4>Безопасность</h4>
                        <p>Всегда оставляйте одного игрока для прикрытия и быстрого отступления.</p>
                    </div>
                    <div class="tip-item">
                        <h4>Эффективность</h4>
                        <p>Используйте калькулятор для точного расчета необходимых ресурсов.</p>
                    </div>
                    <div class="tip-item">
                        <h4>Шум</h4>
                        <p>Учитывайте шумность методов - тихие рейды имеют больше шансов на успех.</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="social-links">
                    <a href="#" aria-label="VKontakte">VK</a>
                    <a href="#" aria-label="Telegram">TG</a>
                    <a href="#" aria-label="YouTube">YT</a>
                    <a href="#" aria-label="Discord">DS</a>
                </div>
                <p class="copyright">© 2023 Rust Raids. Все права защищены. Этот сайт не аффилирован с Facepunch Studios.</p>
            </div>
        </div>
    </footer>

    <script>
        // Данные для расчета рейдов
        const raidData = {
            wood: { c4: 1, rockets: 2, satchels: 4, beancan: 8, melee: 50, explosives: 2 },
            stone: { c4: 2, rockets: 4, satchels: 10, beancan: 20, melee: 150, explosives: 4 },
            metal: { c4: 4, rockets: 8, satchels: 20, beancan: 40, melee: 300, explosives: 8 },
            armored: { c4: 8, rockets: 16, satchels: 40, beancan: 80, melee: 500, explosives: 16 }
        };
        
        const costData = {
            c4: 2200,
            rockets: 1400,
            satchels: 480,
            beancan: 240,
            melee: 0,
            explosives: 1100
        };
        
        const timeData = {
            c4: 10,
            rockets: 8,
            satchels: 15,
            beancan: 20,
            melee: 30,
            explosives: 12
        };
        
        const noiseData = {
            c4: "Очень высокий",
            rockets: "Высокий",
            satchels: "Средний",
            beancan: "Низкий",
            melee: "Тихий",
            explosives: "Высокий"
        };
        
        function calculateRaid() {
            const wallMaterial = document.getElementById('wall-material').value;
            const wallCount = parseInt(document.getElementById('wall-count').value);
            const raidMethod = document.getElementById('raid-method').value;
            
            const itemsNeeded = raidData[wallMaterial][raidMethod] * wallCount;
            const totalCost = costData[raidMethod] * itemsNeeded;
            const totalTime = timeData[raidMethod] * itemsNeeded;
            const noiseLevel = noiseData[raidMethod];
            
            document.getElementById('item-count').textContent = itemsNeeded;
            document.getElementById('total-cost').textContent = totalCost.toLocaleString();
            document.getElementById('raid-time').textContent = totalTime;
            document.getElementById('raid-noise').textContent = noiseLevel;
        }
        
        // Инициализация калькулятора
        document.addEventListener('DOMContentLoaded', function() {
            calculateRaid();
        });
        
        // Плавная прокрутка
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
