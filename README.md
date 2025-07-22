<!-- Ahmed Attafi | Software Developer & IoT Specialist -->

<div align="center">

# Hi, I'm Ahmed Attafi 👋

<p>
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=24&pause### Interactive Fun Zone 🎮

<details>
<summary>🎯 Click here for some fun!</summary>

**🐍 ASCII Snake Stats:**
```
┌─────────────────────────────────────┐
│  Games Played: ∞                   │
│  High Score: 99999                  │
│  Bugs Squashed: All of them! 🐛💥   │
│  Fun Level: Maximum! 🎮✨           │
└─────────────────────────────────────┘
```

**Random Dev Quote:**
> "Code is like humor. When you have to explain it, it's bad." – Cory House

**Fun Facts:**
- ☕ I debug better with coffee
- 🌙 Night owl programmer  
- 🐛 I call bugs "features in development"
- 🎮 Life is just a complex algorithm

**Interactive Command Line:**
```bash
$ whoami
ahmed-attafi

$ cat skills.txt
Web Development ████████████ 95%
IoT Systems     ██████████   85%
Cloud Tech      ████████     80%
Problem Solving ████████████ 99%

$ echo "Want to collaborate?"
Yes! Feel free to reach out! 🚀

$ ./snake_game.exe
🐍 Starting auto-snake game...
🎮 Score: Climbing to infinity!
🏆 Result: Always winning! 
```

</details>F&center=true&vCenter=true&width=500&lines=Software+Developer;IoT+Specialist;Cloud+Enthusiast;Always+Learning"/>
</p>

---

### 🐍 Watch the snake eat my contributions!

<div align="center">

<!-- GitHub Contribution Snake Animation -->
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Attafii/Attafii/output/github-contribution-grid-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Attafii/Attafii/output/github-contribution-grid-snake.svg">
  <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/Attafii/Attafii/output/github-contribution-grid-snake.svg">
</picture>

<!-- Real Playable Snake Game -->
<div id="real-snake-game">
  <h4>🎮 Real Snake Game - Use Arrow Keys!</h4>
  <div id="game-controls">
    <button id="start-btn">🚀 Start Game</button>
    <button id="pause-btn">⏸️ Pause</button>
    <button id="reset-btn">🔄 Reset</button>
  </div>
  <div id="game-info">
    <span>Score: <strong id="real-score">0</strong></span>
    <span>High Score: <strong id="high-score">0</strong></span>
    <span>Speed: <strong id="speed-level">1</strong></span>
  </div>
  <canvas id="snake-canvas" width="400" height="400"></canvas>
  <div id="game-instructions">
    <p>🎯 Use Arrow Keys to control the snake</p>
    <p>🍎 Eat the food to grow and increase score</p>
    <p>⚠️ Don't hit the walls or yourself!</p>
  </div>
  <div id="victory-msg" style="display: none;">
    <h3 id="win-text">🎉 Amazing! 🎉</h3>
    <p id="win-message"></p>
  </div>
</div>

<script>
class SnakeGame {
  constructor() {
    this.canvas = document.getElementById('snake-canvas');
    this.ctx = this.canvas.getContext('2d');
    this.gridSize = 20;
    this.tileCount = this.canvas.width / this.gridSize;
    
    this.snake = [
      {x: 10, y: 10}
    ];
    this.food = this.generateFood();
    this.dx = 0;
    this.dy = 0;
    this.score = 0;
    this.highScore = localStorage.getItem('snakeHighScore') || 0;
    this.gameRunning = false;
    this.speed = 150;
    this.speedLevel = 1;
    
    this.winMessages = [
      "🚀 Incredible! You're debugging life like a pro! 🐛➡️✨",
      "💻 Epic! Your coding skills are as smooth as this snake! 🐍💫",
      "🏆 Legendary! You turned bugs into features again! 🎯🌟",
      "☕ Amazing! Time to celebrate with coffee! ☕🎊",
      "🎮 Perfect! You're the Neo of snake games! 🕶️💻",
      "🌟 Fantastic! Your problem-solving is next level! 🚀✨",
      "🎉 Outstanding! Ready to tackle some real code? 💻🔥"
    ];
    
    this.setupEventListeners();
    this.updateHighScore();
    this.draw();
  }
  
  setupEventListeners() {
    document.getElementById('start-btn').addEventListener('click', () => this.startGame());
    document.getElementById('pause-btn').addEventListener('click', () => this.pauseGame());
    document.getElementById('reset-btn').addEventListener('click', () => this.resetGame());
    
    document.addEventListener('keydown', (e) => this.changeDirection(e));
  }
  
  generateFood() {
    return {
      x: Math.floor(Math.random() * this.tileCount),
      y: Math.floor(Math.random() * this.tileCount)
    };
  }
  
  startGame() {
    if (!this.gameRunning) {
      this.gameRunning = true;
      this.gameLoop();
    }
  }
  
  pauseGame() {
    this.gameRunning = false;
  }
  
  resetGame() {
    this.gameRunning = false;
    this.snake = [{x: 10, y: 10}];
    this.food = this.generateFood();
    this.dx = 0;
    this.dy = 0;
    this.score = 0;
    this.speed = 150;
    this.speedLevel = 1;
    this.updateScore();
    this.updateSpeed();
    this.hideVictoryMessage();
    this.draw();
  }
  
  changeDirection(e) {
    if (!this.gameRunning) return;
    
    const LEFT_KEY = 37;
    const RIGHT_KEY = 39;
    const UP_KEY = 38;
    const DOWN_KEY = 40;
    
    const keyPressed = e.keyCode;
    const goingUp = this.dy === -1;
    const goingDown = this.dy === 1;
    const goingRight = this.dx === 1;
    const goingLeft = this.dx === -1;
    
    if (keyPressed === LEFT_KEY && !goingRight) {
      this.dx = -1;
      this.dy = 0;
    }
    if (keyPressed === UP_KEY && !goingDown) {
      this.dx = 0;
      this.dy = -1;
    }
    if (keyPressed === RIGHT_KEY && !goingLeft) {
      this.dx = 1;
      this.dy = 0;
    }
    if (keyPressed === DOWN_KEY && !goingUp) {
      this.dx = 0;
      this.dy = 1;
    }
  }
  
  gameLoop() {
    if (!this.gameRunning) return;
    
    setTimeout(() => {
      this.clearCanvas();
      this.moveSnake();
      this.drawFood();
      this.drawSnake();
      
      if (this.checkGameEnd()) {
        this.gameRunning = false;
        this.showGameOver();
        return;
      }
      
      this.gameLoop();
    }, this.speed);
  }
  
  clearCanvas() {
    this.ctx.fillStyle = '#0d1117';
    this.ctx.fillRect(0, 0, this.canvas.width, this.canvas.height);
    
    // Draw grid
    this.ctx.strokeStyle = '#1f2937';
    this.ctx.lineWidth = 1;
    for (let i = 0; i <= this.tileCount; i++) {
      this.ctx.beginPath();
      this.ctx.moveTo(i * this.gridSize, 0);
      this.ctx.lineTo(i * this.gridSize, this.canvas.height);
      this.ctx.stroke();
      
      this.ctx.beginPath();
      this.ctx.moveTo(0, i * this.gridSize);
      this.ctx.lineTo(this.canvas.width, i * this.gridSize);
      this.ctx.stroke();
    }
  }
  
  moveSnake() {
    const head = {x: this.snake[0].x + this.dx, y: this.snake[0].y + this.dy};
    this.snake.unshift(head);
    
    if (head.x === this.food.x && head.y === this.food.y) {
      this.score += 10;
      this.updateScore();
      this.food = this.generateFood();
      this.increaseSpeed();
      
      // Check for victory messages
      if (this.score > 0 && this.score % 100 === 0) {
        this.showVictoryMessage();
      }
    } else {
      this.snake.pop();
    }
  }
  
  drawSnake() {
    this.snake.forEach((segment, index) => {
      if (index === 0) {
        // Head
        this.ctx.fillStyle = '#00ff00';
        this.ctx.fillRect(segment.x * this.gridSize + 2, segment.y * this.gridSize + 2, 
                         this.gridSize - 4, this.gridSize - 4);
        
        // Eyes
        this.ctx.fillStyle = '#000';
        this.ctx.fillRect(segment.x * this.gridSize + 6, segment.y * this.gridSize + 6, 3, 3);
        this.ctx.fillRect(segment.x * this.gridSize + 11, segment.y * this.gridSize + 6, 3, 3);
      } else {
        // Body
        this.ctx.fillStyle = '#00D9FF';
        this.ctx.fillRect(segment.x * this.gridSize + 1, segment.y * this.gridSize + 1, 
                         this.gridSize - 2, this.gridSize - 2);
      }
    });
  }
  
  drawFood() {
    this.ctx.fillStyle = '#ff0000';
    this.ctx.fillRect(this.food.x * this.gridSize + 3, this.food.y * this.gridSize + 3, 
                     this.gridSize - 6, this.gridSize - 6);
    
    // Apple stem
    this.ctx.fillStyle = '#00ff00';
    this.ctx.fillRect(this.food.x * this.gridSize + 9, this.food.y * this.gridSize + 1, 2, 4);
  }
  
  checkGameEnd() {
    const head = this.snake[0];
    
    // Wall collision
    if (head.x < 0 || head.x >= this.tileCount || head.y < 0 || head.y >= this.tileCount) {
      return true;
    }
    
    // Self collision
    for (let i = 1; i < this.snake.length; i++) {
      if (head.x === this.snake[i].x && head.y === this.snake[i].y) {
        return true;
      }
    }
    
    return false;
  }
  
  updateScore() {
    document.getElementById('real-score').textContent = this.score;
    if (this.score > this.highScore) {
      this.highScore = this.score;
      localStorage.setItem('snakeHighScore', this.highScore);
      this.updateHighScore();
    }
  }
  
  updateHighScore() {
    document.getElementById('high-score').textContent = this.highScore;
  }
  
  updateSpeed() {
    document.getElementById('speed-level').textContent = this.speedLevel;
  }
  
  increaseSpeed() {
    if (this.score % 50 === 0 && this.speed > 80) {
      this.speed -= 10;
      this.speedLevel++;
      this.updateSpeed();
    }
  }
  
  showVictoryMessage() {
    const randomMessage = this.winMessages[Math.floor(Math.random() * this.winMessages.length)];
    document.getElementById('win-message').textContent = randomMessage;
    document.getElementById('victory-msg').style.display = 'block';
    
    setTimeout(() => {
      this.hideVictoryMessage();
    }, 3000);
  }
  
  hideVictoryMessage() {
    document.getElementById('victory-msg').style.display = 'none';
  }
  
  showGameOver() {
    let message = "💥 Game Over! ";
    if (this.score >= 200) {
      message += "🏆 Legendary performance! You're a coding wizard! 🧙‍♂️✨";
    } else if (this.score >= 100) {
      message += "🎉 Excellent! Your debugging skills are showing! 🐛➡️🌟";
    } else if (this.score >= 50) {
      message += "👍 Good job! You're getting the hang of it! 💻🚀";
    } else {
      message += "🎯 Nice try! Every expert was once a beginner! 💪";
    }
    
    document.getElementById('win-text').textContent = "🎮 Game Over!";
    document.getElementById('win-message').textContent = message;
    document.getElementById('victory-msg').style.display = 'block';
  }
  
  draw() {
    this.clearCanvas();
    this.drawFood();
    this.drawSnake();
  }
}

// Initialize the game when the page loads
let snakeGame;
document.addEventListener('DOMContentLoaded', () => {
  snakeGame = new SnakeGame();
});
</script>

<style>
#real-snake-game {
  background: linear-gradient(135deg, #0d1117 0%, #161b22 100%);
  border: 2px solid #00D9FF;
  border-radius: 15px;
  padding: 20px;
  margin: 20px auto;
  max-width: 450px;
  font-family: 'Courier New', monospace;
  color: #00D9FF;
  text-align: center;
}

#game-controls {
  margin: 15px 0;
}

#game-controls button {
  background: linear-gradient(45deg, #00D9FF, #0099cc);
  color: #000;
  border: none;
  padding: 8px 15px;
  margin: 0 5px;
  border-radius: 20px;
  cursor: pointer;
  font-weight: bold;
  transition: transform 0.2s;
}

#game-controls button:hover {
  transform: scale(1.05);
}

#game-info {
  display: flex;
  justify-content: space-around;
  margin: 15px 0;
  font-size: 14px;
}

#snake-canvas {
  border: 2px solid #00D9FF;
  border-radius: 10px;
  background: #0d1117;
  display: block;
  margin: 15px auto;
}

#game-instructions {
  font-size: 12px;
  margin-top: 10px;
  color: #8b949e;
}

#victory-msg {
  background: linear-gradient(45deg, #00ff00, #00D9FF);
  color: #000;
  padding: 15px;
  border-radius: 10px;
  margin-top: 15px;
  animation: celebration 0.5s ease-in-out;
}

@keyframes celebration {
  0% { transform: scale(0.8); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}
</style>

</div>

<!-- Auto-Playing ASCII Snake Game -->
<div id="snake-game-container">
  <h4>🎮 Auto-Playing Snake Game</h4>
  <div id="snake-board">
    <div id="game-area">
      ┌────────────────────────────────────────┐<br>
      │<span id="snake-line-1">🐍💻🍎    ░░░░░░░░░    🍎��🐍</span>│<br>
      │<span id="snake-line-2">    🍎    ░░░░░░░░░    🍎    </span>│<br>
      │<span id="snake-line-3">💻🐍🍎    ░░██████░░    🍎��💻</span>│<br>
      │<span id="snake-line-4">          ░██SNAKE██░          </span>│<br>
      │<span id="snake-line-5">🍎🐍💻    ░░██████░░    ��🐍🍎</span>│<br>
      │<span id="snake-line-6">    🍎    ░░░░░░░░░    🍎    </span>│<br>
      │<span id="snake-line-7">��💻🍎    ░░░░░░░░░    🍎��🐍</span>│<br>
      └────────────────────────────────────────┘<br>
    </div>
    <div id="game-status">
      Score: <span id="score">0</span> | Status: <span id="status">Playing...</span>
    </div>
    <div id="victory-message" style="display: none;">
      <h3>🎉 VICTORY! 🎉</h3>
      <p id="celebration-text">🚀 Wow! You're as good at this as you are at debugging! 🐛➡️✨</p>
    </div>
  </div>
</div>

<script>
(function() {
  let score = 0;
  let gameRunning = true;
  const celebrationMessages = [
    "🎉 Amazing! You code better than this snake plays! 💻✨",
    "🚀 Victory! Time to celebrate with coffee! ☕🎊",
    "🏆 Winner! Your debugging skills are legendary! 🐛➡️🌟",
    "🎯 Perfect! You turned this bug into a feature! 🐍➡️🏅",
    "💫 Incredible! You're the Neo of the coding matrix! 🕶️💻",
    "🎮 Game Over = You Win! Ready for the next challenge? �",
    "🌟 Fantastic! Your code quality is as smooth as this gameplay! ✨"
  ];
  
  function updateScore() {
    score += Math.floor(Math.random() * 10) + 1;
    document.getElementById('score').textContent = score;
    
    if (score > 100 && gameRunning) {
      gameRunning = false;
      const randomMessage = celebrationMessages[Math.floor(Math.random() * celebrationMessages.length)];
      document.getElementById('status').textContent = 'WINNER!';
      document.getElementById('celebration-text').textContent = randomMessage;
      document.getElementById('victory-message').style.display = 'block';
      
      // Restart game after 5 seconds
      setTimeout(() => {
        score = 0;
        gameRunning = true;
        document.getElementById('victory-message').style.display = 'none';
        document.getElementById('status').textContent = 'Playing...';
      }, 5000);
    }
  }
  
  // Auto-play the game
  setInterval(() => {
    if (gameRunning) {
      updateScore();
      
      // Animate snake movement
      const lines = ['snake-line-1', 'snake-line-2', 'snake-line-3', 'snake-line-5', 'snake-line-6', 'snake-line-7'];
      lines.forEach(lineId => {
        const element = document.getElementById(lineId);
        if (element) {
          const content = element.textContent;
          element.textContent = content.substring(1) + content[0];
        }
      });
    }
  }, 500);
})();
</script>

<style>
#snake-game-container {
  background: linear-gradient(135deg, #0d1117 0%, #161b22 100%);
  border: 2px solid #00D9FF;
  border-radius: 10px;
  padding: 20px;
  margin: 20px auto;
  max-width: 500px;
  font-family: 'Courier New', monospace;
  color: #00D9FF;
}

#game-area {
  background: #000;
  padding: 10px;
  border-radius: 5px;
  text-align: center;
  font-size: 14px;
  line-height: 1.2;
}

#game-status {
  margin-top: 10px;
  text-align: center;
  font-weight: bold;
}

#victory-message {
  background: linear-gradient(45deg, #00ff00, #00D9FF);
  color: #000;
  padding: 15px;
  border-radius: 10px;
  margin-top: 10px;
  text-align: center;
  animation: celebration 1s ease-in-out infinite alternate;
}

@keyframes celebration {
  0% { transform: scale(1); }
  100% { transform: scale(1.05); }
}

.snake-container {
  animation: snake-move 4s linear infinite;
  font-size: 20px;
  margin: 10px 0;
}

@keyframes snake-move {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}
</style>

</div>

---

</div>

## About Me

I'm a Software Developer and IoT Specialist based in Tunisia 🇹🇳, passionate about creating innovative solutions.

**Currently:** Automotive Software QA Engineer @ Capgemini Engineering  
**Focus:** Web Development, IoT Systems, Cloud Technologies  
**Motto:** Turning ideas into code, one commit at a time ☕

### What I Work With

```
Frontend    │ HTML • CSS • JavaScript • React
Backend     │ Python • C# • C++ • Node.js
IoT         │ Arduino • Raspberry Pi • Sensors
Cloud       │ Azure • Firebase
Tools       │ Git • Docker • Jenkins
```

### Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ahmed-attafi/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/Attafii)
[![Medium](https://img.shields.io/badge/Medium-12100E?style=flat&logo=medium&logoColor=white)](https://medium.com/@attafii)
[![Behance](https://img.shields.io/badge/Behance-1769FF?style=flat&logo=behance&logoColor=white)](https://www.behance.net/ahmedattafi_)

![Profile Views](https://komarev.com/ghpvc/?username=Attafii&color=00D9FF&style=flat)

</div>

### Stats

<div align="center">

<img height="160" src="https://github-readme-stats.vercel.app/api?username=Attafii&show_icons=true&theme=dark&hide_border=true&bg_color=0d1117&title_color=00D9FF&icon_color=00D9FF"/>
<img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Attafii&layout=compact&theme=dark&hide_border=true&bg_color=0d1117&title_color=00D9FF"/>

<img src="https://github-readme-streak-stats.herokuapp.com/?user=Attafii&theme=dark&hide_border=true&background=0d1117&stroke=00D9FF&ring=00D9FF&fire=00D9FF&currStreakLabel=00D9FF"/>

</div>

### Interactive Fun Zone 🎮

<details>
<summary>🎯 Click here for some fun!</summary>

**Random Dev Quote:**
> "Code is like humor. When you have to explain it, it's bad." – Cory House

**Fun Facts:**
- ☕ I debug better with coffee
- 🌙 Night owl programmer
- 🐛 I call bugs "features in development"
- � Life is just a complex algorithm

**Want to collaborate?** Feel free to reach out!

</details>

---

<div align="center">

**Thanks for visiting! Let's build something amazing together! 🚀**

</div>
