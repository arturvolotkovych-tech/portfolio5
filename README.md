# portfolio5<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🚀 Мої досягнення - Інформатика</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            min-height: 100vh;
            padding: 20px;
            color: #fff;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border-radius: 30px;
            padding: 40px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.6);
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
        }

        .header .avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3.5rem;
            border: 4px solid rgba(255, 255, 255, 0.3);
            animation: float 3s ease-in-out infinite;
            box-shadow: 0 10px 40px rgba(102, 126, 234, 0.4);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .header h1 {
            font-size: 2.8rem;
            background: linear-gradient(135deg, #667eea, #764ba2, #f093fb);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .header .subtitle {
            color: rgba(255, 255, 255, 0.7);
            font-size: 1.2rem;
            margin-top: 5px;
        }

        .badge-group {
            margin-top: 15px;
            display: flex;
            justify-content: center;
            gap: 10px;
            flex-wrap: wrap;
        }

        .badge {
            display: inline-block;
            padding: 6px 18px;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 600;
            background: rgba(102, 126, 234, 0.3);
            border: 1px solid rgba(102, 126, 234, 0.5);
            color: #a8b5ff;
            transition: all 0.3s;
            cursor: default;
        }

        .badge:hover {
            background: rgba(102, 126, 234, 0.5);
            transform: scale(1.05);
        }

        .badge.gold {
            background: rgba(255, 215, 0, 0.2);
            border-color: #ffd700;
            color: #ffd700;
        }

        .section {
            margin-bottom: 40px;
        }

        .section h2 {
            font-size: 1.6rem;
            margin-bottom: 20px;
            color: #a8b5ff;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 25px;
            border: 2px solid rgba(255, 255, 255, 0.08);
            transition: all 0.4s;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            text-align: center;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(135deg, #667eea, #764ba2, #f093fb);
            border-radius: 20px;
            opacity: 0;
            transition: opacity 0.4s;
            z-index: -1;
        }

        .project-card:hover::before {
            opacity: 1;
        }

        .project-card:hover {
            transform: translateY(-8px) scale(1.02);
            border-color: transparent;
        }

        .project-card .emoji {
            font-size: 3.5rem;
            display: block;
            margin-bottom: 15px;
        }

        .project-card h3 {
            font-size: 1.3rem;
            color: #fff;
            margin-bottom: 8px;
        }

        .project-card p {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.95rem;
            line-height: 1.5;
            margin-bottom: 12px;
        }

        .project-card .tag {
            display: inline-block;
            padding: 4px 16px;
            border-radius: 50px;
            font-size: 0.7rem;
            font-weight: 600;
            background: rgba(102, 126, 234, 0.3);
            color: #a8b5ff;
            border: 1px solid rgba(102, 126, 234, 0.3);
        }

        .project-card .click-hint {
            display: inline-block;
            margin-top: 12px;
            padding: 5px 15px;
            background: rgba(255, 215, 0, 0.15);
            border-radius: 20px;
            color: #ffd700;
            font-size: 0.75rem;
            font-weight: 600;
            border: 1px solid rgba(255, 215, 0, 0.2);
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(10px);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            padding: 20px;
            animation: fadeIn 0.3s ease;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: #1a1a2e;
            border-radius: 30px;
            max-width: 600px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            padding: 35px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.8);
            position: relative;
        }

        .modal-close {
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 2rem;
            color: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: all 0.3s;
            background: none;
            border: none;
        }

        .modal-close:hover {
            color: #fff;
            transform: rotate(90deg);
        }

        .modal-content h2 {
            color: #a8b5ff;
            font-size: 1.8rem;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .modal-content .modal-emoji {
            font-size: 3rem;
            text-align: center;
            margin-bottom: 15px;
        }

        .modal-content .modal-desc {
            color: rgba(255, 255, 255, 0.7);
            font-size: 1.05rem;
            line-height: 1.7;
            margin-bottom: 20px;
        }

        .modal-content .modal-tech {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
            margin-bottom: 20px;
        }

        .modal-content .modal-tech span {
            padding: 4px 14px;
            background: rgba(102, 126, 234, 0.2);
            border-radius: 20px;
            font-size: 0.8rem;
            color: #a8b5ff;
        }

        .modal-content .modal-btn {
            display: inline-block;
            padding: 12px 35px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: #fff;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 5px 25px rgba(102, 126, 234, 0.3);
        }

        .modal-content .modal-btn:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 8px 40px rgba(102, 126, 234, 0.5);
        }

        .game-container {
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }

        .guess-game input {
            padding: 12px 20px;
            border-radius: 10px;
            border: 2px solid rgba(255, 255, 255, 0.1);
            background: rgba(255, 255, 255, 0.05);
            color: #fff;
            font-size: 1rem;
            width: 100%;
            max-width: 200px;
            margin: 10px 0;
            outline: none;
            transition: border-color 0.3s;
        }

        .guess-game input:focus {
            border-color: #667eea;
        }

        .guess-game .guess-btn {
            padding: 12px 30px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: #fff;
            border: none;
            border-radius: 10px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s;
        }

        .guess-game .guess-btn:hover {
            transform: scale(1.05);
        }

        .guess-game .message {
            margin: 15px 0;
            padding: 15px;
            border-radius: 10px;
            font-weight: 600;
            min-height: 50px;
        }

        .guess-game .message.success {
            background: rgba(76, 175, 80, 0.2);
            border: 1px solid #4caf50;
            color: #81c784;
        }

        .guess-game .message.error {
            background: rgba(244, 67, 54, 0.2);
            border: 1px solid #f44336;
            color: #ef9a9a;
        }

        .guess-game .message.info {
            background: rgba(33, 150, 243, 0.2);
            border: 1px solid #2196f3;
            color: #64b5f6;
        }

        .guess-game .attempts {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.9rem;
            margin-top: 10px;
        }

        .guess-game .reset-btn {
            padding: 8px 20px;
            background: rgba(255, 255, 255, 0.1);
            color: #fff;
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
            margin-left: 10px;
        }

        .guess-game .reset-btn:hover {
            background: rgba(255, 255, 255, 0.2);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            text-align: center;
        }

        .stat-item {
            background: rgba(255, 255, 255, 0.03);
            padding: 20px;
            border-radius: 16px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s;
        }

        .stat-item:hover {
            border-color: rgba(102, 126, 234, 0.3);
            transform: scale(1.02);
        }

        .stat-item .number {
            font-size: 2.8rem;
            font-weight: 800;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-item .label {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.9rem;
            margin-top: 4px;
        }

        .btn {
            display: inline-block;
            padding: 14px 40px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: #fff;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 5px 25px rgba(102, 126, 234, 0.4);
        }

        .btn:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 8px 40px rgba(102, 126, 234, 0.6);
        }

        #surprise {
            display: none;
            margin-top: 30px;
            padding: 30px;
            background: linear-gradient(135deg, rgba(255, 215, 0, 0.1), rgba(255, 107, 107, 0.1));
            border-radius: 20px;
            border: 2px solid rgba(255, 215, 0, 0.3);
            text-align: center;
            animation: fadeIn 0.6s ease;
        }

        #surprise .big {
            font-size: 4rem;
            margin: 10px 0;
        }

        #surprise h2 {
            color: #ffd700;
            font-size: 2rem;
        }

        #surprise p {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-20px) scale(0.95); }
            to { opacity: 1; transform: translateY(0) scale(1); }
        }

        .footer {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            color: rgba(255, 255, 255, 0.3);
            font-size: 0.9rem;
        }

        @media (max-width: 600px) {
            .container { padding: 20px; }
            .header h1 { font-size: 2rem; }
            .header .avatar { width: 90px; height: 90px; font-size: 2.8rem; }
            .projects-grid { grid-template-columns: 1fr; }
            .stats-grid { grid-template-columns: 1fr 1fr; }
            .modal-content { padding: 20px; }
        }

        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 10px;
        }
    </style>
</head>
<body>

    <div class="container">

        <div class="header">
            <div class="avatar">🚀</div>
            <h1>Мої досягнення</h1>
            <p class="subtitle">🌟 7-Б клас · Програміст · Креатор</p>
            <div class="badge-group">
                <span class="badge">💻 Веб-розробка</span>
                <span class="badge">🐍 Python</span>
                <span class="badge">📱 Telegram боти</span>
                <span class="badge gold">⭐ Відмінник</span>
            </div>
        </div>

        <div class="section">
            <h2>👤 Про мене</h2>
            <div style="background: rgba(255,255,255,0.03); border-radius: 16px; padding: 20px;">
                <p style="color: rgba(255,255,255,0.8); font-size: 1.05rem; line-height: 1.7;">
                    Привіт! Я — учень 7-Б класу, який <strong style="color: #a8b5ff;">обожнює програмування</strong>. 
                    Це моє портфоліо, де зібрані всі мої проекти. 
                    <strong style="color: #ffd700;">Натискай на картки — і пограй!</strong> 🎮
                </p>
            </div>
        </div>

        <div class="section">
            <h2>💻 Мої проекти (натисни на картку)</h2>
            <div class="projects-grid">

                <div class="project-card" onclick="openModal('guess')">
                    <span class="emoji">🎯</span>
                    <h3>Вгадай число</h3>
                    <p>Комп'ютер загадує число, а ти вгадуєш. Підказки та лічильник спроб!</p>
                    <span class="tag">JavaScript</span>
                    <span class="click-hint">👆 Клікни, щоб грати</span>
                </div>

                <div class="project-card" onclick="openModal('calc')">
                    <span class="emoji">🧮</span>
                    <h3>Калькулятор</h3>
                    <p>Звичайний калькулятор з усіма діями. Працює як на телефоні!</p>
                    <span class="tag">JavaScript</span>
                    <span class="click-hint">👆 Клікни, щоб грати</span>
                </div>

                <div class="project-card" onclick="openModal('test')">
                    <span class="emoji">📝</span>
                    <h3>Тест з інформатики</h3>
                    <p>Перевір свої знання! 5 питань з інформатики з перевіркою.</p>
                    <span class="tag">JavaScript</span>
                    <span class="click-hint">👆 Клікни, щоб грати</span>
                </div>

                <div class="project-card" onclick="openModal('bot')">
                    <span class="emoji">🤖</span>
                    <h3>Telegram бот</h3>
                    <p>Бот для школи з розкладом, нагадуваннями та пошуком по вчителях.</p>
                    <span class="tag">Python + Telegram API</span>
                    <span class="click-hint">👆 Клікни, щоб подивитись</span>
                </div>

                <div class="project-card" onclick="openModal('schedule')">
                    <span class="emoji">📚</span>
                    <h3>Сайт розкладу</h3>
                    <p>Інтерактивний сайт з розкладом уроків для 7-Б класу.</p>
                    <span class="tag">HTML + CSS + JS</span>
                    <span class="click-hint">👆 Клікни, щоб подивитись</span>
                </div>

                <div class="project-card" onclick="openModal('weather')">
                    <span class="emoji">🌤️</span>
                    <h3>Сайт погоди</h3>
                    <p>Додаток для перегляду погоди з пошуком по містах.</p>
                    <span class="tag">HTML + CSS + JS</span>
                    <span class="click-hint">👆 Клікни, щоб подивитись</span>
                </div>

            </div>
        </div>

        <div class="section">
            <h2>📊 Моя статистика</h2>
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="number" id="projectsCount">0</div>
                    <div class="label">Проектів</div>
                </div>
                <div class="stat-item">
                    <div class="number" id="linesCount">0</div>
                    <div class="label">Рядків коду</div>
                </div>
                <div class="stat-item">
                    <div class="number" id="awardsCount">0</div>
                    <div class="label">Нагород</div>
                </div>
                <div class="stat-item">
                    <div class="number" id="hoursCount">0</div>
                    <div class="label">Годин кодування</div>
                </div>
            </div>
        </div>

        <div style="text-align: center; margin-top: 10px;">
            <button class="btn" onclick="showSurprise()">🎁 Клікни за сюрпризом!</button>
        </div>

        <div id="surprise">
            <div class="big">🎉🎊🌟</div>
            <h2>Вітаю! Ти отримав(ла) 12 балів!</h2>
            <p>За <strong>креативність, старанність та якісні проекти</strong> з інформатики</p>
            <p style="margin-top: 10px; font-size: 1.2rem;">🏆 <strong>Учень року</strong> — номінація "Найкращий програміст"</p>
            <div style="margin-top: 15px; font-size: 2rem;">⭐💻🚀🔥</div>
        </div>

        <div class="footer">
            © 2024 Моє портфоліо · Створено з ❤️ для інформатики
        </div>

    </div>

    <div class="modal" id="modal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeModal()">✕</button>
            <div id="modalBody"></div>
        </div>
    </div>

    <script>
        function openModal(type) {
            const modal = document.getElementById('modal');
            const body = document.getElementById('modalBody');
            
            let content = '';
            
            switch(type) {
                case 'guess':
                    content = guessGameHTML();
                    break;
                case 'calc':
                    content = calcGameHTML();
                    break;
                case 'test':
                    content = testGameHTML();
                    break;
                case 'bot':
                    content = botProjectHTML();
                    break;
                case 'schedule':
                    content = scheduleProjectHTML();
                    break;
                case 'weather':
                    content = weatherProjectHTML();
                    break;
                default:
                    content = '<p>Проект в розробці</p>';
            }
            
            body.innerHTML = content;
            modal.classList.add('active');
            document.body.style.overflow = 'hidden';
            
            if (type === 'guess') {
                setTimeout(() => initGuessGame(), 100);
            }
        }

        function closeModal() {
            document.getElementById('modal').classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        document.getElementById('modal').addEventListener('click', function(e) {
            if (e.target === this) closeModal();
        });

        // ===== ГРА "ВГАДАЙ ЧИСЛО" =====
        function guessGameHTML() {
            return `
                <div class="modal-emoji">🎯</div>
                <h2>Вгадай число</h2>
                <p class="modal-desc">Комп'ютер загадав число від 1 до 100. Спробуй вгадати!</p>
                <div class="modal-tech"><span>JavaScript</span><span>Логіка</span></div>
                
                <div class="game-container guess-game" id="guessGame">
                    <div class="message info" id="guessMessage">Я загадав число від 1 до 100</div>
                    <div style="display:flex; gap:10px; flex-wrap:wrap; align-items:center;">
                        <input type="number" id="guessInput" min="1" max="100" placeholder="Введи число...">
                        <button class="guess-btn" onclick="makeGuess()">Перевірити</button>
                        <button class="reset-btn" onclick="resetGuessGame()">🔄 Нова гра</button>
                    </div>
                    <div class="attempts">Спроб: <span id="guessAttempts">0</span></div>
                </div>
            `;
        }

        let guessNumber = Math.floor(Math.random() * 100) + 1;
        let guessAttempts = 0;

        function initGuessGame() {
            guessNumber = Math.floor(Math.random() * 100) + 1;
            guessAttempts = 0;
            const msg = document.getElementById('guessMessage');
            if (msg) {
                msg.className = 'message info';
                msg.textContent = 'Я загадав число від 1 до 100';
            }
            const attempts = document.getElementById('guessAttempts');
            if (attempts) attempts.textContent = '0';
            const input = document.getElementById('guessInput');
            if (input) { input.value = ''; input.focus(); }
        }

        function makeGuess() {
            const input = document.getElementById('guessInput');
            const msg = document.getElementById('guessMessage');
            const attemptsEl = document.getElementById('guessAttempts');
            
            if (!input || !msg) return;
            
            const guess = parseInt(input.value);
            if (isNaN(guess) || guess < 1 || guess > 100) {
                msg.className = 'message error';
                msg.textContent = '❌ Введи число від 1 до 100!';
                return;
            }
            
            guessAttempts++;
            attemptsEl.textContent = guessAttempts;
            
            if (guess === guessNumber) {
                msg.className = 'message success';
                msg.textContent = `🎉 Вітаю! Ти вгадав за ${guessAttempts} спроб! Число було ${guessNumber}`;
                input.disabled = true;
            } else if (guess < guessNumber) {
                msg.className = 'message info';
                msg.textContent = '📈 Моє число БІЛЬШЕ';
            } else {
                msg.className = 'message info';
                msg.textContent = '📉 Моє число МЕНШЕ';
            }
            
            input.value = '';
            input.focus();
        }

        function resetGuessGame() {
            const input = document.getElementById('guessInput');
            if (input) input.disabled = false;
            initGuessGame();
        }

        // ===== КАЛЬКУЛЯТОР =====
        let calcDisplay = '';

        function calcGameHTML() {
            return `
                <div class="modal-emoji">🧮</div>
                <h2>Калькулятор</h2>
                <p class="modal-desc">Звичайний калькулятор з усіма діями</p>
                <div class="modal-tech"><span>JavaScript</span></div>
                
                <div class="game-container calc-game">
                    <div class="calc-display" id="calcDisplay" style="background:rgba(0,0,0,0.4);padding:15px 20px;border-radius:12px;font-size:2rem;text-align:right;margin-bottom:15px;min-height:60px;border:1px solid rgba(255,255,255,0.05);">0</div>
                    <div style="display:grid;grid-template-columns:repeat(4,1fr);gap:10px;">
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(244,67,54,0.3);color:#ef9a9a;" onclick="calcClear()">C</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('(')">(</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput(')')">)</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(102,126,234,0.3);color:#a8b5ff;" onclick="calcInput('/')">÷</button>
                        
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('7')">7</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('8')">8</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('9')">9</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(102,126,234,0.3);color:#a8b5ff;" onclick="calcInput('*')">×</button>
                        
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('4')">4</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('5')">5</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('6')">6</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(102,126,234,0.3);color:#a8b5ff;" onclick="calcInput('-')">−</button>
                        
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('1')">1</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('2')">2</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('3')">3</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(102,126,234,0.3);color:#a8b5ff;" onclick="calcInput('+')">+</button>
                        
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;grid-column:span 2;" onclick="calcInput('0')">0</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:rgba(255,255,255,0.08);color:#fff;" onclick="calcInput('.')">.</button>
                        <button style="padding:15px;border:none;border-radius:12px;font-size:1.2rem;font-weight:600;cursor:pointer;background:linear-gradient(135deg,#667eea,#764ba2);color:#fff;" onclick="calcResult()">=</button>
                    </div>
                </div>
            `;
        }

        function calcInput(value) {
            const display = document.getElementById('calcDisplay');
            if (!display) return;
            if (display.textContent === '0' && value !== '.') {
                display.textContent = value;
            } else {
                display.textContent += value;
            }
        }

        function calcClear() {
            const display = document.getElementById('calcDisplay');
            if (display) display.textContent = '0';
        }

        function calcResult() {
            const display = document.getElementById('calcDisplay');
            if (!display) return;
            try {
                const result = eval(display.textContent.replace(/×/g, '*').replace(/÷/g, '/'));
                display.textContent = result;
            } catch(e) {
                display.textContent = 'Помилка';
            }
        }

        // ===== ТЕСТ =====
        function testGameHTML() {
            return `
                <div class="modal-emoji">📝</div>
                <h2>Тест з інформатики</h2>
                <p class="modal-desc">Перевір свої знання! Відповідай на питання.</p>
                <div class="modal-tech"><span>JavaScript</span></div>
                
                <div class="game-container test-game" id="testGame">
                    <div id="testContent"></div>
                </div>
            `;
        }

        // ===== ІНШІ ПРОЕКТИ =====
        function botProjectHTML() {
            return `
                <div class="modal-emoji">🤖</div>
                <h2>Telegram бот розкладу</h2>
                <p class="modal-desc">Бот для школи з розкладом уроків, нагадуваннями та пошуком по вчителях.</p>
                <div class="modal-tech"><span>Python</span><span>Telegram API</span></div>
                <div style="background:rgba(255,255,255,0.05);border-radius:12px;padding:20px;">
                    <p style="color:rgba(255,255,255,0.7);">📌 Функції:</p>
                    <ul style="color:rgba(255,255,255,0.6);list-style:none;padding:0;">
                        <li>✅ /today - розклад на сьогодні</li>
                        <li>✅ /tomorrow - розклад на завтра</li>
                        <li>✅ /week - розклад на тиждень</li>
                        <li>✅ /teacher - пошук по вчителю</li>
                    </ul>
                </div>
            `;
        }

        function scheduleProjectHTML() {
            return `
                <div class="modal-emoji">📚</div>
                <h2>Сайт розкладу</h2>
                <p class="modal-desc">Інтерактивний сайт з розкладом уроків для 7-Б класу з пошуком по днях.</p>
                <div class="modal-tech"><span>HTML</span><span>CSS</span><span>JS</span></div>
                <div style="background:rgba(255,255,255,0.05);border-radius:12px;padding:20px;">
                    <p style="color:rgba(255,255,255,0.7);">📌 Можливості:</p>
                    <ul style="color:rgba(255,255,255,0.6);list-style:none;padding:0;">
                        <li>✅ Перегляд по днях</li>
                        <li>✅ Пошук по вчителях</li>
                        <li>✅ Гарний дизайн</li>
                    </ul>
                </div>
            `;
        }

        function weatherProjectHTML() {
            return `
                <div class="modal-emoji">🌤️</div>
                <h2>Сайт погоди</h2>
                <p class="modal-desc">Додаток для перегляду погоди з пошуком по містах та гарним дизайном.</p>
                <div class="modal-tech"><span>HTML</span><span>CSS</span><span>JS</span></div>
                <div style="background:rgba(255,255,255,0.05);border-radius:12px;padding:20px;">
                    <p style="color:rgba(255,255,255,0.7);">📌 Можливості:</p>
                    <ul style="color:rgba(255,255,255,0.6);list-style:none;padding:0;">
                        <li>✅ Пошук по містах</li>
                        <li>✅ Температура, вологість, вітер</li>
                        <li>✅ Красиві іконки</li>
                    </ul>
                </div>
            `;
        }

        // ===== СТАТИСТИКА =====
        document.addEventListener('DOMContentLoaded', function() {
            const counters = [
                { id: 'projectsCount', target: 6 },
                { id: 'linesCount', target: 2450 },
                { id: 'awardsCount', target: 5 },
                { id: 'hoursCount', target: 380 }
            ];

            counters.forEach(counter => {
                animateCounter(counter.id, counter.target, 2500);
            });
        });

        function animateCounter(id, target, duration) {
            const element = document.getElementById(id);
            if (!element) return;
            let start = 0;
            const steps = 60;
            const increment = target / steps;
            let current = 0;
            const stepTime = duration / steps;

            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    element.textContent = target;
                    clearInterval(timer);
                } else {
                    element.textContent = Math.floor(current);
                }
            }, stepTime);
        }

        function showSurprise() {
            const surprise = document.getElementById('surprise');
            if (surprise.style.display === 'none') {
                surprise.style.display = 'block';
                surprise.scrollIntoView({ behavior: 'smooth', block: 'center' });
            } else {
                surprise.style.display = 'none';
            }
        }
    </script>
</body>
</html>
