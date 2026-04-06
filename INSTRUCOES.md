# Hub de Entregas — Bernardo Ramos
## Como funciona e como atualizar

---

## Estrutura de arquivos

```
Consultoria BernardoRamos/
├── index.html              ← O hub (tela de login + botão de portfólio público)
├── conutric.html           ← Playbook da Conutric (acesso via login)
├── logo.png                ← Logo do site
├── particles.gif           ← GIF de partículas do fundo
├── GIF NOVO.gif            ← GIF animado da tela de login
├── portfolio/
│   ├── index.html          ← Galeria pública de projetos (sem login)
│   ├── ambev-v2.html       ← Projeto Ambev (versão atualizada)
│   ├── dna-condominios-v2.html
│   ├── dress-to-v2.html
│   ├── kariwoka-v2.html
│   ├── kiria-hair-v2.html
│   └── lysoform-v2.html
│   └── assets/
│       ├── slides/         ← Thumbnails e páginas dos slides (PNG)
│       ├── pdfs/           ← PDFs originais dos projetos
│       ├── kariwoka-competitors.png
│       ├── kiria-products.png
│       ├── logo_lysoform.png
│       └── lysoform-competitors.png
└── INSTRUCOES.md           ← Este arquivo
```

---

## Como funciona o site

O site tem **dois acessos**:

1. **Área de clientes** (com login) — acessível pelo `index.html`
   Clientes entram com usuário e senha e veem o playbook deles. Cada cliente tem seu próprio arquivo `.html` na raiz.

2. **Portfólio público** (sem login) — acessível pelo botão "Ver Portfólio" na tela de login
   Qualquer pessoa pode ver os projetos universitários em `portfolio/index.html`.

---

## Como adicionar um novo projeto ao portfólio público

### Passo 1 — Salvar o HTML do projeto

Coloque o arquivo do projeto (ex: `meu-projeto-v2.html`) dentro da pasta `portfolio/`.

Se o projeto tiver imagens próprias (fotos geradas, logos customizados), salve em `portfolio/assets/`.

---

### Passo 2 — Adicionar o card no portfolio/index.html

Abra `portfolio/index.html` e encontre a seção `<div class="projects-grid">`.

Adicione um novo card seguindo o modelo:

```html
<a href="meu-projeto-v2.html" class="project-card">
  <img class="card-thumb" src="assets/slides/meu-thumb.png" alt="Nome do Projeto" loading="lazy">
  <div class="card-badge">
    <span class="card-number">07</span>
    <span class="card-tag">Tipo de Projeto</span>
  </div>
  <div class="card-info">
    <div class="card-company">Nome da Empresa</div>
    <div class="card-desc">Descrição curta do projeto</div>
    <div class="card-cta">
      Ver projeto
      <svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5">
        <path d="M3 8h10M9 4l4 4-4 4"/>
      </svg>
    </div>
  </div>
</a>
```

---

## Como adicionar um novo cliente (área privada)

### Passo 1 — Preparar o arquivo do cliente

Pegue o HTML do playbook/entrega do cliente.

Se ele tiver login próprio (como o da Conutric tinha), faça estas duas mudanças no CSS:
- `#ls { display:flex }` → `display:none`
- `#app { display:none }` → `display:block`

Se não tiver login próprio, não precisa fazer nada. Salve o arquivo como `nomedocliente.html` dentro da pasta raiz.

---

### Passo 2 — Cadastrar no hub

Abra o `index.html` e encontre o bloco `var CLIENTS = {` (fica perto do fim, dentro do `<script>`).

Adicione o novo cliente seguindo o modelo:

```javascript
var CLIENTS = {

  'conutric': {
    senha: 'conutric123',
    label: 'Conutric Consultoria',
    badge: 'Brandbook + Presença Digital',
    url: 'conutric.html'
  },

  // Novo cliente ↓
  'nomedocliente': {
    senha: 'senha123',
    label: 'Nome Completo do Cliente',
    badge: 'Tipo de Entrega',
    url: 'nomedocliente.html'
  }

};
```

---

### Passo 3 — Publicar no GitHub

```bash
git add .
git commit -m "adiciona cliente: Nome do Cliente"
git push
```

O GitHub Pages atualiza em menos de 1 minuto.

---

## Clientes ativos

| Usuário | Cliente | Tipo de Entrega | Arquivo |
|---|---|---|---|
| conutric | Conutric Consultoria | Brandbook + Presença Digital | conutric.html |

---

## Projetos no portfólio público

| Arquivo | Projeto | Tag |
|---|---|---|
| ambev-v2.html | Ambev | Hackathon |
| dna-condominios-v2.html | DNA Condomínios | Estratégia |
| dress-to-v2.html | Dress To | Análise de Marca |
| kariwoka-v2.html | Kariwoka | Análise de Mercado |
| kiria-hair-v2.html | Kiria Hair | Rebranding |
| lysoform-v2.html | Lysoform | Marketing Estratégico |

---

## Links do site

- **Hub principal:** https://angryfps.github.io/bernardo-hub/
- **Portfólio público:** https://angryfps.github.io/bernardo-hub/portfolio/

---

## Ações rápidas

| Ação | O que fazer |
|---|---|
| Novo projeto no portfólio | Salvar HTML em `portfolio/` + adicionar card no `portfolio/index.html` |
| Novo cliente privado | Salvar HTML na raiz + adicionar bloco no CLIENTS do `index.html` |
| Alterar senha de cliente | Mudar campo `senha` no CLIENTS do `index.html` |
| Remover cliente | Deletar o bloco no CLIENTS + apagar o arquivo HTML |
| Atualizar entrega | Substituir o arquivo .html correspondente |

---

*Bernardo Ramos · Consultoria · 2026*
