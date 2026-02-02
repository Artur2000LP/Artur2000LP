# Hi, I'm Artur 👋 👨‍🦱🧑‍💻
<img src="https://github.com/Artur2000LP/Artur2000LP/assets/113075481/b2f5a018-7d0b-4ec1-aebe-7292a2ea66fb"  style=" display: felx;  flex: right">


## about me in code;
```JS
const Artur = {
  pronouns: "she" | "her",
  code: [Javascript, Typescript, PHP, HTML, CSS, Java, C++ ],
  tools: [React, Laravel, Angular, Node, nex.js ]
}
```
<svg width="800" height="600" viewBox="0 0 800 600" xmlns="http://www.w3.org/2000/svg">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Fira+Code&amp;display=swap');
    text { font-family: 'Fira Code', monospace; font-size: 14px; white-space: pre; }
    
    /* Colores para fondo transparente (ajustados para que resalten) */
    .k { fill: #c586c0; } /* keyword (púrpura) */
    .v { fill: #9cdcfe; } /* variable (azul claro) */
    .s { fill: #ce9178; } /* string (naranja/café) */
    .f { fill: #dcdcaa; } /* function (amarillo) */
    .o { fill: #d4d4d4; } /* operator (gris claro) */
    .c { fill: #6a9955; } /* comment (verde) */
    .r { fill: #4af626; font-weight: bold; } /* result (verde neón) */
  </style>

  <rect width="100%" height="35" rx="12" fill="#333" />
  <circle cx="20" cy="17" r="6" fill="#ff5f56" />
  <circle cx="40" cy="17" r="6" fill="#ffbd2e" />
  <circle cx="60" cy="17" r="6" fill="#27c93f" />

  <g id="codeDisplay" transform="translate(25, 75)"></g>
  <g id="consoleDisplay" transform="translate(25, 480)"></g>

  <rect id="cursor" x="25" y="55" width="8" height="18" fill="#4af626">
    <animate attributeName="opacity" values="0;1;0" dur="1s" repeatCount="indefinite" />
  </rect>

  <script type="text/javascript">
    <![CDATA[
    const code = [
      [{t: "const", c: "k"}, {t: " { from } = ", c: "o"}, {t: "require", c: "f"}, {t: "('rxjs');", c: "s"}],
      [{t: "const", c: "k"}, {t: " { map } = ", c: "o"}, {t: "require", c: "f"}, {t: "('rxjs/operators');", c: "s"}],
      [],
      [{t: "const", c: "k"}, {t: " users$ = ", c: "o"}, {t: "from", c: "f"}, {t: "([", c: "o"}],
      [{t: "  { user: ", c: "o"}, {t: "'Artur'", c: "s"}, {t: ", role: ", c: "o"}, {t: "'Admin'", c: "s"}, {t: " },", c: "o"}],
      [{t: "  { user: ", c: "o"}, {t: "'Usuario'", c: "s"}, {t: ", role: ", c: "o"}, {t: "'Visitante'", c: "s"}, {t: " }", c: "o"}],
      [{t: "]);", c: "o"}],
      [],
      [{t: "users$", c: "v"}, {t: ".", c: "o"}, {t: "pipe", c: "f"}, {t: "(", c: "o"}],
      [{t: "  ", c: "o"}, {t: "map", c: "f"}, {t: "(u => {", c: "o"}],
      [{t: "    ", c: "o"}, {t: "if", c: "k"}, {t: " (u.role === ", c: "o"}, {t: "'Admin'", c: "s"}, {t: ") {", c: "o"}],
      [{t: "      ", c: "o"}, {t: "return", c: "k"}, {t: " `¡Hola ${u.user}! Estás en modo edición.`;", c: "s"}],
      [{t: "    } ", c: "o"}, {t: "else", c: "k"}, {t: " {", c: "o"}],
      [{t: "      ", c: "o"}, {t: "return", c: "k"}, {t: " `Bienvenido a mi perfil profesional. Soy Artur...`;", c: "s"}],
      [{t: "    }", c: "o"}],
      [{t: "  })", c: "o"}],
      [{t: ").", c: "o"}, {t: "subscribe", c: "f"}, {t: "(msg => ", c: "o"}, {t: "console", c: "v"}, {t: ".", c: "o"}, {t: "log", c: "f"}, {t: "(msg));", c: "o"}]
    ];

    const output = [
      {t: "// --- RESULTADO EN CONSOLA ---", c: "c"},
      {t: "¡Hola Artur! Estás viendo tu perfil en modo edición.", c: "r"},
      {t: "Bienvenido a mi perfil profesional. Soy Artur, es un gusto tenerte aquí.", c: "r"}
    ];

    const cursor = document.getElementById('cursor');

    async function play() {
      const codeG = document.getElementById('codeDisplay');
      const consoleG = document.getElementById('consoleDisplay');
      
      for (let i = 0; i < code.length; i++) {
        const line = document.createElementNS("http://www.w3.org/2000/svg", "text");
        line.setAttribute("y", i * 22);
        codeG.appendChild(line);
        
        for (const part of code[i]) {
          const span = document.createElementNS("http://www.w3.org/2000/svg", "tspan");
          span.classList.add(part.c);
          line.appendChild(span);
          for (const char of part.t) {
            span.textContent += char;
            const box = line.getBBox();
            cursor.setAttribute("x", 25 + box.width + 2);
            cursor.setAttribute("y", 75 + (i * 22) - 15);
            await new Promise(r => setTimeout(r, 12));
          }
        }
      }

      await new Promise(r => setTimeout(r, 800));
      for (let i = 0; i < output.length; i++) {
        const line = document.createElementNS("http://www.w3.org/2000/svg", "text");
        line.setAttribute("y", i * 25);
        line.classList.add(output[i].c);
        consoleG.appendChild(line);
        for (const char of output[i].t) {
          line.textContent += char;
          const box = line.getBBox();
          cursor.setAttribute("x", 25 + box.width + 2);
          cursor.setAttribute("y", 480 + (i * 25) - 15);
          await new Promise(r => setTimeout(r, 20));
        }
      }
    }
    window.onload = play;
    ]]>
  </script>
</svg>
<!--h1 without bottom border-->
<div id="user-content-toc">
  <ul align="center">
    <summary><h2 style="display: inline-block">Technologies That I Know </h2></summary>
  </ul>
</div>
<!--tech stack icons-->
<p align="center">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=git,aws,cpp,css,discord,docker,postgres,prisma,pug,dynamodb,express,figma,firebase,redis,github,html,java,js,linux,md,materialui,nginx,mongodb,mysql,nextjs,nodejs,postman,py,react,redux,tailwind,ts,vscode,kubernetes&perline=14" />
  </a>
</p>



## you can find me 🌎:
   - [blog](https://github.com/Artur2000LP)
   - [facebook](https://www.facebook.com/ruhiartur.ltnaprras?mibextid=ZbWKwL)


<!--
**Artur2000LP/Artur2000LP** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
