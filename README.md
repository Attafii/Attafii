<!-- Ahmed Attafi | Software Developer & IoT Specialist -->

<div align="center">

# Hi, I'm Ahmed Attafi 👋

<p>
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=24&pause=1000&color=00D9FF&center=true&vCenter=true&width=500&lines=Software+Developer;IoT+Specialist;Cloud+Enthusiast;Always+Learning"/>
</p>

---

💻 watch my code come to life

<div id="code-visualization">
  <div class="code-editor">
    <div class="editor-header">
      <div class="editor-buttons">
        <div class="btn red"></div>
        <div class="btn yellow"></div>
        <div class="btn green"></div>
      </div>
      <span class="file-name">ahmed-attafi.js</span>
    </div>
    <div class="code-content">
      <div class="line-numbers" id="line-numbers"></div>
      <div class="code-lines" id="code-lines"></div>
    </div>
    <div class="status-bar">
      <span>Lines: <span id="line-count">0</span></span>
      <span>Language: JavaScript</span>
      <span>💚 Live</span>
    </div>
  </div>
</div>

✨ building the future, one line at a time

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
// Animated Code Visualization
class CodeVisualization {
  constructor() {
    this.codeLines = document.getElementById('code-lines');
    this.lineNumbers = document.getElementById('line-numbers');
    this.lineCount = document.getElementById('line-count');
    
    this.code = [
      "// Welcome to Ahmed's coding journey ✨",
      "",
      "class Developer {",
      "  constructor() {",
      "    this.name = 'Ahmed Attafi';",
      "    this.location = 'Tunisia 🇹🇳';",
      "    this.passion = 'Building innovative solutions';",
      "    this.coffee = Infinity;",
      "  }",
      "",
      "  getCurrentRole() {",
      "    return 'Automotive Software QA Engineer @ Capgemini';",
      "  }",
      "",
      "  getSkills() {",
      "    return {",
      "      frontend: ['HTML', 'CSS', 'JavaScript', 'React'],",
      "      backend: ['Python', 'C#', 'C++', 'Node.js'],",
      "      iot: ['Arduino', 'Raspberry Pi', 'Sensors'],",
      "      cloud: ['Azure', 'Firebase'],",
      "      tools: ['Git', 'Docker', 'Jenkins']",
      "    };",
      "  }",
      "",
      "  debugCode() {",
      "    while (this.coffee > 0) {",
      "      this.solveProblem();",
      "      this.coffee--;",
      "    }",
      "    this.brewMoreCoffee();",
      "  }",
      "",
      "  collaborate() {",
      "    return 'Always ready for new challenges! 🚀';",
      "  }",
      "}",
      "",
      "const ahmed = new Developer();",
      "console.log(ahmed.collaborate());"
    ];
    
    this.currentLine = 0;
    this.currentChar = 0;
    this.isDeleting = false;
    this.typeSpeed = 50;
    this.deleteSpeed = 25;
    this.pauseTime = 2000;
    
    this.startAnimation();
  }
  
  startAnimation() {
    this.typeCode();
  }
  
  typeCode() {
    if (this.currentLine < this.code.length) {
      const line = this.code[this.currentLine];
      
      if (!this.isDeleting && this.currentChar <= line.length) {
        // Typing
        this.displayCode();
        this.currentChar++;
        setTimeout(() => this.typeCode(), this.typeSpeed);
      } else if (!this.isDeleting && this.currentChar > line.length) {
        // Line complete, move to next
        this.currentLine++;
        this.currentChar = 0;
        setTimeout(() => this.typeCode(), 100);
      }
    } else {
      // All lines typed, restart after pause
      setTimeout(() => this.restart(), this.pauseTime);
    }
  }
  
  displayCode() {
    if (!this.codeLines || !this.lineNumbers) return;
    
    let html = '';
    let lineNumbersHtml = '';
    
    for (let i = 0; i <= this.currentLine && i < this.code.length; i++) {
      const line = this.code[i];
      let displayLine = '';
      
      if (i === this.currentLine) {
        displayLine = line.substring(0, this.currentChar);
        if (this.currentChar < line.length) {
          displayLine += '<span class="cursor">|</span>';
        }
      } else {
        displayLine = line;
      }
      
      // Syntax highlighting
      displayLine = this.highlightSyntax(displayLine);
      
      html += `<div class="code-line">${displayLine}</div>`;
      lineNumbersHtml += `<div class="line-number">${i + 1}</div>`;
    }
    
    this.codeLines.innerHTML = html;
    this.lineNumbers.innerHTML = lineNumbersHtml;
    
    if (this.lineCount) {
      this.lineCount.textContent = this.currentLine + 1;
    }
  }
  
  highlightSyntax(line) {
    // Simple syntax highlighting
    line = line.replace(/\/\/(.*)/g, '<span class="comment">//$1</span>');
    line = line.replace(/\b(class|constructor|return|while|const|let|var|function|if|else)\b/g, '<span class="keyword">$1</span>');
    line = line.replace(/\b(this|new)\b/g, '<span class="keyword">$1</span>');
    line = line.replace(/'([^']*)'/g, '<span class="string">\'$1\'</span>');
    line = line.replace(/"([^"]*)"/g, '<span class="string">"$1"</span>');
    line = line.replace(/\b(\d+)\b/g, '<span class="number">$1</span>');
    line = line.replace(/\b(true|false|null|undefined|Infinity)\b/g, '<span class="boolean">$1</span>');
    
    return line;
  }
  
  restart() {
    this.currentLine = 0;
    this.currentChar = 0;
    this.isDeleting = false;
    this.typeCode();
  }
}

// Initialize code visualization when page loads
document.addEventListener('DOMContentLoaded', () => {
  new CodeVisualization();
});

// Also initialize immediately if DOM is already loaded
if (document.readyState !== 'loading') {
  new CodeVisualization();
}
</script>

<style>
#code-visualization {
  display: flex;
  justify-content: center;
  margin: 20px 0;
  padding: 20px;
}

.code-editor {
  background: #0d1117;
  border: 1px solid #30363d;
  border-radius: 8px;
  max-width: 700px;
  width: 100%;
  font-family: 'Monaco', 'Menlo', 'Ubuntu Mono', monospace;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
  overflow: hidden;
}

.editor-header {
  background: #21262d;
  padding: 12px 16px;
  display: flex;
  align-items: center;
  border-bottom: 1px solid #30363d;
}

.editor-buttons {
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

.file-name {
  color: #f0f6fc;
  font-size: 13px;
  font-weight: 500;
}

.code-content {
  display: flex;
  background: #0d1117;
  min-height: 400px;
  max-height: 500px;
  overflow-y: auto;
}

.line-numbers {
  background: #161b22;
  color: #656d76;
  padding: 16px 12px;
  font-size: 13px;
  line-height: 1.5;
  text-align: right;
  min-width: 40px;
  user-select: none;
  border-right: 1px solid #21262d;
}

.code-lines {
  flex: 1;
  padding: 16px;
  color: #f0f6fc;
  font-size: 13px;
  line-height: 1.5;
  white-space: pre;
}

.code-line {
  min-height: 19.5px;
}

.cursor {
  color: #00D9FF;
  font-weight: bold;
  animation: blink 1s infinite;
}

@keyframes blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}

/* Syntax highlighting */
.keyword { color: #ff7b72; }
.string { color: #a5d6ff; }
.comment { color: #7c3aed; font-style: italic; }
.number { color: #79c0ff; }
.boolean { color: #ffa657; }

.status-bar {
  background: #21262d;
  padding: 8px 16px;
  font-size: 12px;
  color: #8b949e;
  display: flex;
  justify-content: space-between;
  border-top: 1px solid #30363d;
}

/* Scrollbar styling */
.code-content::-webkit-scrollbar {
  width: 8px;
}

.code-content::-webkit-scrollbar-track {
  background: #161b22;
}

.code-content::-webkit-scrollbar-thumb {
  background: #656d76;
  border-radius: 4px;
}

.code-content::-webkit-scrollbar-thumb:hover {
  background: #768390;
}

/* Responsive design */
@media (max-width: 768px) {
  .code-editor {
    max-width: 100%;
    margin: 0 10px;
  }
  
  .code-lines, .line-numbers {
    font-size: 12px;
    padding: 12px;
  }
  
  .status-bar {
    flex-direction: column;
    gap: 4px;
  }
}
</style>
