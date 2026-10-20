<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Firdaus Hasrin - UTM Software Engineering GitHub Profile Generator</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            utm: {
              maroon: '#800000',
              gold: '#D4AF37',
              dark: '#500000',
              light: '#A00000'
            }
          },
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            mono: ['Fira Code', 'monospace']
          }
        }
      }
    }
  </script>
  <style>
    /* Custom Scrollbars */
    ::-webkit-scrollbar {
      width: 8px;
      height: 8px;
    }
    ::-webkit-scrollbar-track {
      background: #0f172a;
    }
    ::-webkit-scrollbar-thumb {
      background: #334155;
      border-radius: 4px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: #475569;
    }

    /* Glow Effects */
    .glow-maroon {
      box-shadow: 0 0 25px rgba(128, 0, 0, 0.45);
    }
    .glow-gold {
      box-shadow: 0 0 20px rgba(212, 175, 55, 0.3);
    }
    .text-glow {
      text-shadow: 0 0 10px rgba(212, 175, 55, 0.5);
    }

    /* Animated Gradients */
    @keyframes gradient-x {
      0%, 100% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
    }
    .animate-gradient {
      background-size: 200% 200%;
      animation: gradient-x 6s ease infinite;
    }

    /* Typing Animation Simulation */
    @keyframes typing {
      from { width: 0 }
      to { width: 100% }
    }
    @keyframes blink {
      50% { border-color: transparent }
    }
    .typewriter {
      overflow: hidden;
      white-space: nowrap;
      border-right: 3px solid #D4AF37;
      animation: typing 3.5s steps(40, end), blink .75s step-end infinite;
    }

    /* Markdown Styling inside Preview */
    .markdown-body {
      color: #e2e8f0;
      font-family: 'Inter', sans-serif;
    }
    .markdown-body h1, .markdown-body h2, .markdown-body h3 {
      border-bottom: 1px solid #334155;
      padding-bottom: 0.3em;
      margin-top: 1.5em;
      margin-bottom: 0.8em;
      font-weight: 700;
    }
    .markdown-body h1 { font-size: 2em; color: #f8fafc; }
    .markdown-body h2 { font-size: 1.5em; color: #f1f5f9; }
    .markdown-body h3 { font-size: 1.25em; color: #e2e8f0; }
    .markdown-body p { margin-bottom: 1em; line-height: 1.7; }
    .markdown-body img { max-width: 100%; display: inline-block; }
    .markdown-body code {
      background-color: #1e293b;
      padding: 0.2em 0.4em;
      border-radius: 4px;
      font-family: 'Fira Code', monospace;
      font-size: 0.9em;
    }
    .markdown-body blockquote {
      border-left: 4px solid #800000;
      padding-left: 1rem;
      color: #94a3b8;
      font-style: italic;
      background: rgba(128, 0, 0, 0.05);
      padding-top: 0.5rem;
      padding-bottom: 0.5rem;
      border-radius: 0 8px 8px 0;
    }
  </style>
</head>
<body class="bg-slate-950 text-slate-100 font-sans min-h-screen flex flex-col antialiased selection:bg-utm-maroon selection:text-white">

  <!-- Header / Navigation Bar -->
  <header class="border-b border-slate-800 bg-slate-900/80 backdrop-blur-md sticky top-0 z-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
      <div class="flex items-center space-x-3">
        <!-- UTM Logo SVG -->
        <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-utm-maroon to-black p-1.5 flex items-center justify-center shadow-lg border border-utm-gold/40">
          <svg viewBox="0 0 100 100" class="w-full h-full fill-utm-gold">
            <path d="M10 20 L50 5 L90 20 L90 80 L50 95 L10 80 Z" fill="none" stroke="#D4AF37" stroke-width="6"/>
            <text x="50" y="58" font-family="sans-serif" font-weight="900" font-size="32" text-anchor="middle" fill="#D4AF37">UTM</text>
          </svg>
        </div>
        <div>
          <h1 class="text-lg font-bold bg-gradient-to-r from-white via-slate-200 to-utm-gold bg-clip-text text-transparent">
            Firdaus Hasrin README Studio
          </h1>
          <p class="text-xs text-slate-400">Software Engineering @ UTM Skudai, Johor Bahru</p>
        </div>
      </div>

      <!-- Action Buttons -->
      <div class="flex items-center space-x-3">
        <button id="copyMdBtn" onclick="copyMarkdown()" class="flex items-center space-x-2 bg-gradient-to-r from-utm-maroon to-red-900 hover:from-red-800 hover:to-utm-maroon text-white font-medium px-4 py-2 rounded-lg text-sm transition-all duration-200 shadow-md hover:shadow-utm-maroon/50 border border-utm-gold/30">
          <i class="fa-solid fa-copy"></i>
          <span id="copyBtnText">Copy Markdown</span>
        </button>
        <button id="toggleTabBtn" onclick="toggleMobileView()" class="md:hidden bg-slate-800 hover:bg-slate-700 text-slate-200 p-2 rounded-lg text-sm border border-slate-700">
          <i class="fa-solid fa-arrows-rotate"></i>
        </button>
      </div>
    </div>
  </header>

  <!-- Main Grid Layout -->
  <main class="flex-1 max-w-7xl w-full mx-auto p-4 sm:p-6 grid grid-cols-1 md:grid-cols-12 gap-6">

    <!-- LEFT COLUMN: Controls & Settings Panel (5 Cols) -->
    <section class="md:col-span-5 flex flex-col space-y-6 max-h-[calc(100vh-6rem)] overflow-y-auto pr-1">
      
      <!-- Profile Information Card -->
      <div class="bg-slate-900/90 rounded-xl border border-slate-800 p-5 shadow-xl backdrop-blur">
        <div class="flex items-center space-x-2 text-utm-gold font-semibold text-sm mb-4 uppercase tracking-wider">
          <i class="fa-solid fa-user-gear"></i>
          <span>Personal & Academic Details</span>
        </div>
        
        <div class="space-y-4">
          <div>
            <label class="block text-xs font-medium text-slate-400 mb-1">Full Name</label>
            <input type="text" id="inputName" value="Firdaus Hasrin" oninput="updateProfile()" class="w-full bg-slate-950 border border-slate-800 rounded-lg px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-utm-gold transition">
          </div>

          <div>
            <label class="block text-xs font-medium text-slate-400 mb-1">Tagline / Subtitle</label>
            <input type="text" id="inputTagline" value="🚀 Beginner Software Engineering Student @ UTM JB | Aspiring Full-Stack Developer" oninput="updateProfile()" class="w-full bg-slate-950 border border-slate-800 rounded-lg px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-utm-gold transition">
          </div>

          <div class="grid grid-cols-2 gap-3">
            <div>
              <label class="block text-xs font-medium text-slate-400 mb-1">Campus</label>
              <input type="text" id="inputCampus" value="UTM Skudai, Johor Bahru" oninput="updateProfile()" class="w-full bg-slate-950 border border-slate-800 rounded-lg px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-utm-gold transition">
            </div>
            <div>
              <label class="block text-xs font-medium text-slate-400 mb-1">Degree Program</label>
              <input type="text" id="inputDegree" value="Bachelor of Software Engineering (Hons)" oninput="updateProfile()" class="w-full bg-slate-950 border border-slate-800 rounded-lg px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-utm-gold transition">
            </div>
          </div>

          <div>
            <label class="block text-xs font-medium text-slate-400 mb-1">GitHub Username</label>
            <input type="text" id="inputGithub" value="firdaushasrin" oninput="updateProfile()" class="w-full bg-slate-950 border border-slate-800 rounded-lg px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-utm-gold transition">
          </div>
        </div>
      </div>

      <!-- Features & Sections Toggle -->
      <div class="bg-slate-900/90 rounded-xl border border-slate-800 p-5 shadow-xl backdrop-blur">
        <div class="flex items-center space-x-2 text-utm-gold font-semibold text-sm mb-4 uppercase tracking-wider">
          <i class="fa-solid fa-sliders"></i>
          <span>Enable Profile Components</span>
        </div>

        <div class="space-y-3">
          <label class="flex items-center justify-between p-2 rounded-lg bg-slate-950 border border-slate-800/80 cursor-pointer hover:border-slate-700 transition">
            <span class="text-sm font-medium text-slate-300"><i class="fa-solid fa-heading text-red-400 mr-2"></i> Animated Banner Header</span>
            <input type="checkbox" id="chkBanner" checked onchange="updateProfile()" class="w-4 h-4 rounded text-utm-maroon focus:ring-utm-gold bg-slate-900 border-slate-700">
          </label>

          <label class="flex items-center justify-between p-2 rounded-lg bg-slate-950 border border-slate-800/80 cursor-pointer hover:border-slate-700 transition">
            <span class="text-sm font-medium text-slate-300"><i class="fa-solid fa-graduation-cap text-amber-400 mr-2"></i> UTM Branding & Logo</span>
            <input type="checkbox" id="chkUtm" checked onchange="updateProfile()" class="w-4 h-4 rounded text-utm-maroon focus:ring-utm-gold bg-slate-900 border-slate-700">
          </label>

          <label class="flex items-center justify-between p-2 rounded-lg bg-slate-950 border border-slate-800/80 cursor-pointer hover:border-slate-700 transition">
            <span class="text-sm font-medium text-slate-300"><i class="fa-solid fa-keyboard text-emerald-400 mr-2"></i> Animated Typing Greeting</span>
            <input type="checkbox" id="chkTyping" checked onchange="updateProfile()" class="w-4 h-4 rounded text-utm-maroon focus:ring-utm-gold bg-slate-900 border-slate-700">
          </label>

          <label class="flex items-center justify-between p-2 rounded-lg bg-slate-950 border border-slate-800/80 cursor-pointer hover:border-slate-700 transition">
            <span class="text-sm font-medium text-slate-300"><i class="fa-solid fa-chart-line text-blue-400 mr-2"></i> GitHub Live Stats & Streak</span>
            <input type="checkbox" id="chkStats" checked onchange="updateProfile()" class="w-4 h-4 rounded text-utm-maroon focus:ring-utm-gold bg-slate-900 border-slate-700">
          </label>

          <label class="flex items-center justify-between p-2 rounded-lg bg-slate-950 border border-slate-800/80 cursor-pointer hover:border-slate-700 transition">
            <span class="text-sm font-medium text-slate-300"><i class="fa-solid fa-play text-purple-400 mr-2"></i> Video Showcase / Coding Animation</span>
            <input type="checkbox" id="chkVideo" checked onchange="updateProfile()" class="w-4 h-4 rounded text-utm-maroon focus:ring-utm-gold bg-slate-900 border-slate-700">
          </label>

          <label class="flex items-center justify-between p-2 rounded-lg bg-slate-950 border border-slate-800/80 cursor-pointer hover:border-slate-700 transition">
            <span class="text-sm font-medium text-slate-300"><i class="fa-solid fa-seedling text-green-400 mr-2"></i> Beginner Journey Projects</span>
            <input type="checkbox" id="chkProjects" checked onchange="updateProfile()" class="w-4 h-4 rounded text-utm-maroon focus:ring-utm-gold bg-slate-900 border-slate-700">
          </label>
        </div>
      </div>

      <!-- Social & Contact Links -->
      <div class="bg-slate-900/90 rounded-xl border border-slate-800 p-5 shadow-xl backdrop-blur">
        <div class="flex items-center space-x-2 text-utm-gold font-semibold text-sm mb-4 uppercase tracking-wider">
          <i class="fa-solid fa-link"></i>
          <span>Social Media Links</span>
        </div>

        <div class="space-y-3">
          <div>
            <label class="block text-xs font-medium text-slate-400 mb-1"><i class="fa-solid fa-envelope mr-1 text-red-400"></i> Student Email</label>
            <input type="email" id="inputEmail" value="firdaus@utm.my" oninput="updateProfile()" class="w-full bg-slate-950 border border-slate-800 rounded-lg px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-utm-gold">
          </div>
          <div>
            <label class="block text-xs font-medium text-slate-400 mb-1"><i class="fa-brands fa-linkedin mr-1 text-blue-400"></i> LinkedIn Username</label>
            <input type="text" id="inputLinkedin" value="firdaushasrin" oninput="updateProfile()" class="w-full bg-slate-950 border border-slate-800 rounded-lg px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-utm-gold">
          </div>
          <div>
            <label class="block text-xs font-medium text-slate-400 mb-1"><i class="fa-brands fa-instagram mr-1 text-pink-400"></i> Instagram Handle</label>
            <input type="text" id="inputInstagram" value="firdaushasrin" oninput="updateProfile()" class="w-full bg-slate-950 border border-slate-800 rounded-lg px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-utm-gold">
          </div>
        </div>
      </div>

    </section>

    <!-- RIGHT COLUMN: Interactive Live Preview & Code View (7 Cols) -->
    <section class="md:col-span-7 flex flex-col h-full bg-slate-900 rounded-2xl border border-slate-800 shadow-2xl overflow-hidden min-h-[600px]">
      
      <!-- Preview Header Tabs -->
      <div class="bg-slate-950/80 border-b border-slate-800 p-3 flex items-center justify-between">
        <div class="flex items-center space-x-2">
          <button id="tabPreviewBtn" onclick="switchTab('preview')" class="px-4 py-1.5 rounded-lg text-xs font-semibold bg-utm-maroon text-white border border-utm-gold/40 shadow">
            <i class="fa-solid fa-eye mr-1.5"></i> Visual Preview
          </button>
          <button id="tabCodeBtn" onclick="switchTab('code')" class="px-4 py-1.5 rounded-lg text-xs font-semibold bg-slate-800 text-slate-400 hover:text-white transition">
            <i class="fa-solid fa-code mr-1.5"></i> Raw Markdown
          </button>
        </div>

        <div class="flex items-center space-x-2 text-xs text-slate-400">
          <span class="inline-block w-2.5 h-2.5 rounded-full bg-emerald-500 animate-pulse"></span>
          <span>Live Rendering</span>
        </div>
      </div>

      <!-- Preview Panel Content -->
      <div id="previewTab" class="p-6 overflow-y-auto max-h-[calc(100vh-12rem)] bg-slate-950/50 flex-1">
        <div id="markdownOutput" class="markdown-body max-w-none">
          <!-- Rendered output will inject here -->
        </div>
      </div>

      <!-- Raw Markdown Code Panel Content -->
      <div id="codeTab" class="hidden p-4 overflow-y-auto max-h-[calc(100vh-12rem)] bg-slate-950 flex-1 font-mono text-xs text-slate-300">
        <pre><code id="rawCodeOutput" class="whitespace-pre-wrap break-words"></code></pre>
      </div>

    </section>

  </main>

  <!-- Notification Toast -->
  <div id="toast" class="fixed bottom-6 right-6 bg-slate-900 border border-utm-gold text-white px-5 py-3 rounded-xl shadow-2xl transform translate-y-24 opacity-0 transition-all duration-300 flex items-center space-x-3 z-50">
    <div class="w-8 h-8 rounded-full bg-utm-maroon flex items-center justify-center text-utm-gold">
      <i class="fa-solid fa-check"></i>
    </div>
    <div>
      <h4 class="text-sm font-bold text-slate-100">Copied to Clipboard!</h4>
      <p class="text-xs text-slate-400">Paste it directly into your GitHub README.md</p>
    </div>
  </div>

  <!-- JavaScript Logic -->
  <script>
    // State variables
    let currentTab = 'preview';

    function generateMarkdown() {
      const name = document.getElementById('inputName').value || 'Firdaus Hasrin';
      const tagline = document.getElementById('inputTagline').value || 'Software Engineering Student @ UTM JB';
      const campus = document.getElementById('inputCampus').value || 'UTM Skudai, Johor Bahru';
      const degree = document.getElementById('inputDegree').value || 'Bachelor of Software Engineering (Hons)';
      const github = document.getElementById('inputGithub').value || 'firdaushasrin';
      const email = document.getElementById('inputEmail').value || 'firdaus@utm.my';
      const linkedin = document.getElementById('inputLinkedin').value || 'firdaushasrin';
      const instagram = document.getElementById('inputInstagram').value || 'firdaushasrin';

      const showBanner = document.getElementById('chkBanner').checked;
      const showUtm = document.getElementById('chkUtm').checked;
      const showTyping = document.getElementById('chkTyping').checked;
      const showStats = document.getElementById('chkStats').checked;
      const showVideo = document.getElementById('chkVideo').checked;
      const showProjects = document.getElementById('chkProjects').checked;

      let md = '';

      // Banner Header
      if (showBanner) {
        md += `<div align="center">\n`;
        md += `  <img src="https://capsule-render.vercel.app/api?type=waving&color=800000&height=220&section=header&text=${encodeURIComponent(name)}&fontSize=42&fontColor=D4AF37&animation=fadeIn&stroke=D4AF37&strokeWidth=1" width="100%" alt="Header Banner"/>\n`;
        md += `</div>\n\n`;
      }

      // UTM Header & Typing Greeting
      md += `<div align="center">\n`;
      if (showUtm) {
        md += `  <img src="https://upload.wikimedia.org/wikipedia/commons/8/81/UTM-LOGO.png" width="120" alt="UTM Logo" style="margin-bottom: 10px;"/>\n`;
        md += `  <h3>🏛️ <b>UNIVERSITI TEKNOLOGI MALAYSIA (UTM JB)</b></h3>\n`;
        md += `  <p><b>${degree}</b></p>\n\n`;
      }

      if (showTyping) {
        md += `  <a href="https://readme-typing-svg.demolab.com"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=D4AF37&center=true&vCenter=true&width=600&lines=Hi+there!+I'm+${encodeURIComponent(name)}+%F0%9F%90%A7;Software+Engineering+Student+@+UTM+JB;Beginner+Developer+%7C+Learning+C%2B%2B%2C+Web+%26+Java;Building+a+strong+coding+foundation+step-by-step!" alt="Typing SVG" /></a>\n\n`;
      }

      // Badges Row
      md += `  <p align="center">\n`;
      md += `    <a href="https://utm.my"><img src="https://img.shields.io/badge/Campus-UTM%20Johor%20Bahru-800000?style=for-the-badge&logo=education&logoColor=D4AF37" alt="UTM JB"/></a>\n`;
      md += `    <a href="https://github.com/${github}"><img src="https://img.shields.io/badge/Level-Beginner_Developer-000000?style=for-the-badge&logo=github&logoColor=white" alt="Level"/></a>\n`;
      md += `    <a href="mailto:${email}"><img src="https://img.shields.io/badge/Status-Learning_%26_Growing-2ea44f?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Status"/></a>\n`;
      md += `  </p>\n`;
      md += `</div>\n\n`;

      md += `<hr/>\n\n`;

      // About Me Section
      md += `## 🚀 About Me\n\n`;
      md += `Hello! 👋 I am **${name}**, a passionate **Software Engineering** student based at **${campus}**.\n\n`;
      md += `- 🎓 **Degree:** ${degree}\n`;
      md += `- 🏫 **University:** Universiti Teknologi Malaysia (UTM), Skudai, Johor\n`;
      md += `- 🌱 **Current Focus:** Master fundamental algorithms, Object-Oriented Programming (C++/Java), and Modern Web Technologies.\n`;
      md += `- 💡 **Philosophy:** *"Code is like humor. When you have to explain it, it’s bad."* Every line of code is a step towards growth!\n`;
      md += `- 🎯 **Goal:** Transition from a beginner enthusiast to a full-stack software engineer.\n\n`;

      // Tech Stack Section
      md += `## 🛠️ What I'm Learning & Using\n\n`;
      md += `<p align="left">\n`;
      md += `  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++" />\n`;
      md += `  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5" />\n`;
      md += `  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3" />\n`;
      md += `  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JS" />\n`;
      md += `  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git" />\n`;
      md += `  <img src="https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white" alt="VS Code" />\n`;
      md += `</p>\n\n`;

      // Beginner Projects & Journey
      if (showProjects) {
        md += `## 📌 Beginner Journey & Academic Assignments\n\n`;
        md += `Here are some of the lab exercises and initial projects I am working on as part of my UTM curriculum:\n\n`;
        md += `| Project / Lab | Language | Description | Status |\n`;
        md += `| :--- | :--- | :--- | :--- |\n`;
        md += `| 📚 **UTM SECJ1013 Programming Technique** | C++ | Data structures, pointers, and object-oriented concepts | 🟡 In Progress |\n`;
        md += `| 🌐 **Personal Web Portfolio** | HTML/CSS/JS | First interactive single-page portfolio website | 🟢 Completed |\n`;
        md += `| 🧮 **Mini Calculator App** | C++ / JS | Logic practice exercise with simple GUI/CLI | 🟢 Completed |\n`;
        md += `| 📂 **Data Structures Practice** | C++ | Implementations of Linked Lists, Stacks, and Queues | 🟡 Learning |\n\n`;
      }

      // Video / Animation Feature
      if (showVideo) {
        md += `## 💻 Coding Workspace & Aesthetics\n\n`;
        md += `<div align="center">\n`;
        md += `  <img src="https://cdn.dribbble.com/users/1162077/screenshots/3848914/programmer.gif" width="80%" style="border-radius:10px;" alt="Coding Animation GIF" />\n`;
        md += `  <p><i>"Debugging is like being the detective in a crime movie where you are also the murderer."</i></p>\n`;
        md += `</div>\n\n`;
      }

      // GitHub Stats Cards
      if (showStats) {
        md += `## 📊 GitHub Analytics & Streak\n\n`;
        md += `<div align="center">\n`;
        md += `  <img height="165" src="https://github-readme-stats.vercel.app/api?username=${github}&show_icons=true&theme=maroon_light&hide_border=true&title_color=D4AF37&icon_color=800000" alt="Firdaus Stats" />\n`;
        md += `  <img height="165" src="https://github-readme-streak-stats.herokuapp.com/?user=${github}&theme=maroon_light&hide_border=true&background=0D1117&ring=D4AF37&fire=800000" alt="Firdaus Streak" />\n`;
        md += `</div>\n\n`;
      }

      // Contact & Social Media Footer
      md += `## 📫 Connect With Me\n\n`;
      md += `<p align="left">\n`;
      if (email) md += `  <a href="mailto:${email}"><img src="https://img.shields.io/badge/Email-firdaus--hasrin-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>\n`;
      if (linkedin) md += `  <a href="https://linkedin.in/${linkedin}"><img src="https://img.shields.io/badge/LinkedIn-Firdaus_Hasrin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>\n`;
      if (instagram) md += `  <a href="https://instagram.com/${instagram}"><img src="https://img.shields.io/badge/Instagram-@firdaushasrin-E4405F?style=for-the-badge&logo=instagram&logoColor=white" /></a>\n`;
      md += `</p>\n\n`;

      // Footer Wave
      md += `<div align="center">\n`;
      md += `  <img src="https://capsule-render.vercel.app/api?type=waving&color=800000&height=100&section=footer" width="100%"/>\n`;
      md += `</div>\n`;

      return md;
    }

    function updateProfile() {
      const markdownText = generateMarkdown();
      
      // Update HTML live preview
      document.getElementById('markdownOutput').innerHTML = marked.parse(markdownText);
      
      // Update Raw Markdown Code tab
      document.getElementById('rawCodeOutput').textContent = markdownText;
    }

    function switchTab(tab) {
      currentTab = tab;
      const previewEl = document.getElementById('previewTab');
      const codeEl = document.getElementById('codeTab');
      const prevBtn = document.getElementById('tabPreviewBtn');
      const codeBtn = document.getElementById('tabCodeBtn');

      if (tab === 'preview') {
        previewEl.classList.remove('hidden');
        codeEl.classList.add('hidden');

        prevBtn.className = "px-4 py-1.5 rounded-lg text-xs font-semibold bg-utm-maroon text-white border border-utm-gold/40 shadow";
        codeBtn.className = "px-4 py-1.5 rounded-lg text-xs font-semibold bg-slate-800 text-slate-400 hover:text-white transition";
      } else {
        previewEl.classList.add('hidden');
        codeEl.classList.remove('hidden');

        codeBtn.className = "px-4 py-1.5 rounded-lg text-xs font-semibold bg-utm-maroon text-white border border-utm-gold/40 shadow";
        prevBtn.className = "px-4 py-1.5 rounded-lg text-xs font-semibold bg-slate-800 text-slate-400 hover:text-white transition";
      }
    }

    function toggleMobileView() {
      if (currentTab === 'preview') {
        switchTab('code');
      } else {
        switchTab('preview');
      }
    }

    function copyMarkdown() {
      const markdownText = generateMarkdown();
      
      // Copy logic with execCommand fallback for iFrame support
      const dummyTextArea = document.createElement("textarea");
      dummyTextArea.value = markdownText;
      document.body.appendChild(dummyTextArea);
      dummyTextArea.select();
      document.execCommand('copy');
      document.body.removeChild(dummyTextArea);

      // Show toast notification
      const toast = document.getElementById('toast');
      toast.classList.remove('translate-y-24', 'opacity-0');
      toast.classList.add('translate-y-0', 'opacity-100');

      const btnText = document.getElementById('copyBtnText');
      btnText.innerText = "Copied!";

      setTimeout(() => {
        toast.classList.remove('translate-y-0', 'opacity-100');
        toast.classList.add('translate-y-24', 'opacity-0');
        btnText.innerText = "Copy Markdown";
      }, 3000);
    }

    // Initialize application on load
    window.onload = function() {
      updateProfile();
    };
  </script>
</body>
</html>
