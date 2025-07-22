<!-- Ahmed Attafi | Software Developer & IoT Specialist -->

<div align="center">

# Hi, I'm Ahmed Attafi 👋

<p>
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=24&pause=1000&color=00D9FF&center=true&vCenter=true&width=500&lines=Software+Developer;IoT+Specialist;Cloud+Enthusiast;Always+Learning"/>
</p>

---

🧠 close your eyes , let's play a funny game

<div id="contribution-snake">
  <div class="grid-container">
    <div class="contribution-grid" id="snake-grid"></div>
  </div>
</div>

▶ now open 🧠

---

### 📊 Quick Stats

```
🔥 Commits This Year: 420+
⭐ Stars Earned: 89
🔀 Pull Requests: 156
🐛 Issues Closed: 73
☕ Coffee Consumed: ∞
```

### 🎯 Fun Facts

- 🌙 **Night Owl Coder** - Best commits happen after midnight
- 🐛 **Bug Whisperer** - I speak fluent debugging
- ☕ **Coffee Dependent** - My code runs on caffeine
- 🎮 **Code Gamer** - Turning algorithms into art

---

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

---

### Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ahmed-attafi/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/Attafii)
[![Medium](https://img.shields.io/badge/Medium-12100E?style=flat&logo=medium&logoColor=white)](https://medium.com/@attafii)
[![Behance](https://img.shields.io/badge/Behance-1769FF?style=flat&logo=behance&logoColor=white)](https://www.behance.net/ahmedattafi_)

![Profile Views](https://komarev.com/ghpvc/?username=Attafii&color=00D9FF&style=flat)

</div>

---

### Stats

<div align="center">

<img height="160" src="https://github-readme-stats.vercel.app/api?username=Attafii&show_icons=true&theme=dark&hide_border=true&bg_color=0d1117&title_color=00D9FF&icon_color=00D9FF"/>
<img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Attafii&layout=compact&theme=dark&hide_border=true&bg_color=0d1117&title_color=00D9FF"/>

<img src="https://github-readme-streak-stats.herokuapp.com/?user=Attafii&theme=dark&hide_border=true&background=0d1117&stroke=00D9FF&ring=00D9FF&fire=00D9FF&currStreakLabel=00D9FF"/>

</div>

---

### Interactive Fun Zone 🎮

<details>
<summary>🎯 Click here for some fun!</summary>

**Random Dev Quote:**
> "Code is like humor. When you have to explain it, it's bad." – Cory House

**Today's Mood:**
```
if (coffee.available()) {
    mood = "Ready to code! ☕";
} else {
    mood = "404: Motivation not found";
}
```

**Developer Level:**
```
[████████████████████] 99% Complete
Missing: Just one more tutorial... 📚
```

</details>

---

<div align="center">

**Thanks for visiting! Let's build something amazing together! 🚀**

</div>

<script>
// Contribution Snake Animation
class ContributionSnake {
  constructor() {
    this.grid = document.getElementById('snake-grid');
    this.width = 52; // weeks in a year
    this.height = 7; // days in a week
    this.snake = [];
    this.direction = { x: 1, y: 0 };
    this.speed = 150;
    
    this.createGrid();
    this.initSnake();
    this.animate();
  }
  
  createGrid() {
    if (!this.grid) return;
    
    this.grid.innerHTML = '';
    for (let week = 0; week < this.width; week++) {
      for (let day = 0; day < this.height; day++) {
        const cell = document.createElement('div');
        cell.className = 'grid-cell';
        cell.dataset.week = week;
        cell.dataset.day = day;
        
        // Add some random contributions
        const intensity = Math.random();
        if (intensity > 0.7) cell.classList.add('level-4');
        else if (intensity > 0.5) cell.classList.add('level-3');
        else if (intensity > 0.3) cell.classList.add('level-2');
        else if (intensity > 0.1) cell.classList.add('level-1');
        
        this.grid.appendChild(cell);
      }
    }
  }
  
  initSnake() {
    // Start snake in the middle-left
    this.snake = [
      { x: 0, y: 3 },
      { x: 1, y: 3 },
      { x: 2, y: 3 },
      { x: 3, y: 3 }
    ];
    this.updateSnakeDisplay();
  }
  
  updateSnakeDisplay() {
    // Clear previous snake
    const cells = this.grid.querySelectorAll('.grid-cell');
    cells.forEach(cell => {
      cell.classList.remove('snake-head', 'snake-body');
    });
    
    // Draw new snake
    this.snake.forEach((segment, index) => {
      const cell = this.grid.querySelector(`[data-week="${segment.x}"][data-day="${segment.y}"]`);
      if (cell) {
        if (index === this.snake.length - 1) {
          cell.classList.add('snake-head');
        } else {
          cell.classList.add('snake-body');
        }
      }
    });
  }
  
  moveSnake() {
    const head = this.snake[this.snake.length - 1];
    const newHead = {
      x: head.x + this.direction.x,
      y: head.y + this.direction.y
    };
    
    // Check boundaries and change direction
    if (newHead.x >= this.width) {
      // Hit right wall, go down
      this.direction = { x: 0, y: 1 };
      newHead.x = head.x;
      newHead.y = head.y + 1;
    } else if (newHead.y >= this.height) {
      // Hit bottom wall, go left
      this.direction = { x: -1, y: 0 };
      newHead.y = head.y;
      newHead.x = head.x - 1;
    } else if (newHead.x < 0) {
      // Hit left wall, go up
      this.direction = { x: 0, y: -1 };
      newHead.x = head.x;
      newHead.y = head.y - 1;
    } else if (newHead.y < 0) {
      // Hit top wall, go right
      this.direction = { x: 1, y: 0 };
      newHead.y = head.y;
      newHead.x = head.x + 1;
    }
    
    // Add new head
    this.snake.push(newHead);
    
    // Remove tail (keep snake length constant)
    if (this.snake.length > 8) {
      this.snake.shift();
    }
    
    this.updateSnakeDisplay();
  }
  
  animate() {
    this.moveSnake();
    setTimeout(() => this.animate(), this.speed);
  }
}

// Initialize snake animation when page loads
document.addEventListener('DOMContentLoaded', () => {
  new ContributionSnake();
});

// Also initialize immediately if DOM is already loaded
if (document.readyState !== 'loading') {
  new ContributionSnake();
}
</script>

<style>
#contribution-snake {
  display: flex;
  justify-content: center;
  margin: 20px 0;
  padding: 20px;
  background: #0d1117;
  border-radius: 8px;
  border: 1px solid #21262d;
}

.grid-container {
  background: #0d1117;
  padding: 16px;
  border-radius: 6px;
}

.contribution-grid {
  display: grid;
  grid-template-columns: repeat(52, 1fr);
  grid-template-rows: repeat(7, 1fr);
  gap: 2px;
  max-width: 800px;
}

.grid-cell {
  width: 11px;
  height: 11px;
  background-color: #161b22;
  border-radius: 2px;
  transition: all 0.3s ease;
}

/* Contribution levels */
.grid-cell.level-1 { background-color: #0e4429; }
.grid-cell.level-2 { background-color: #006d32; }
.grid-cell.level-3 { background-color: #26a641; }
.grid-cell.level-4 { background-color: #39d353; }

/* Snake styling */
.grid-cell.snake-body {
  background-color: #00D9FF !important;
  border-radius: 50%;
  transform: scale(1.1);
  box-shadow: 0 0 8px rgba(0, 217, 255, 0.6);
}

.grid-cell.snake-head {
  background-color: #00ff00 !important;
  border-radius: 50%;
  transform: scale(1.2);
  box-shadow: 0 0 12px rgba(0, 255, 0, 0.8);
  position: relative;
}

.grid-cell.snake-head::before {
  content: '';
  position: absolute;
  top: 2px;
  left: 2px;
  width: 2px;
  height: 2px;
  background: #000;
  border-radius: 50%;
}

.grid-cell.snake-head::after {
  content: '';
  position: absolute;
  top: 2px;
  right: 2px;
  width: 2px;
  height: 2px;
  background: #000;
  border-radius: 50%;
}

/* Responsive design */
@media (max-width: 768px) {
  .contribution-grid {
    grid-template-columns: repeat(26, 1fr);
    max-width: 400px;
  }
  
  .grid-cell {
    width: 8px;
    height: 8px;
  }
}
</style>
