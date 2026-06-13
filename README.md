# AstenArchive — Portfólio de Alexandre Costa

Portfólio pessoal em **astenarchive.com**: site estático (HTML, CSS e JavaScript puros), sem dependências nem build.

## Estrutura

```
index.html        → página principal (secções: sobre, formação, projetos, competências, contacto)
css/style.css     → estilos (tema escuro, responsivo)
js/main.js        → menu mobile + animações de scroll
CNAME             → domínio personalizado para o GitHub Pages
.github/workflows/deploy.yml → deploy automático a cada push para main
```

## Pré-visualizar localmente

Basta abrir o `index.html` no browser, ou:

```bash
python3 -m http.server 8000
# abrir http://localhost:8000
```

## Publicar com o domínio astenarchive.com

### 1. Ativar o GitHub Pages

No GitHub: **Settings → Pages → Source → GitHub Actions**. O workflow `deploy.yml` publica o site automaticamente a cada push para `main`.

### 2. Configurar o domínio no GitHub

Ainda em **Settings → Pages → Custom domain**, escreve `astenarchive.com` e guarda. Ativa também **Enforce HTTPS** (pode demorar alguns minutos a ficar disponível).

### 3. Configurar o DNS no registador do domínio

No painel onde compraste o astenarchive.com, cria estes registos:

| Tipo  | Nome | Valor             |
|-------|------|-------------------|
| A     | @    | 185.199.108.153   |
| A     | @    | 185.199.109.153   |
| A     | @    | 185.199.110.153   |
| A     | @    | 185.199.111.153   |
| CNAME | www  | `<utilizador>.github.io` |

A propagação do DNS pode demorar de alguns minutos até 24 horas.

## Atualizar conteúdo

- **Novo projeto:** duplica um bloco `<article class="projeto">` em `index.html` (secção `#projetos`) e edita o texto.
- **LinkedIn:** atualiza o link na secção `#contacto`.
- **Cores:** muda as variáveis em `:root` no `css/style.css`.
