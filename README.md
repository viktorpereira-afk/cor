<button id="theme-toggle" class="theme-btn">Mudar Tema</button>
/* Cores padrão: Tema Escuro (Tech) */
:root {
  --bg-color: #121214;
  --card-bg: #1e1e24;
  --text-color: #ffffff;
  --text-muted: #a0a0a0;
  --accent-color: #007bff;
}

/* Cores quando o Tema Claro estiver ativo */
body.light-theme {
  --bg-color: #f8f9fa;
  --card-bg: #ffffff;
  --text-color: #212529;
  --text-muted: #6c757d;
  --accent-color: #0056b3;
}

/* Aplicando as variáveis no seu site */
body {
  background-color: var(--bg-color);
  color: var(--text-color);
  transition: background-color 0.3s ease, color 0.3s ease;
  font-family: sans-serif;
}

/* Atualização do card (do código anterior) usando as variáveis */
.tech-card {
  background-color: var(--card-bg);
  color: var(--text-color);
  transition: transform 0.3s ease, background-color 0.3s ease;
}

.card-date, .card-excerpt {
  color: var(--text-muted);
}

/* Estilo simples para o botão */
.theme-btn {
  padding: 8px 16px;
  background-color: var(--accent-color);
  color: #fff;
  border: none;
  border-radius: 20px;
  cursor: pointer;
  font-weight: bold;
  transition: background-color 0.3s;
}
const themeToggleBtn = document.getElementById('theme-toggle');

// Verifica se o usuário já tinha uma preferência salva anteriormente
const currentTheme = localStorage.getItem('theme');
if (currentTheme === 'light') {
  document.body.classList.add('light-theme');
}

// Escuta o clique no botão
themeToggleBtn.addEventListener('click', () => {
  // Adiciona ou remove a classe .light-theme
  document.body.classList.toggle('light-theme');
  
  // Salva a escolha no navegador do usuário
  let theme = 'dark';
  if (document.body.classList.contains('light-theme')) {
    theme = 'light';
  }
  localStorage.setItem('theme', theme);
});
