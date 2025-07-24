
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Malla Interactiva Arquitectura UChile</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f4f4f4; padding: 20px; }
    h1 { text-align: center; color: #333; }
    .semestre { margin-bottom: 20px; background: #fff; padding: 15px; border-radius: 10px; box-shadow: 0 2px 4px rgba(0,0,0,0.1); }
    .semestre h2 { color: #555; }
    .ramo { margin: 5px 0; padding: 5px; border-left: 5px solid #ccc; background: #fafafa; }
    .ramo.taller { border-color: orange; }
    .ramo.matematica { border-color: #3498db; }
    .ramo.historia { border-color: #2ecc71; }
    .ramo.urbanismo { border-color: #9b59b6; }
    .ramo.electivo { border-color: #95a5a6; }
    .ramo label { margin-left: 8px; }
    .ramo input[type='number'] { width: 60px; margin-left: 10px; }
    .avance { font-weight: bold; font-size: 1.2em; margin-top: 30px; text-align: center; }
  </style>
</head>
<body>
  <h1>Malla Interactiva Yazmín – Arquitectura UChile</h1>
  <div id="contenido"></div>
  <div class="avance" id="avance">Progreso: 0 créditos (0%)</div>

  <script>
    const malla = [
      [
        {name:'Taller 1', cred:18, area:'taller', prere:[]},
        {name:'Geometría', cred:3, area:'matematica', prere:[]},
        {name:'Matemáticas', cred:3, area:'matematica', prere:[]},
        {name:'Historia, Cultura y Habitar', cred:3, area:'historia', prere:[]},
        {name:'Inglés 1', cred:3, area:'electivo', prere:[]}
      ],
      [
        {name:'Taller 2', cred:18, area:'taller', prere:['Taller 1']},
        {name:'Investigación del Entorno', cred:3, area:'electivo', prere:['Taller 1']},
        {name:'Física', cred:3, area:'matematica', prere:['Matemáticas']},
        {name:'Fundamentos de la Arquitectura', cred:3, area:'electivo', prere:['Historia, Cultura y Habitar']},
        {name:'Inglés 2', cred:3, area:'electivo', prere:['Inglés 1']}
      ],
      [
        {name:'Taller 3', cred:9, area:'taller', prere:['Taller 2']},
        {name:'Sostenibilidad Urbana', cred:6, area:'urbanismo', prere:['Investigación del Entorno']},
        {name:'Cultura de la arquitectura clásica', cred:3, area:'historia', prere:['Historia, Cultura y Habitar']},
        {name:'Morfol. y materialización', cred:6, area:'electivo', prere:['Fundamentos de la Arquitectura']},
        {name:'Principios de habitabilidad', cred:3, area:'electivo', prere:['Morfol. y materialización']},
        {name:'Inglés 3', cred:3, area:'electivo', prere:['Inglés 2']}
      ],
      [
        {name:'Taller 4', cred:9, area:'taller', prere:['Taller 3']},
        {name:'Métodos y prácticas del urbanismo', cred:6, area:'urbanismo', prere:['Sostenibilidad Urbana']},
        {name:'Problemas arquitectura moderna', cred:3, area:'historia', prere:['Cultura de la arquitectura clásica']},
        {name:'Diseño y materialización', cred:6, area:'electivo', prere:['Morfol. y materialización']},
        {name:'Transversal FAU', cred:3, area:'electivo', prere:[]},
        {name:'Inglés 4', cred:3, area:'electivo', prere:['Inglés 3']}
      ]
    ];
    let aprobados = new Set();
    let notas = {};
    function init() {
      const cont = document.getElementById("contenido");
      malla.forEach((sem, i) => {
        const div = document.createElement("div");
        div.className = "semestre";
        div.innerHTML = `<h2>Semestre ${i + 1}</h2>`;
        sem.forEach(r => {
          const ramoDiv = document.createElement("div");
          ramoDiv.className = `ramo ${r.area}`;
          ramoDiv.innerHTML = `<input type="checkbox" onchange="toggleRamo('${r.name}', this, ${i})"> 
            <label>${r.name} (${r.cred} cr)</label>
            <input type="number" placeholder="Nota" step="0.1" min="1.0" max="7.0" disabled onchange="calcularPromSem(${i})">`;
          div.appendChild(ramoDiv);
        });
        const prom = document.createElement("div");
        prom.id = `prom${i}`;
        prom.innerHTML = "Promedio: -";
        div.appendChild(prom);
        cont.appendChild(div);
      });
    }
    function toggleRamo(nombre, checkbox, semIdx) {
      const ramoDiv = checkbox.parentElement;
      const notaInput = ramoDiv.querySelector("input[type='number']");
      if (checkbox.checked) {
        aprobados.add(nombre);
        notaInput.disabled = false;
        notaInput.focus();
      } else {
        aprobados.delete(nombre);
        notaInput.disabled = true;
        notaInput.value = "";
      }
      liberarSubsecuentes();
      calcularPromSem(semIdx);
      calcularAvance();
    }
    function liberarSubsecuentes() {
      document.querySelectorAll(".ramo").forEach(div => {
        const nombre = div.querySelector("label").innerText.split(" (")[0];
        const checkbox = div.querySelector("input[type='checkbox']");
        const ramo = malla.flat().find(r => r.name === nombre);
        const bloqueado = ramo.prere.some(p => !aprobados.has(p));
        checkbox.disabled = bloqueado;
        div.style.opacity = bloqueado ? 0.4 : 1;
      });
    }
    function calcularPromSem(idx) {
      const ramos = document.querySelectorAll(`.semestre:nth-child(${idx+1}) .ramo input[type='number']`);
      let total = 0, count = 0;
      ramos.forEach(n => {
        if (!n.disabled && n.value) {
          total += parseFloat(n.value);
          count++;
        }
      });
      const prom = count ? (total / count).toFixed(2) : '-';
      document.getElementById(`prom${idx}`).innerText = `Promedio: ${prom}`;
    }
    function calcularAvance() {
      let total = 0, aprob = 0;
      malla.forEach(sem => sem.forEach(r => total += r.cred));
      malla.forEach(sem => sem.forEach(r => { if (aprobados.has(r.name)) aprob += r.cred; }));
      document.getElementById("avance").innerText = `Progreso: ${aprob} créditos (${((aprob/total)*100).toFixed(1)}%)`;
    }
    init();
  </script>
</body>
</html>
