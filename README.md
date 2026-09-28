# Projeto-HTML-5-JAVA-SCRiPT-Hotelaria
project


<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Priston Tale - Servidor Oficial</title>
  <style>
    :root {
      --bg-dark: #0a0c10;
      --panel-bg: #141824;
      --gold-primary: #f0b232;
      --gold-glow: #ffe066;
      --text-main: #d1d5db;
      --border-metal: #2e384d;
      --blue-glow: #00d2ff;
      --purple-glow: #c084fc;
    }

  * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background-color: var(--bg-dark);
      color: var(--text-main);
      background-image: radial-gradient(circle at 50% 20%, #1e2638 0%, #0a0c10 80%);
      min-height: 100vh;
    }

    /* Top Navigation */
    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 16px 40px;
      border-bottom: 2px solid var(--border-metal);
      background: rgba(10, 12, 16, 0.9);
      backdrop-filter: blur(8px);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 900;
      color: var(--gold-primary);
      text-transform: uppercase;
      letter-spacing: 3px;
      text-shadow: 0 0 12px rgba(240, 178, 50, 0.5);
    }

    nav a {
      color: var(--text-main);
      text-decoration: none;
      margin-left: 24px;
      font-weight: bold;
      font-size: 0.95rem;
      transition: color 0.3s;
    }

    nav a:hover {
      color: var(--gold-primary);
    }

    /* Hero Section */
    .hero {
      text-align: center;
      padding: 60px 20px 40px;
    }

    .hero h1 {
      font-size: 2.8rem;
      color: #fff;
      text-transform: uppercase;
      letter-spacing: 2px;
      margin-bottom: 12px;
    }

    .hero p {
      font-size: 1.1rem;
      color: #9ca3af;
      margin-bottom: 24px;
    }

    .cta-btn {
      display: inline-block;
      padding: 14px 36px;
      background: linear-gradient(180deg, #f0b232, #b87b0a);
      color: #111;
      font-weight: 800;
      font-size: 1.1rem;
      text-decoration: none;
      border-radius: 4px;
      border: 1px solid var(--gold-glow);
      box-shadow: 0 0 20px rgba(240, 178, 50, 0.4);
      transition: all 0.3s;
      cursor: pointer;
    }

    .cta-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 0 30px rgba(240, 178, 50, 0.7);
    }

    /* Layout */
    .container {
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 20px 60px;
      display: grid;
      grid-template-columns: 2fr 1fr;
      gap: 24px;
    }

    .card {
      background: var(--panel-bg);
      border: 1px solid var(--border-metal);
      border-radius: 8px;
      padding: 24px;
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.5);
    }

    .card h2 {
      color: var(--gold-primary);
      margin-bottom: 16px;
      font-size: 1.3rem;
      border-bottom: 1px solid var(--border-metal);
      padding-bottom: 8px;
    }

    /* Abas das Tribos */
    .tribes-tabs {
      display: flex;
      gap: 10px;
      margin-bottom: 16px;
    }

    .tribe-btn {
      flex: 1;
      padding: 12px;
      background: #1e2638;
      border: 1px solid var(--border-metal);
      color: #fff;
      font-weight: bold;
      border-radius: 4px;
      cursor: pointer;
      transition: 0.3s;
      font-size: 1rem;
    }

    .tribe-btn:hover {
      border-color: var(--gold-primary);
    }

    .tribe-btn.active {
      background: var(--gold-primary);
      color: #0a0c10;
      box-shadow: 0 0 12px rgba(240, 178, 50, 0.4);
    }

    /* Lista de Classes */
    .class-list {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
      gap: 12px;
      margin-bottom: 20px;
    }

    .class-item {
      background: #0f131c;
      border: 1px solid var(--border-metal);
      padding: 14px 10px;
      border-radius: 6px;
      text-align: center;
      cursor: pointer;
      transition: 0.2s;
    }

    .class-item:hover {
      border-color: var(--blue-glow);
      transform: translateY(-2px);
    }

    .class-item.selected {
      border-color: var(--gold-glow);
      background: #1c2333;
      box-shadow: 0 0 12px rgba(240, 178, 50, 0.3);
    }

    .class-item strong {
      display: block;
      color: #fff;
      font-size: 0.95rem;
      margin-bottom: 4px;
    }

    .class-item span {
      font-size: 0.75rem;
      color: #9ca3af;
    }

    /* Painel de Detalhes da Classe Selecionada */
    .class-detail-box {
      background: #0d111a;
      border: 1px dashed var(--border-metal);
      border-radius: 6px;
      padding: 16px;
      margin-top: 10px;
    }

    .class-detail-box h3 {
      color: var(--blue-glow);
      font-size: 1.1rem;
      margin-bottom: 6px;
    }

    .class-detail-box p {
      font-size: 0.9rem;
      line-height: 1.5;
      color: #cbd5e1;
    }

    /* Status do Servidor */
    .stat-row {
      display: flex;
      justify-content: space-between;
      padding: 12px 0;
      border-bottom: 1px dashed var(--border-metal);
      font-size: 0.95rem;
    }

    .status-online {
      color: #10b981;
      font-weight: bold;
    }

    @media (max-width: 768px) {
      .container {
        grid-template-columns: 1fr;
      }
      .hero h1 {
        font-size: 2rem;
      }
    }
  </style>
</head>
<body>

  <header>
    <div class="logo">Priston Tale</div>
    <nav>
      <a href="#classes">Classes</a>
      <a href="#status">Status</a>
      <a href="#downloads">Download</a>
      <a href="#cadastro">Cadastre-se</a>
    </nav>
  </header>

  <section class="hero">
    <h1>O Retorno ao Continente de Priston</h1>
    <p>Taxa de XP: 15x | Drops Customizados | Guerra de Bless Castle Semanal</p>
    <a href="#cadastro" class="cta-btn">JOGAR AGORA</a>
  </section>

  <main class="container">
    
    <!-- Painel de Classes -->
    <section class="card" id="classes">
      <h2>Selecione sua Tribo e Classe</h2>
      
      <!-- Abas de seleção -->
      <div class="tribes-tabs">
        <button id="btn-tempskron" class="tribe-btn active" onclick="trocarTribo('tempskron')">Tempskron</button>
        <button id="btn-morion" class="tribe-btn" onclick="trocarTribo('morion')">Morion</button>
      </div>

      <!-- Container onde as classes aparecem -->
      <div id="class-container" class="class-list"></div>

      <!-- Caixa de detalhes -->
      <div class="class-detail-box">
        <h3 id="detail-title">Lutador</h3>
        <p id="detail-desc">Especialista em combate corpo a corpo, alto dano físico e maestria com Machados.</p>
      </div>
    </section>

    <!-- Status Lateral -->
    <aside class="card" id="status">
      <h2>Status do Reino</h2>
      <div class="stat-row">
        <span>Servidor:</span>
        <span class="status-online">Online</span>
      </div>
      <div class="stat-row">
        <span>Jogadores:</span>
        <strong>1.482</strong>
      </div>
      <div class="stat-row">
        <span>Bless Castle:</span>
        <span>Domingo às 16:00</span>
      </div>
      <div class="stat-row">
        <span>Próximo SOD:</span>
        <span>Em 24 min</span>
      </div>
    </aside>

  </main>

  <!-- Script de Interatividade -->
  <script>
    // Base de dados das classes de Priston Tale
    const classesData = {
      tempskron: [
        {
          nome: "Lutador",
          tipo: "Corpo a Corpo",
          desc: "Guerreiro de força bruta focado em combate próximo. Utiliza Machados pesados e possui alto dano em área com habilidades devastadoras."
        },
        {
          nome: "Mecânico",
          tipo: "Tanque / Suporte",
          desc: "Mestre em tecnologia e defesa. Possui armaduras de alta resistência, escudos reforçados e pode reparar equipamentos em batalha."
        },
        {
          nome: "Pikesman",
          tipo: "Dano Crítico",
          desc: "Combatente veloz armado com Foices e Lanças gigantes. Conhecido por desferir os maiores acertos críticos do continente."
        },
        {
          nome: "Arqueira",
          tipo: "Médio Alcance / Esquiva",
          desc: "Atiradora precisa armada com Arcos e Bestas. Ataca inimigos à distância com tiros múltiplos e alta esquiva."
        },
        {
          nome: "Assassina",
          tipo: "Velocidade / Veneno / Furtividade / dano crítico",
          desc: "Guerreira ágil especializada em Adagas Duplas e Garras, aplicando venenos letais e golpes furtivos em sequência."
        }
      ],
      morion: [
        {
          nome: "Cavaleiro",
          tipo: "Sagrado / Defesa",
          desc: "Guerreiro sagrado empunhando Espadas e Escudos. Canaliza poderes divinos para defesa impenetrável e exorcismo contra mortos-vivos."
        },
        {
          nome: "Atalanta",
          tipo: "Longo Alcance",
          desc: "Guerreira mística que arremessa dardos sagrados (Javelins). Combina agilidade com auras protetoras e suporte à equipe."
        },
        {
          nome: "Sacerdotisa",
          tipo: "Cura / Suporte",
          desc: "Guardiã da luz divina. Responsável pelas maiores magias de cura, ressurreição e bênçãos protetoras essenciais para qualquer grupo."
        },
        {
          nome: "Mago",
          tipo: "Magia Ofensiva",
          desc: "Conjurador dos elementos Fogo, Gelo e Eletricidade. Causa dano massivo à distância com magias em área devastadoras."
        },
        {
          nome: "Xamã",
          tipo: "Invocação / Trevas",
          desc: "Conjurador sombrio capaz de invocar espíritos fantasmagóricos e lançar maldições que enfraquecem grupos inteiros de monstros."
        }
      ]
    };

    let triboAtual = 'tempskron';

    function renderizarClasses(tribo) {
      const container = document.getElementById('class-container');
      container.innerHTML = '';

      const lista = classesData[tribo];

      lista.forEach((item, index) => {
        const card = document.createElement('div');
        card.className = `class-item ${index === 0 ? 'selected' : ''}`;
        card.innerHTML = `<strong>${item.nome}</strong><span>${item.tipo}</span>`;
        
        card.onclick = () => {
          document.querySelectorAll('.class-item').forEach(el => el.classList.remove('selected'));
          card.classList.add('selected');
          atualizarDetalhe(item);
        };

        container.appendChild(card);
      });

      // Atualiza o card de detalhes com o primeiro item da lista
      atualizarDetalhe(lista[0]);
    }

    function atualizarDetalhe(item) {
      document.getElementById('detail-title').innerText = item.nome;
      document.getElementById('detail-desc').innerText = item.desc;
    }

    function trocarTribo(tribo) {
      triboAtual = tribo;
      
      // Atualiza botões
      document.getElementById('btn-tempskron').classList.toggle('active', tribo === 'tempskron');
      document.getElementById('btn-morion').classList.toggle('active', tribo === 'morion');

      renderizarClasses(tribo);
    }

    // Inicializa com Tempskron
    renderizarClasses('tempskron');
  </script>

</body>
</html>
