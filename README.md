<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Артур · Боевой рекорд · Синий стиль</title>
    <!-- Имитация GitHub-страницы с хакерским/кибер-акцентом и анимацией печати -->
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0a0c10;  /* глубокий тёмный фон, похожий на GitHub dark */
            font-family: 'Fira Code', 'SF Mono', 'JetBrains Mono', 'Courier New', monospace;
            color: #ccdeee;
            padding: 2rem 1.5rem;
            line-height: 1.5;
        }

        /* главный контейнер — как ридми-стиль, но с синими акцентами */
        .readme-container {
            max-width: 1000px;
            margin: 0 auto;
            background: #0d1117;
            border-radius: 24px;
            padding: 2rem 2rem 2.5rem;
            box-shadow: 0 20px 35px -12px rgba(0,0,0,0.6), 0 0 0 1px rgba(33, 114, 229, 0.2);
            border-left: 4px solid #1f6feb;
        }

        /* синяя тема для заголовков, ссылок, особых элементов */
        h1, h2, h3, .blue-glow {
            color: #58a6ff;
            letter-spacing: -0.3px;
        }

        /* панель терминала / код-строка с анимацией */
        .terminal-bar {
            background: #161b22;
            border-radius: 14px;
            margin: 24px 0 20px;
            padding: 6px 16px;
            display: flex;
            align-items: center;
            gap: 12px;
            flex-wrap: wrap;
            border: 1px solid #30363d;
            box-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }

        .dots {
            display: flex;
            gap: 8px;
        }
        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: #ff5f56;
        }
        .dot:nth-child(2) { background: #ffbd2e; }
        .dot:nth-child(3) { background: #27c93f; }

        .code-line {
            font-family: 'Fira Code', monospace;
            font-size: 1rem;
            background: #0a0c10;
            padding: 6px 14px;
            border-radius: 40px;
            color: #b1e3ff;
            display: inline-flex;
            align-items: baseline;
            gap: 4px;
            flex-wrap: wrap;
            letter-spacing: 0.2px;
        }

        .prompt {
            color: #7e9cd9;
            user-select: none;
        }

        .typing-name {
            font-weight: 700;
            color: #3b82f6;  /* ярко-синий */
            text-shadow: 0 0 3px #1e88e5;
            border-right: 2px solid #3b82f6;
            white-space: pre;
            display: inline-block;
            min-width: 90px;
        }

        .blinking-cursor {
            animation: blink 1s step-end infinite;
            margin-left: 2px;
            display: inline-block;
            width: 2px;
            background: #3b82f6;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        /* таблицы в стиле GitHub */
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 18px 0;
            background: #0d1117;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 1px 3px rgba(0,0,0,0.2);
        }
        th {
            background: #161b22;
            color: #79c0ff;
            font-weight: 600;
            padding: 10px 16px;
            text-align: left;
            border-bottom: 1px solid #30363d;
            font-size: 0.9rem;
        }
        td {
            padding: 10px 16px;
            border-bottom: 1px solid #21262d;
            color: #e6edf3;
        }
        tr:last-child td {
            border-bottom: none;
        }
        .result-badge {
            color: #58a6ff;
            font-weight: bold;
            background: #1a2a3a;
            padding: 2px 10px;
            border-radius: 20px;
            display: inline-block;
            font-size: 0.85rem;
            letter-spacing: 0.3px;
        }

        /* арсенал — уровень владения выделен синим */
        .level {
            color: #3b82f6;
            font-weight: 600;
            background: rgba(59,130,246,0.12);
            padding: 2px 10px;
            border-radius: 20px;
            font-size: 0.85rem;
        }

        hr {
            border: none;
            height: 1px;
            background: linear-gradient(90deg, #1f6feb, #30363d, #1f6feb);
            margin: 24px 0;
        }

        .principle-list {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            margin: 24px 0;
        }
        .principle-item {
            background: #0d1117;
            border: 1px solid #2d3a4a;
            border-radius: 60px;
            padding: 8px 18px;
            font-weight: 500;
            letter-spacing: 0.8px;
        }
        .principle-item strong {
            color: #3b82f6;
            font-weight: 700;
        }
        .quote {
            text-align: center;
            font-style: italic;
            color: #8ab2f0;
            border-left: 3px solid #1f6feb;
            padding: 12px 20px;
            background: #0a1017;
            border-radius: 20px;
            margin: 20px 0;
        }

        .footer-badge {
            text-align: center;
            font-size: 0.7rem;
            color: #4c6b8a;
            margin-top: 30px;
            border-top: 1px dashed #2d3a4a;
            padding-top: 18px;
        }
        a {
            color: #58a6ff;
            text-decoration: none;
        }
        .lang-block {
            background: #0a0f16;
            padding: 8px 20px;
            border-radius: 28px;
            margin: 10px 0;
        }

        @media (max-width: 640px) {
            .readme-container {
                padding: 1.2rem;
            }
            .code-line {
                font-size: 0.8rem;
            }
        }

        /* Специальный блок для визуального кода "артур в реальном времени" */
        .realtime-header {
            background: #010409;
            border-radius: 16px;
            margin-bottom: 24px;
            padding: 10px 0 4px 0;
        }
        .git-animation {
            background: #06090f;
            border-radius: 16px;
            padding: 12px 20px;
            font-family: monospace;
            font-size: 0.9rem;
            border: 1px solid #2d3a4a;
        }
        .git-command {
            color: #b1bac4;
        }
    </style>
</head>
<body>
<div class="readme-container">
    <!-- Верхний декоративный ASCII стиль (borz style) но адаптирован -->
    <p align="center" style="margin-bottom: 6px;">
        <span style="color:#1f6feb;">══════════════════════════════════════════════════════════</span>
    </p>
    <p align="center">
        <span style="color:#8cb2f0;"><b>|</b>  НЕ ОТСТУПАЮ  <b>|</b>  НЕ СДАЮСЬ  <b>|</b></span>
    </p>
    <p align="center" style="margin-bottom: 12px;">
        <span style="color:#1f6feb;">══════════════════════════════════════════════════════════</span>
    </p>

    <!-- ЭФФЕКТ НАБОРА ИМЕНИ: как будто в реальном времени пишется строчка кода на GitHub -->
    <div class="terminal-bar">
        <div class="dots">
            <div class="dot"></div>
            <div class="dot"></div>
            <div class="dot"></div>
        </div>
        <div class="code-line">
            <span class="prompt">$&nbsp;git&nbsp;config&nbsp;--global&nbsp;user.name&nbsp;</span>
            <span class="typing-name" id="dynamicName"></span>
            <span class="blinking-cursor" style="width: 2px; background:#3b82f6;">&nbsp;</span>
        </div>
        <div class="code-line" style="background: transparent; padding-left: 0;">
            <span style="color:#7e9cd9;"># ➜ profile loaded: ARTHUR · BERSERK MODE</span>
        </div>
    </div>

    <!-- сияющий заголовок с именем Артур -->
    <h1 align="center" style="font-size: 3rem; margin: 5px 0 0px 0; letter-spacing: 1px;">⚡ ARTHUR ⚡</h1>
    <p align="center">
        <b style="color:#58a6ff;">ЧЕБОКСАРЫ  |  КООПЕРАТИВНЫЙ ИНСТИТУТ  |  19 ЛЕТ</b>
    </p>
    <p align="center" style="margin: 8px 0 4px;">
        <span style="color:#1f6feb;">══════════════════════════════════════════════════════════</span>
    </p>

    <!-- БОЕВОЙ РЕКОРД - все цифры ярко-синие -->
    <h2>🔥 БОЕВОЙ РЕКОРД</h2>
    <table>
        <thead>
            <tr><th>Проект</th><th>Задача</th><th>Результат</th></tr>
        </thead>
        <tbody>
            <tr><td>⚡ High-load API gateway</td><td>10k RPS</td><td><span class="result-badge">-45% LATENCY</span></td></tr>
            <tr><td>📦 Распределённый кэш</td><td>LRU синхронизация</td><td><span class="result-badge">92% HIT RATE</span></td></tr>
            <tr><td>🌀 Асинхронный парсер</td><td>50+ источников</td><td><span class="result-badge">x8 SPEED</span></td></tr>
        </tbody>
    </table>

    <!-- АРСЕНАЛ с синими уровнями -->
    <h2>🧰 АРСЕНАЛ</h2>
    <table>
        <thead><tr><th>Категория</th><th>Оружие</th><th>Уровень</th></tr></thead>
        <tbody>
            <tr><td>🚀 Бэкенд</td><td>FastAPI / Django / asyncio / Celery</td><td><span class="level">ВЛАДЕЮ</span></td></tr>
            <tr><td>🗄️ Базы</td><td>PostgreSQL / Redis / MongoDB</td><td><span class="level">УВЕРЕННО</span></td></tr>
            <tr><td>🐳 Инфра</td><td>Docker / Nginx / Linux / Git</td><td><span class="level">ГОТОВ</span></td></tr>
            <tr><td>🧪 Тесты</td><td>pytest / locust</td><td><span class="level">ПРАКТИКА</span></td></tr>
            <tr><td>📖 Изучаю</td><td>Kubernetes / Kafka</td><td><span class="level">В ПРОЦЕССЕ</span></td></tr>
        </tbody>
    </table>

    <!-- ЯЗЫКИ + АНГЛИЙСКИЙ C2 синий акцент-->
    <h2>🌐 ЯЗЫКИ</h2>
    <div class="lang-block">
        <p><span style="color:#58a6ff;">🔹 РУССКИЙ</span> — РОДНОЙ</p>
        <p><span style="color:#58a6ff;">🔹 АНГЛИЙСКИЙ</span> — C2 (СВОБОДНО ЧИТАЮ ТЕХНИЧЕСКУЮ ДОКУМЕНТАЦИЮ)</p>
        <p><span style="color:#58a6ff;">🔹 КОД</span> — ПИШУ БЕЗ СТРАХА</p>
    </div>

    <!-- ПРИНЦИПЫ в стиле сильных утверждений -->
    <h2>⚙️ ПРИНЦИПЫ</h2>
    <div class="principle-list">
        <div class="principle-item"><strong>НЕ ЖАЛОВАТЬСЯ</strong> — ДЕЛАТЬ</div>
        <div class="principle-item"><strong>НЕ БОЯТЬСЯ</strong> — РАЗБИРАТЬ</div>
        <div class="principle-item"><strong>НЕ СДАВАТЬСЯ</strong> — ДАВИТЬ</div>
        <div class="principle-item"><strong>НЕ ОТСТУПАТЬ</strong> — ПОБЕЖДАТЬ</div>
    </div>

    <!-- Цитата -->
    <div class="quote">
        «В IT как в клетке: либо ты ломаешь задачу, либо она ломает тебя»
    </div>

    <p align="center">
        <span style="color:#1f6feb;">══════════════════════════════════════════════════════════</span>
    </p>
    <!-- дополнительный эффект реального времени: строчка коммита с именем Артур появляется динамически -->
    <div class="git-animation" id="commitAnim">
        <span class="git-command">➜ git log -1 --pretty=format:"%an"</span><br>
        <span id="commitAuthorOutput" style="color:#3b82f6; font-weight: bold;">[ ожидание генерации... ]</span>
        <span style="margin-left: 8px;">✨</span>
    </div>
    <div class="footer-badge">
        BORZ STYLE · ARTHUR · NO MERCY · NO SURRENDER<br>
        МОНОХРОМНО-СИНИЙ · ЖЁСТКО · БЕЗ КОМПРОМИССОВ
    </div>
</div>

<script>
    (function() {
        // 1. Эффект "печатания" имени Артур в реальном времени (строчка кода)
        const targetName = "Артур";
        const dynamicSpan = document.getElementById('dynamicName');
        if (dynamicSpan) {
            let index = 0;
            dynamicSpan.textContent = "";
            function typeNext() {
                if (index < targetName.length) {
                    dynamicSpan.textContent += targetName[index];
                    index++;
                    setTimeout(typeNext, 180); // скорость печати как реальный набор
                } else {
                    // после завершения добавить имитацию завершения команды
                    const cursorBlink = document.querySelector('.blinking-cursor');
                    if (cursorBlink) cursorBlink.style.animation = 'blink 1s step-end infinite';
                    // дополнительно в консоль git эффект: вывод "Name set to 'Артур'"
                    const gitFeedback = document.createElement('div');
                    gitFeedback.style.fontSize = "0.8rem";
                    gitFeedback.style.marginTop = "4px";
                    gitFeedback.style.color = "#7aa2f7";
                    gitFeedback.innerHTML = "✓ user.name set to 'Артур' &nbsp;|&nbsp; profile synced";
                    const termParent = document.querySelector('.terminal-bar');
                    if(termParent && !termParent.querySelector('.git-feedback')) {
                        gitFeedback.classList.add('git-feedback');
                        termParent.appendChild(gitFeedback);
                    }
                }
            }
            typeNext();
        }

        // 2. Эмуляция "реального времени" — в блоке git-animation постепенно заполняем строку,
        // как будто команда выполняется и выводит "Артур"
        const commitOutputSpan = document.getElementById('commitAuthorOutput');
        if (commitOutputSpan) {
            const finalAuthor = "Артур <arthur.borz@cyber.dev>";
            let step = 0;
            commitOutputSpan.textContent = "";
            function simulateCommitFetch() {
                if (step < finalAuthor.length) {
                    commitOutputSpan.textContent += finalAuthor[step];
                    step++;
                    setTimeout(simulateCommitFetch, 70);
                } else {
                    // добавляем красивый псевдо-статус
                    const extra = document.createElement('div');
                    extra.style.marginTop = "8px";
                    extra.style.fontSize = "0.75rem";
                    extra.style.color = "#6e8fbb";
                    extra.innerHTML = "✔ commit: 3a7f2e1 — \"feat: arthur profile injection\" (verified)";
                    const parentDiv = document.getElementById('commitAnim');
                    if (parentDiv && !parentDiv.querySelector('.extra-status')) {
                        extra.classList.add('extra-status');
                        parentDiv.appendChild(extra);
                    }
                }
            }
            // делаем задержку перед запуском, чтобы гармонировать с основной анимацией (через 0.4 сек)
            setTimeout(simulateCommitFetch, 500);
        }

        // 3. Добавим дополнительный синий динамический эффект: пульсация у некоторых элементов
        const headings = document.querySelectorAll('h1, h2');
        headings.forEach(h => {
            h.style.transition = 'text-shadow 0.2s';
            setInterval(() => {
                if (Math.random() > 0.7) {
                    h.style.textShadow = '0 0 3px #3b82f6';
                    setTimeout(() => { h.style.textShadow = 'none'; }, 200);
                }
            }, 1200);
        });

        // 4. эффект печати на странице в целом не обязателен, но имитирует "живой код"
        // Также можно менять цвет отдельных элементов на синий при наведении.
        const allTdLevels = document.querySelectorAll('.level');
        allTdLevels.forEach(el => {
            el.style.transition = 'all 0.2s';
            el.addEventListener('mouseenter', () => {
                el.style.backgroundColor = '#1a44aa';
                el.style.color = '#f0f6ff';
            });
            el.addEventListener('mouseleave', () => {
                el.style.backgroundColor = 'rgba(59,130,246,0.12)';
                el.style.color = '#3b82f6';
            });
        });

        // Имитация лога коммитов на странице (динамическое обновление каждые 7 секунд, как будто активность)
        let altern = 0;
        setInterval(() => {
            const commitBlock = document.getElementById('commitAnim');
            if (commitBlock && altern % 2 === 0) {
                const fakeUpdate = document.createElement('div');
                fakeUpdate.style.fontSize = "0.7rem";
                fakeUpdate.style.color = "#58a6ff";
                fakeUpdate.style.borderTop = "1px dashed #2d3a4a";
                fakeUpdate.style.marginTop = "8px";
                fakeUpdate.style.paddingTop = "6px";
                fakeUpdate.innerHTML = "> git push origin main — [Артур] успешно доставлен";
                if (!commitBlock.querySelector('.live-push')) {
                    fakeUpdate.classList.add('live-push');
                    commitBlock.appendChild(fakeUpdate);
                    setTimeout(() => {
                        if(fakeUpdate) fakeUpdate.remove();
                    }, 2800);
                }
            }
            altern++;
        }, 6800);
    })();
</script>

<!-- Дополнительная эмуляция строки как при чтении README на GitHub —  синий бордер и динамическая дата-->
</body>
</html>
