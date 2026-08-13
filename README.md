# Copiloto de Inovação

Projeto estático de protótipo para geração de desafios, ideias e portfólio pessoal de inovação, conforme o PRD e o design system do repositório.

## Como abrir

- Abra o arquivo `index.html` diretamente no navegador, ou
- Rode um servidor estático na pasta do projeto e acesse `/index.html`.

Exemplo:

```bash
cd /caminho/para/o/projeto
python3 -m http.server 8000
```

Depois acesse `http://localhost:8000`.

## Funcionalidades

- Abas para explorar desafios, gerar ideias e visualizar ideias salvas.
- Geração local de conteúdo mock via `chamarIA(tipo, contexto)`.
- Persistência em `localStorage` com fallback em memória para protótipo local.
- Edição e exclusão de ideias salvas no navegador.
