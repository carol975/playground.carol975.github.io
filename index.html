<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Romantic Pac-Man Game</title>
    <style>
        body {
            margin: 0;
            font-family: 'Arial', sans-serif;
            background: linear-gradient(to bottom right, #ffafbd, #ffc3a0);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: white;
            text-align: center;
            overflow: hidden;
        }
        .start-screen {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }
        .heart-button {
            font-size: 4rem;
            color: crimson;
            cursor: pointer;
            animation: heartbeat 1.5s infinite;
        }
        .heart-label {
            font-size: 1.2rem;
            color: crimson;
            font-weight: bold;
        }
        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }
        canvas {
            display: none;
            background: black;
            margin: 0 auto;
            border: 5px solid white;
        }
        .score {
            position: absolute;
            top: 20px;
            font-size: 24px;
            color: white;
        }
        .win-message {
            position: absolute;
            top: 100px;
            font-size: 32px;
            color: crimson;
        }
    </style>
</head>
<body>
    <div class="start-screen">
        <div>
            <div class="heart-button" id="startButton">❤️</div>
            <div class="heart-label">Carol</div>
        </div>
        <h1>Click the heart to start the game!</h1>
    </div>
    <div class="score" id="score">Score: 0</div>
    <div class="win-message" id="winMessage" style="display: none;">爱你一辈子!</div>
    <canvas id="gameCanvas" width="600" height="400"></canvas>

    <script>
        const startButton = document.getElementById('startButton');
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        const scoreDisplay = document.getElementById('score');
        const winMessage = document.getElementById('winMessage');

        let pacman = { x: 50, y: 50, size: 20, dx: 0, dy: 0, speed: 5 };
        let carol = { x: 300, y: 200, size: 30, dx: 1, dy: 1 };
        let alligator = { x: 500, y: 300, size: 30, speed: 1 }; // Alligator setup
        let score = 0;
        let gameRunning = false;
        let alligatorVisible = true; // Track if alligator is visible
        let alligatorHit = false; // Track if collision happened in the current frame

        // Start the game
        startButton.addEventListener('click', () => {
            document.querySelector('.start-screen').style.display = 'none';
            canvas.style.display = 'block';
            winMessage.style.display = 'none'; // Hide win message when the game starts
            score = 0; // Reset the score
            scoreDisplay.textContent = 'Score: ' + score;
            gameRunning = true;
            gameLoop();
        });

        // Keyboard controls
        document.addEventListener('keydown', (event) => {
            if (event.key === 'ArrowUp' || event.key === 'w') {
                pacman.dy = -pacman.speed;
                pacman.dx = 0;
            } else if (event.key === 'ArrowDown' || event.key === 's') {
                pacman.dy = pacman.speed;
                pacman.dx = 0;
            } else if (event.key === 'ArrowLeft' || event.key === 'a') {
                pacman.dx = -pacman.speed;
                pacman.dy = 0;
            } else if (event.key === 'ArrowRight' || event.key === 'd') {
                pacman.dx = pacman.speed;
                pacman.dy = 0;
            }
        });

        // Draw Carol (a cute heart with the name)
        function drawCarol() {
            ctx.fillStyle = 'gray';

            // Draw Carol's body (oval)
            ctx.beginPath();
            ctx.ellipse(carol.x, carol.y, carol.size, carol.size * 0.7, 0, 0, Math.PI * 2);
            ctx.fill();

            // Draw Carol's ears
            ctx.beginPath();
            ctx.arc(carol.x - carol.size * 0.6, carol.y - carol.size * 0.5, carol.size * 0.4, 0, Math.PI * 2);
            ctx.arc(carol.x + carol.size * 0.6, carol.y - carol.size * 0.5, carol.size * 0.4, 0, Math.PI * 2);
            ctx.fill();

            // Add Carol's name
            ctx.fillStyle = 'white';
            ctx.font = 'bold 14px Arial';
            ctx.textAlign = 'center';
            ctx.fillText('囤囤鼠', carol.x, carol.y + carol.size + 15);

        }

        // Draw Pac-Man (Lee as a mouse shape)
        function drawPacman() {
            ctx.fillStyle = 'red';

            // Draw smooth heart shape for Pacman
            ctx.beginPath();
            ctx.arc(pacman.x - pacman.size / 2, pacman.y - pacman.size / 3, pacman.size / 2, Math.PI, 0);
            ctx.arc(pacman.x + pacman.size / 2, pacman.y - pacman.size / 3, pacman.size / 2, Math.PI, 0);
            ctx.lineTo(pacman.x, pacman.y + pacman.size * 0.7); // Adjusted bottom of heart for smoother curves
            ctx.closePath();
            ctx.fill();

            // Add Pacman's name
            ctx.fillStyle = 'white';
            ctx.font = 'bold 14px Arial';
            ctx.textAlign = 'center';
            ctx.fillText('卡罗尔', pacman.x, pacman.y + pacman.size + 15);
        }


        // Draw Alligator (chasing character)
        function drawAlligator() {
            if (!alligatorVisible) return; // If the alligator is invisible, do not draw it

            ctx.fillStyle = 'green';

            // Draw Alligator body (rectangle with rounded edges)
            ctx.beginPath();
            ctx.moveTo(alligator.x - alligator.size / 2, alligator.y);
            ctx.lineTo(alligator.x + alligator.size / 2, alligator.y);
            ctx.lineTo(alligator.x + alligator.size / 2, alligator.y + alligator.size / 1.5);
            ctx.lineTo(alligator.x - alligator.size / 2, alligator.y + alligator.size / 1.5);
            ctx.closePath();
            ctx.fill();

            // Add Alligator's name
            ctx.fillStyle = 'white';
            ctx.font = 'bold 14px Arial';
            ctx.textAlign = 'center';
            ctx.fillText('小心眼鳄鱼精', alligator.x, alligator.y + alligator.size + 15);
        }

        // Update positions of Pac-Man, Carol, and Alligator
        function updatePositions() {
            // Update Pac-Man
            pacman.x += pacman.dx;
            pacman.y += pacman.dy;

            // Keep Pac-Man in bounds
            if (pacman.x + pacman.size > canvas.width || pacman.x - pacman.size < 0) {
                pacman.dx = 0;
            }
            if (pacman.y + pacman.size > canvas.height || pacman.y - pacman.size < 0) {
                pacman.dy = 0;
            }

            // Update Carol
            carol.x += carol.dx;
            carol.y += carol.dy;

            // Keep Carol in bounds
            if (carol.x + carol.size > canvas.width || carol.x - carol.size < 0) {
                carol.dx *= -1;
            }
            if (carol.y + carol.size > canvas.height || carol.y - carol.size < 0) {
                carol.dy *= -1;
            }

            // Update Alligator's movement: it chases Lee (pacman)
            let dx = pacman.x - alligator.x;
            let dy = pacman.y - alligator.y;
            let angle = Math.atan2(dy, dx);
            alligator.x += Math.cos(angle) * alligator.speed;
            alligator.y += Math.sin(angle) * alligator.speed;
        }

        // Check for collision between Lee (pacman) and Carol
        function checkCollision() {
            const dx = pacman.x - carol.x;
            const dy = pacman.y - carol.y;
            const distance = Math.sqrt(dx * dx + dy * dy);

            if (distance < pacman.size + carol.size / 2) {
                score++;
                scoreDisplay.textContent = 'Score: ' + score;
                // Move Carol to a new random position
                carol.x = Math.random() * (canvas.width - carol.size) + carol.size;
                carol.y = Math.random() * (canvas.height - carol.size) + carol.size;
            }

            // Check for collision between Lee (pacman) and Alligator
            const ax = pacman.x - alligator.x;
            const ay = pacman.y - alligator.y;
            const alligatorDistance = Math.sqrt(ax * ax + ay * ay);

            // If Pac-Man collides with the alligator and the alligator is visible
            if (alligatorDistance < pacman.size + alligator.size / 2 && alligatorVisible) {
                // Hide the alligator
                alligatorVisible = false;

                // Make the alligator reappear after a brief delay
                setTimeout(() => {
                    alligatorVisible = true; // Alligator reappears
                    // Decrease score only after alligator disappears
                    if (score > 0) {
                        score--;
                        scoreDisplay.textContent = 'Score: ' + score;
                    }
                }, 1000); // Alligator disappears for 1 second
            }

            // Check if the score has reached 10, game win condition
            if (score >= 10) {
                gameRunning = false;
                winMessage.style.display = 'block'; // Show win message
            }
        }

        // Main game loop
        function gameLoop() {
            if (!gameRunning) return;

            // Clear canvas
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Draw Pac-Man, Carol, and Alligator
            drawPacman();
            drawCarol();
            drawAlligator();

            // Update positions
            updatePositions();
            checkCollision();

            // Request the next frame
            requestAnimationFrame(gameLoop);
        }
    </script>
</body>
</html>
