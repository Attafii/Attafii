<!-- Ahmed Attafi | Software Developer & IoT Specialist -->

<div align="center">

# Hi, I'm Ahmed Attafi 👋

<p>
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=24&pause=1000&color=00D9FF&center=true&vCenter=true&width=500&lines=Software+Developer;IoT+Specialist;Cloud+Enthusiast;Always+Learning"/>
</p>

---

### 🐍 Watch the snake eat my contributions!

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Attafii/Attafii/output/github-contribution-grid-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Attafii/Attafii/output/github-contribution-grid-snake.svg">
  <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/Attafii/Attafii/output/github-contribution-grid-snake.svg">
</picture>

<!-- Interactive Code Terminal -->
<div id="interactive-terminal">
  <div class="terminal-header">
    <div class="terminal-buttons">
      <div class="btn red"></div>
      <div class="btn yellow"></div>
      <div class="btn green"></div>
    </div>
    <span class="terminal-title">ahmed@dev:~$</span>
  </div>
  <div class="terminal-body">
    <div id="terminal-content">
      <div class="terminal-line">
        <span class="prompt">$</span>
        <span class="command">whoami</span>
      </div>
      <div class="output">ahmed-attafi</div>
      
      <div class="terminal-line">
        <span class="prompt">$</span>
        <span class="command">cat passion.txt</span>
      </div>
      <div class="output">Building innovative solutions with code ✨</div>
      
      <div class="terminal-line">
        <span class="prompt">$</span>
        <span class="command">ls skills/</span>
      </div>
      <div class="output">javascript/ python/ iot/ cloud/ problem-solving/</div>
      
      <div class="terminal-line interactive-line">
        <span class="prompt">$</span>
        <input type="text" id="user-input" placeholder="try: help, about, skills, contact" autocomplete="off">
        <span class="cursor">|</span>
      </div>
    </div>
  </div>
</div>

</div>

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

</details>

---

<div align="center">

**Thanks for visiting! Let's build something amazing together! 🚀**

</div>

<script>
// Interactive Terminal
class InteractiveTerminal {
  constructor() {
    this.input = document.getElementById('user-input');
    this.content = document.getElementById('terminal-content');
    this.commands = {
      help: 'Available commands: about, skills, contact, clear, joke, coffee',
      about: 'Software Developer & IoT Specialist from Tunisia 🇹🇳\nPassionate about creating innovative solutions!',
      skills: 'JavaScript ████████████ 95%\nPython      ██████████   85%\nIoT Systems ███████████  90%\nCloud Tech  ████████     80%',
      contact: 'LinkedIn: /in/ahmed-attafi\nGitHub: @Attafii\nReady to collaborate! 🚀',
      clear: 'CLEAR_TERMINAL',
      joke: 'Why do programmers prefer dark mode?\nBecause light attracts bugs! 🐛💡',
      coffee: 'Brewing coffee... ☕\n[████████████] 100%\nCoffee ready! Time to code! 💻'
    };
    
    if (this.input) {
      this.setupEventListeners();
      this.animateCursor();
    }
  }
  
  setupEventListeners() {
    this.input.addEventListener('keypress', (e) => {
      if (e.key === 'Enter') {
        this.executeCommand();
      }
    });
    
    this.input.addEventListener('focus', () => {
      this.input.style.outline = 'none';
    });
  }
  
  executeCommand() {
    const command = this.input.value.trim().toLowerCase();
    
    if (command) {
      // Add command to terminal
      this.addLine(`$ ${command}`, 'command');
      
      // Execute command
      if (this.commands[command]) {
        if (command === 'clear') {
          this.clearTerminal();
        } else {
          this.addLine(this.commands[command], 'output');
        }
      } else {
        this.addLine(`Command not found: ${command}\nType 'help' for available commands`, 'output error');
      }
      
      this.input.value = '';
      this.scrollToBottom();
    }
  }
  
  addLine(text, className = '') {
    const lines = text.split('\n');
    lines.forEach(line => {
      const div = document.createElement('div');
      div.className = `terminal-line ${className}`;
      if (className === 'command') {
        div.innerHTML = `<span class="prompt">$</span> <span class="command">${line.substring(2)}</span>`;
      } else {
        div.innerHTML = `<div class="output ${className}">${line}</div>`;
      }
      
      // Insert before the interactive line
      const interactiveLine = document.querySelector('.interactive-line');
      this.content.insertBefore(div, interactiveLine);
    });
  }
  
  clearTerminal() {
    const lines = this.content.querySelectorAll('.terminal-line:not(.interactive-line)');
    lines.forEach(line => line.remove());
  }
  
  scrollToBottom() {
    const terminal = document.getElementById('interactive-terminal');
    if (terminal) {
      terminal.scrollTop = terminal.scrollHeight;
    }
  }
  
  animateCursor() {
    const cursor = document.querySelector('.cursor');
    if (cursor) {
      setInterval(() => {
        cursor.style.opacity = cursor.style.opacity === '0' ? '1' : '0';
      }, 500);
    }
  }
}

// Initialize terminal when page loads
document.addEventListener('DOMContentLoaded', () => {
  new InteractiveTerminal();
});

// Also initialize immediately if DOM is already loaded
if (document.readyState !== 'loading') {
  new InteractiveTerminal();
}
</script>

<style>
#interactive-terminal {
  background: #0d1117;
  border: 1px solid #30363d;
  border-radius: 8px;
  margin: 20px auto;
  max-width: 600px;
  font-family: 'Monaco', 'Menlo', 'Ubuntu Mono', monospace;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
  overflow: hidden;
}

.terminal-header {
  background: #21262d;
  padding: 12px 16px;
  display: flex;
  align-items: center;
  border-bottom: 1px solid #30363d;
}

.terminal-buttons {
  display: flex;
  gap: 8px;
  margin-right: 16px;
}

.btn {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}

.btn.red { background: #ff5f56; }
.btn.yellow { background: #ffbd2e; }
.btn.green { background: #27ca3f; }

.terminal-title {
  color: #f0f6fc;
  font-size: 13px;
  font-weight: 500;
}

.terminal-body {
  padding: 16px;
  max-height: 300px;
  overflow-y: auto;
}

.terminal-line {
  margin: 4px 0;
  display: flex;
  align-items: center;
  line-height: 1.5;
}

.prompt {
  color: #00D9FF;
  margin-right: 8px;
  font-weight: bold;
}

.command {
  color: #a5d6ff;
}

.output {
  color: #f0f6fc;
  margin-left: 24px;
  white-space: pre-line;
  font-size: 14px;
}

.output.error {
  color: #ff7b72;
}

.interactive-line {
  margin-top: 8px;
}

#user-input {
  background: transparent;
  border: none;
  color: #a5d6ff;
  font-family: inherit;
  font-size: 14px;
  outline: none;
  flex: 1;
  margin-left: 8px;
}

#user-input::placeholder {
  color: #656d76;
  font-style: italic;
}

.cursor {
  color: #00D9FF;
  font-weight: bold;
  margin-left: 4px;
  animation: blink 1s infinite;
}

@keyframes blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}

/* Scrollbar styling */
.terminal-body::-webkit-scrollbar {
  width: 6px;
}

.terminal-body::-webkit-scrollbar-track {
  background: #21262d;
}

.terminal-body::-webkit-scrollbar-thumb {
  background: #656d76;
  border-radius: 3px;
}

.terminal-body::-webkit-scrollbar-thumb:hover {
  background: #768390;
}
</style>
