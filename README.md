<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SLAY KING | Награды нашей группы</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Arial, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            color: #fff;
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .header {
            text-align: center;
            padding: 40px 20px;
            background: linear-gradient(90deg, #6a11cb 0%, #2575fc 100%);
            border-radius: 20px;
            margin-bottom: 40px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .header h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.5);
        }

        .header p {
            font-size: 1.2rem;
            opacity: 0.9;
            max-width: 800px;
            margin: 0 auto;
            line-height: 1.6;
        }

        .deadline {
            background: rgba(255, 215, 0, 0.15);
            border: 2px solid #ffd700;
            padding: 15px;
            border-radius: 10px;
            margin-top: 20px;
            display: inline-block;
            font-weight: bold;
        }

        .nominations-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }

        .nomination-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .nomination-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
        }

        .nomination-card h3 {
            color: #ffd700;
            font-size: 1.8rem;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 2px solid rgba(255, 215, 0, 0.3);
        }

        .nomination-card p {
            color: #ccc;
            margin-bottom: 20px;
            line-height: 1.5;
            min-height: 60px;
        }

        .candidates {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .candidate {
            display: flex;
            align-items: center;
            padding: 12px 15px;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .candidate:hover {
            background: rgba(106, 17, 203, 0.3);
            transform: translateX(5px);
        }

        .candidate.selected {
            background: rgba(37, 117, 252, 0.3);
            border-color: #2575fc;
        }

        .vote-btn {
            background: linear-gradient(90deg, #6a11cb 0%, #2575fc 100%);
            color: white;
            border: none;
            padding: 15px 40px;
            font-size: 1.2rem;
            border-radius: 50px;
            cursor: pointer;
            margin: 30px auto;
            display: block;
            transition: all 0.3s ease;
            font-weight: bold;
            letter-spacing: 1px;
        }

        .vote-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(37, 117, 252, 0.4);
        }

        .vote-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            transform: none !important;
        }

        .results-section {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 30px;
            margin-top: 40px;
            display: none;
        }

        .results-section.active {
            display: block;
        }

        .winner-card {
            background: linear-gradient(135deg, rgba(255, 215, 0, 0.15), rgba(255, 215, 0, 0.05));
            border: 2px solid #ffd700;
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
            text-align: center;
        }

        .winner-card h4 {
            color: #ffd700;
            font-size: 1.5rem;
            margin-bottom: 10px;
        }

        .progress-bar {
            height: 20px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            margin: 15px 0;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #6a11cb 0%, #2575fc 100%);
            border-radius: 10px;
            width: 0%;
            transition: width 1.5s ease;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            padding: 40px;
            border-radius: 20px;
            max-width: 500px;
            width: 90%;
            text-align: center;
            border: 2px solid #6a11cb;
        }

        .instructions {
            background: rgba(255, 255, 255, 0.05);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
        }

        .instructions h3 {
            color: #6a11cb;
            margin-bottom: 15px;
        }

        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            
            .nominations-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🏆 SLAY KING 2024</h1>
            <p>Голосование за лучших участников нашей группы! Выберите победителей в каждой номинации.</p>
            <div class="deadline">
                ⏰ Голосование открыто до: 20 декабря 2024, 23:59
            </div>
        </div>

        <div class="instructions">
            <h3>📋 Как голосовать:</h3>
            <p>1. Выберите ОДНОГО участника в КАЖДОЙ номинации<br>
               2. Все поля должны быть заполнены<br>
               3. Нажмите кнопку "Отправить голоса" в конце страницы<br>
               4. После голосования вы увидите предварительные результаты</p>
        </div>

        <div class="nominations-grid" id="nominationsContainer">
            <!-- Номинации будут загружены через JavaScript -->
        </div>

        <button class="vote-btn" id="submitVote" disabled>Отправить голоса</button>

        <div class="results-section" id="resultsSection">
            <h2 style="text-align: center; margin-bottom: 30px; color: #ffd700;">📊 Текущие результаты</h2>
            <div id="resultsContainer"></div>
        </div>
    </div>

    <div class="modal" id="successModal">
        <div class="modal-content">
            <h2 style="color: #4CAF50; margin-bottom: 20px;">✅ Голос принят!</h2>
            <p>Спасибо за участие в голосовании SLAY KING!</p>
            <p>Итоги будут объявлены 21 декабря 2024.</p>
            <button class="vote-btn" style="margin-top: 30px;" onclick="closeModal()">Понятно</button>
        </div>
    </div>

    <script>
        // Данные номинаций и участников
        const nominationsData = [
            {
                id: 1,
                title: "👑 МЕМ-КОРОЛЬ",
                description: "За самый смешной и уместный мем в группе",
                candidates: [
                    { id: 1, name: "Алексей 'Мемный' Иванов", votes: 42 },
                    { id: 2, name: "Катя Шутница", votes: 38 },
                    { id: 3, name: "Максим Рижовый", votes: 25 },
                    { id: 4, name: "Дима Ирония", votes: 31 }
                ]
            },
            {
                id: 2,
                title: "💡 СОВЕТНИК ГОДА",
                description: "За самые полезные советы и помощь новичкам",
                candidates: [
                    { id: 5, name: "Ольга Помогаева", votes: 45 },
                    { id: 6, name: "Сергей Экспертов", votes: 39 },
                    { id: 7, name: "Анна Консультант", votes: 28 },
                    { id: 8, name: "Михаил Наставник", votes: 22 }
                ]
            },
            {
                id: 3,
                title: "😊 ДУША КОМПАНИИ",
                description: "За позитив и активность в общении",
                candidates: [
                    { id: 9, name: "Виктория Оптимистка", votes: 52 },
                    { id: 10, name: "Артём Весельчак", votes: 41 },
                    { id: 11, name: "Елена Улыбка", votes: 33 },
                    { id: 12, name: "Павел Энтузиаст", votes: 27 }
                ]
            },
            {
                id: 4,
                title: "🌟 ЛЕГЕНДА ГРУППЫ",
                description: "За долгое присутствие и значимый вклад",
                candidates: [
                    { id: 13, name: "Андрей Основатель", votes: 48 },
                    { id: 14, name: "Мария Ветеран", votes: 36 },
                    { id: 15, name: "Игорь Старейшина", votes: 29 },
                    { id: 16, name: "Наталья Альфа", votes: 24 }
                ]
            },
            {
                id: 5,
                title: "🎨 КОНТЕНТ-МЕЙКЕР",
                description: "За лучший пользовательский контент",
                candidates: [
                    { id: 17, name: "Денис Фотограф", votes: 40 },
                    { id: 18, name: "Алина Видеоблогер", votes: 37 },
                    { id: 19, name: "Роман Копирайтер", votes: 26 },
                    { id: 20, name: "Юлия Дизайнер", votes: 30 }
                ]
            },
            {
                id: 6,
                title: "🚀 НОВИЧОК ГОДА",
                description: "Самый заметный новый участник",
                candidates: [
                    { id: 21, name: "Кирилл Прогресс", votes: 35 },
                    { id: 22, name: "Светлана Неофит", votes: 32 },
                    { id: 23, name: "Тимофей Стартер", votes: 21 },
                    { id: 24, name: "Валерия Дебют", votes: 28 }
                ]
            }
        ];

        let userVotes = {};
        let hasVoted = localStorage.getItem('hasVoted') === 'true';

        // Инициализация страницы
        function initPage() {
            const container = document.getElementById('nominationsContainer');
            
            nominationsData.forEach(nomination => {
                const card = document.createElement('div');
                card.className = 'nomination-card';
                card.innerHTML = `
                    <h3>${nomination.title}</h3>
                    <p>${nomination.description}</p>
                    <div class="candidates">
                        ${nomination.candidates.map(candidate => `
                            <div class="candidate" data-nom="${nomination.id}" data-id="${candidate.id}">
                                <input type="radio" name="nomination_${nomination.id}" 
                                       id="candidate_${candidate.id}" style="margin-right: 10px;">
                                <label for="candidate_${candidate.id}" style="flex-grow: 1; cursor: pointer;">
                                    ${candidate.name}
                                    <span style="float: right; color: #6a11cb; font-weight: bold;">
                                        ${candidate.votes} голосов
                                    </span>
                                </label>
                            </div>
                        `).join('')}
                    </div>
                `;
                container.appendChild(card);
            });

            // Обработчики для выбора кандидатов
            document.querySelectorAll('.candidate').forEach(candidate => {
                candidate.addEventListener('click', function() {
                    const nomId = this.dataset.nom;
                    const candId = this.dataset.id;
                    
                    // Снимаем выделение со всех в этой номинации
                    document.querySelectorAll(`[data-nom="${nomId}"]`).forEach(el => {
                        el.classList.remove('selected');
                        el.querySelector('input').checked = false;
                    });
                    
                    // Выделяем выбранного
                    this.classList.add('selected');
                    this.querySelector('input').checked = true;
                    
                    // Сохраняем выбор
                    userVotes[nomId] = candId;
                    
                    // Активируем кнопку если все номинации выбраны
                    checkVotesCompletion();
                });
            });

            // Обработчик кнопки отправки
            document.getElementById('submitVote').addEventListener('click', submitVote);

            // Если уже голосовали, показываем результаты
            if (hasVoted) {
                showResults();
            }
        }

        // Проверка заполнения всех номинаций
        function checkVotesCompletion() {
            const totalNominations = nominationsData.length;
            const votedNominations = Object.keys(userVotes).length;
            const submitBtn = document.getElementById('submitVote');
            
            if (votedNominations === totalNominations && !hasVoted) {
                submitBtn.disabled = false;
                submitBtn.textContent = `Отправить ${totalNominations} голоса`;
            }
        }

        // Отправка голосов
        function submitVote() {
            if (hasVoted) {
                alert('Вы уже голосовали!');
                return;
            }

            // Здесь должна быть отправка на сервер
            // Временно симулируем сохранение
            localStorage.setItem('hasVoted', 'true');
            hasVoted = true;
            
            // Показываем модальное окно
            document.getElementById('successModal').classList.add('active');
            
            // Обновляем результаты
            updateVotesCount();
            showResults();
            
            // Блокируем кнопку
            document.getElementById('submitVote').disabled = true;
            document.getElementById('submitVote').textContent = 'Вы уже проголосовали';
        }

        // Обновление счетчиков голосов
        function updateVotesCount() {
            Object.entries(userVotes).forEach(([nomId, candId]) => {
                const nomination = nominationsData.find(n => n.id == nomId);
                if (nomination) {
                    const candidate = nomination.candidates.find(c => c.id == candId);
                    if (candidate) {
                        candidate.votes += 1;
                    }
                }
            });
        }

        // Показать результаты
        function showResults() {
            const resultsContainer = document.getElementById('resultsContainer');
            resultsContainer.innerHTML = '';
            
            nominationsData.forEach(nomination => {
                const totalVotes = nomination.candidates.reduce((sum, c) => sum + c.votes, 0);
                const winner = nomination.candidates.reduce((prev, current) => 
                    (prev.votes > current.votes) ? prev : current
                );
                
                const resultCard = document.createElement('div');
                resultCard.className = 'winner-card';
                resultCard.innerHTML = `
                    <h4>${nomination.title}</h4>
                    <p>Победитель: <strong>${winner.name}</strong></p>
                    <p>Голосов: ${winner.votes} из ${totalVotes}</p>
                    <div class="progress-bar">
                        <div class="progress-fill" style="width: ${(winner.votes/totalVotes)*100}%"></div>
                    </div>
                    <div style="display: flex; justify-content: space-between; font-size: 0.9em; opacity: 0.8;">
                        ${nomination.candidates.map(c => 
                            `${c.name}: ${c.votes}`
                        ).join(' | ')}
                    </div>
                `;
                resultsContainer.appendChild(resultCard);
            });
            
            document.getElementById('resultsSection').classList.add('active');
        }

        // Закрыть модальное окно
        function closeModal() {
            document.getElementById('successModal').classList.remove('active');
            window.scrollTo({
                top: document.getElementById('resultsSection').offsetTop,
                behavior: 'smooth'
            });
        }

        // Кнопка "Поделиться результатами"
        function shareResults() {
            const text = `Я только что проголосовал в SLAY KING! 🏆\nПрисоединяйся: ${window.location.href}`;
            if (navigator.share) {
                navigator.share({
                    title: 'SLAY KING Голосование',
                    text: text,
                    url: window.location.href
                });
            } else {
                navigator.clipboard.writeText(text);
                alert('Ссылка скопирована в буфер обмена! Поделись с друзьями!');
            }
        }

        // Инициализация при загрузке
        document.addEventListener('DOMContentLoaded', initPage);
    </script>
</body>
</html>
