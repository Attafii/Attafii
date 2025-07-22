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
