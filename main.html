<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Planner de Gestão Semanal - Dashboard</title>
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    padding: 0;
    background: #1f2937;
    color: #f8fafc;
  }
  h1 {
    text-align: center;
    padding: 20px;
    color: #f8fafc;
    background: #111827;
    margin: 0;
    font-size: 1.8rem;
    box-shadow: 0 2px 4px rgba(0,0,0,0.5);
  }
  h3 {
    text-align: center;
    margin: 0;
    padding: 10px;
    color: #cbd5e1;
  }
  .planner {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
    gap: 20px;
    padding: 20px;
  }
  .day-card {
    background: #111827;
    border-radius: 12px;
    box-shadow: 0 6px 18px rgba(0,0,0,0.6);
    display: flex;
    flex-direction: column;
    transition: transform 0.2s;
    max-height: 700px;
    overflow-y: auto;
  }
  .day-card:hover { transform: translateY(-4px); }
  .day-header {
    background: #2563eb;
    color: #f8fafc;
    padding: 16px;
    font-weight: bold;
    text-align: center;
    font-size: 1.2rem;
    border-top-left-radius: 12px;
    border-top-right-radius: 12px;
    position: sticky;
    top: 0;
    z-index: 10;
  }
  .task-list {
    list-style: none;
    margin: 0;
    padding: 12px;
    flex-grow: 1;
  }
  .task-item {
    background: #1e293b;
    border-radius: 10px;
    padding: 12px;
    margin-bottom: 10px;
    cursor: grab;
    display: flex;
    flex-direction: column;
    transition: background 0.2s, transform 0.2s;
    word-break: break-word;
  }
  .task-item:hover { background: #374151; transform: translateY(-2px); }
  .task-main {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 5px;
    flex-wrap: wrap;
  }
  .task-text {
    font-weight: 600;
    flex: 1 1 auto;
    color: #f8fafc;
    word-break: break-word;
  }
  .task-details {
    font-size: 0.85rem;
    color: #cbd5e1;
    margin-top: 6px;
    word-break: break-word;
  }
  .task-actions button {
    border: none;
    border-radius: 6px;
    padding: 5px 8px;
    margin: 2px;
    cursor: pointer;
    font-size: 0.8rem;
    transition: 0.2s;
  }
  .btn-edit { background: #facc15; color: #1f2937; }
  .btn-edit:hover { transform: scale(1.1); }
  .btn-delete { background: #ef4444; color: #f8fafc; }
  .btn-delete:hover { transform: scale(1.1); }
  .btn-copy { background: #10b981; color: #f8fafc; }
  .btn-copy:hover { transform: scale(1.1); }
  .add-task {
    padding: 12px;
    border-top: 1px solid #374151;
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  .add-task input, .add-task textarea {
    padding: 10px;
    border-radius: 8px;
    border: 1px solid #374151;
    background: #1f2937;
    color: #f8fafc;
    width: 100%;
    box-sizing: border-box;
    font-size: 0.95rem;
  }
  .add-task button {
    background: #3b82f6;
    color: #f8fafc;
    border: none;
    border-radius: 8px;
    padding: 10px;
    cursor: pointer;
    font-weight: bold;
    transition: 0.2s;
  }
  .add-task button:hover { background: #2563eb; }

  /* Classe para atividade concluída */
  .completed {
    text-decoration: line-through;
    color: #9ca3af;
  }
</style>
</head>
<body>
<h1>📊 Planner Rotina Semanal</h1>
<h3>📊 Supervisão NOC</h3>
<div class="planner" id="planner"></div>
<script>
const diasSemana = ['Segunda-feira','Terça-feira','Quarta-feira','Quinta-feira','Sexta-feira'];

function carregarPlanner() {
  const plannerEl = document.getElementById('planner');
  plannerEl.innerHTML = '';

  diasSemana.forEach(dia => {
    const card = document.createElement('div');
    card.className = 'day-card';

    const header = document.createElement('div');
    header.className = 'day-header';
    header.textContent = dia;
    card.appendChild(header);

    const lista = document.createElement('ul');
    lista.className = 'task-list';
    lista.id = `lista-${dia}`;

    const tarefas = JSON.parse(localStorage.getItem(dia)) || [];
    tarefas.forEach((tarefa, index) => renderTarefa(lista, dia, tarefa, index));
    card.appendChild(lista);

    const addTask = document.createElement('div');
    addTask.className = 'add-task';
    addTask.innerHTML = `
      <input type="time" id="start-${dia}" placeholder="Início" required>
      <input type="time" id="end-${dia}" placeholder="Fim" required>
      <input type="text" id="desc-${dia}" placeholder="Descrição da atividade" required>
      <textarea id="details-${dia}" placeholder="Detalhes (opcional)"></textarea>
      <button onclick="adicionarTarefa('${dia}')">➕ Adicionar</button>
    `;
    card.appendChild(addTask);

    plannerEl.appendChild(card);
  });

  adicionarDragAndDrop();
}

function renderTarefa(lista, dia, tarefa, index) {
  const li = document.createElement('li');
  li.className = 'task-item';
  li.draggable = true;

  const main = document.createElement('div');
  main.className = 'task-main';

  // Checkbox
  const checkbox = document.createElement('input');
  checkbox.type = 'checkbox';
  checkbox.checked = tarefa.done || false;
  checkbox.addEventListener('change', () => {
    tarefa.done = checkbox.checked;
    salvarStatusConcluido(dia, index, tarefa.done);
    if (tarefa.done) {
      span.classList.add('completed');
    } else {
      span.classList.remove('completed');
    }
  });
  main.appendChild(checkbox);

  // Texto da tarefa
  const span = document.createElement('span');
  span.className = 'task-text';
  span.textContent = `${tarefa.start} - ${tarefa.end} | ${tarefa.desc}`;
  if (tarefa.done) span.classList.add('completed');
  main.appendChild(span);

  // Botões de ação
  const actions = document.createElement('div');
  actions.className = 'task-actions';
  actions.innerHTML = `
    <button class='btn-edit' onclick="editarTarefa('${dia}', ${index})">✏️</button>
    <button class='btn-delete' onclick="excluirTarefa('${dia}', ${index})">🗑</button>
    <button class='btn-copy' onclick="copiarTarefa('${dia}', ${index})">📋</button>
  `;
  main.appendChild(actions);
  li.appendChild(main);

  if (tarefa.details) {
    const details = document.createElement('div');
    details.className = 'task-details';
    details.textContent = `➡️ ${tarefa.details}`;
    li.appendChild(details);
  }

  lista.appendChild(li);
}

function salvarStatusConcluido(dia, index, done) {
  const tarefas = JSON.parse(localStorage.getItem(dia)) || [];
  if (tarefas[index]) {
    tarefas[index].done = done;
    localStorage.setItem(dia, JSON.stringify(tarefas));
  }
}

function adicionarTarefa(dia) {
  const start = document.getElementById(`start-${dia}`).value;
  const end = document.getElementById(`end-${dia}`).value;
  const desc = document.getElementById(`desc-${dia}`).value.trim();
  const details = document.getElementById(`details-${dia}`).value.trim();
  if (!start || !end || !desc) return;

  const tarefas = JSON.parse(localStorage.getItem(dia)) || [];
  if(tarefas.length >= 20) { alert('Limite de 20 tarefas por dia atingido!'); return; }
  tarefas.push({ start, end, desc, details, done: false });
  localStorage.setItem(dia, JSON.stringify(tarefas));
  carregarPlanner();
}

function editarTarefa(dia, index) {
  const tarefas = JSON.parse(localStorage.getItem(dia)) || [];
  const tarefa = tarefas[index];
  const start = prompt('Editar hora início:', tarefa.start);
  const end = prompt('Editar hora fim:', tarefa.end);
  const desc = prompt('Editar descrição:', tarefa.desc);
  const details = prompt('Editar detalhes:', tarefa.details);
  if (start && end && desc) {
    tarefas[index] = { start, end, desc, details, done: tarefa.done || false };
    localStorage.setItem(dia, JSON.stringify(tarefas));
    carregarPlanner();
  }
}

function excluirTarefa(dia, index) {
  const tarefas = JSON.parse(localStorage.getItem(dia)) || [];
  tarefas.splice(index, 1);
  localStorage.setItem(dia, JSON.stringify(tarefas));
  carregarPlanner();
}

function copiarTarefa(dia, index) {
  const tarefa = JSON.parse(localStorage.getItem(dia))[index];
  diasSemana.forEach(d => {
    if(d !== dia){
      const tarefas = JSON.parse(localStorage.getItem(d)) || [];
      if(tarefas.length < 20){
        tarefas.push({ ...tarefa });
        localStorage.setItem(d, JSON.stringify(tarefas));
      }
    }
  });
  carregarPlanner();
}

function adicionarDragAndDrop() {
  let dragged;
  document.querySelectorAll('.task-item').forEach(item => {
    item.addEventListener('dragstart', e => { dragged = item; e.dataTransfer.effectAllowed = 'move'; });
    item.addEventListener('dragover', e => e.preventDefault());
    item.addEventListener('drop', e => {
      e.preventDefault();
      if(dragged && dragged !== item){
        const parent = item.parentNode;
        parent.insertBefore(dragged, item);
        salvarOrdem(parent);
      }
    });
  });
}

function salvarOrdem(lista) {
  const dia = lista.id.replace('lista-','');
  const tarefas = [];
  lista.querySelectorAll('.task-item').forEach(li => {
    const text = li.querySelector('.task-text').textContent.split('|');
    const hora = text[0].trim().split(' - ');
    const desc = text[1].trim();
    const detailsEl = li.querySelector('.task-details');
    const details = detailsEl ? detailsEl.textContent.replace('➡️ ','') : '';
    const done = li.querySelector('input[type="checkbox"]').checked;
    tarefas.push({ start: hora[0], end: hora[1], desc, details, done });
  });
  localStorage.setItem(dia, JSON.stringify(tarefas));
}

carregarPlanner();
</script>
</body>
</html>
