# PRD — Copiloto de Inovação

> Documento de requisitos do produto (Product Requirements Document).
> Cole este arquivo como base do projeto no GitHub Copilot app. Ele descreve **o que** construir e **as regras** que o agente deve seguir. O design visual fica no arquivo `design-system.md`.

---

## 1. Visão

O **Copiloto de Inovação** é um assistente web que ajuda times de inovação a sair da página em branco: ele levanta **desafios e oportunidades** sobre uma área ou tema, gera **ideias de solução** para um problema descrito num formulário e permite **salvar e editar** essas ideias, formando um portfólio pessoal de inovação.

## 2. Problema

Times de inovação perdem tempo e energia em duas frentes: (1) descobrir *quais* problemas valem a pena atacar numa área, e (2) transformar um problema em ideias concretas e acionáveis. Hoje isso depende de reuniões, planilhas soltas e memória. O Copiloto encurta esse caminho com apoio de IA.

## 3. Usuários

Profissionais de inovação (designers, projetos, negócios, TI) — pessoas com boa noção de negócio e de prompt, mas **sem perfil técnico de programação**. A interface precisa ser autoexplicativa, em português, sem jargão.

## 4. Objetivos e não-objetivos

**Objetivos**
- Gerar desafios/oportunidades a partir de uma área ou tema.
- Gerar ideias de solução a partir de um problema descrito em formulário.
- Salvar, editar e excluir ideias.
- Ser simples, rápido e agradável de usar.

**Não-objetivos (fora do escopo deste protótipo)**
- Autenticação/login de usuários.
- Banco de dados central e compartilhamento entre pessoas.
- Colaboração em tempo real, permissões, histórico de versões.

## 5. Funcionalidades

### F1 — Explorar desafios e oportunidades
- Entrada: um campo de texto para **área ou tema** (ex.: "embalagens sustentáveis").
- Ação: botão **Gerar desafios**.
- Saída: uma lista (cards) de **4 a 6 desafios/oportunidades**, cada um com **título**, **descrição curta** e **"por que importa"**.
- Cada card tem um botão **"Gerar ideias para este desafio"**, que leva o título para o formulário da F2.

### F2 — Gerar ideias de solução
- Entrada: formulário com **Desafio/problema** (obrigatório), **Área/contexto**, **Público-alvo** e **Restrições** (opcional).
- Ação: botão **Gerar ideias de solução**.
- Saída: **3 a 5 ideias** (cards), cada uma com **título**, **descrição**, **primeiros passos** e marcadores de **impacto** e **esforço**.
- Cada ideia tem um botão **Salvar ideia**.

### F3 — Minhas ideias (salvar e editar)
- Lista das ideias salvas.
- Cada ideia pode ser **editada** (título e descrição) e **excluída**.
- Um contador mostra quantas ideias estão salvas.
- Estado vazio amigável quando não há ideias.

## 6. Arquitetura técnica (restrições firmes)

- **Site 100% estático**: apenas **HTML, CSS e JavaScript**. **Sem** frameworks, **sem** back-end, **sem** banco de dados externo, **sem** instalar dependências.
- **Começar como um único arquivo `index.html`** na raiz do repositório (CSS e JS embutidos). Isso mantém o deploy no GitHub Pages trivial. Pode-se separar em mais arquivos depois, se necessário.
- **Persistência das ideias**: usar `localStorage` do navegador, com **fallback em memória** (try/catch) para nunca quebrar. Deixar claro na interface que os dados ficam **apenas naquele navegador** (limitação de protótipo).
- **Geração de conteúdo (IA)**: concentrar TODA a geração em **uma única função `chamarIA(tipo, contexto)`**.
  - **Encontros 09 e 10**: essa função devolve **exemplos locais (mock)**, para o produto ficar navegável sem depender de IA.
  - **Encontro 11**: substituir o corpo por uma chamada real a **OpenRouter** (ou NesGen), com **seleção de modelo** e a **chave colada pelo usuário** e guardada só na sessão do navegador (`sessionStorage`) — **nunca no repositório**.
- **Deploy**: publicação via **GitHub Pages** a partir do repositório (branch principal). Requer **repositório público** no plano gratuito.

## 7. Fluxo de telas

Uma página com três abas: **Explorar desafios**, **Gerar ideias** e **Minhas ideias**. Cabeçalho fixo com nome do produto e um selo de "protótipo". Navegação sem recarregar a página.

## 8. Requisitos não-funcionais

- **Idioma**: português (BR).
- **Responsivo**: funciona bem em telas de notebook e celular.
- **Acessível e limpo**: bom contraste, textos legíveis, feedback visual (carregando, avisos).
- **Rápido**: resposta imediata no mock; no modo real, mostrar estado de "carregando".

## 9. Identidade visual

Seguir o `design-system.md` do projeto (paleta azul/branco corporativa, tipografia e componentes). Cada participante pode adaptar o design system como parte da atividade.

## 10. Roadmap da construção (3 encontros)

- **Encontro 09 — Fundações**: repositório criado, `prd.md` e `design-system.md` no projeto, esqueleto da interface (as 3 abas) gerado a partir deste PRD.
- **Encontro 10 — Telas e funcionalidades**: as três funcionalidades operacionais com dados de exemplo (mock), design system aplicado, ideias salvando e editando. **Sem IA real ainda.**
- **Encontro 11 — IA + publicação**: conectar `chamarIA()` ao OpenRouter/NesGen (chave colada, modelo escolhido), revisar, e **publicar no GitHub Pages**.

## 11. Critérios de aceite (protótipo pronto)

- [ ] As três abas funcionam e navegam sem recarregar.
- [ ] Gerar desafios devolve cards com título, descrição e "por que importa".
- [ ] Gerar ideias devolve cards com título, descrição, primeiros passos, impacto e esforço.
- [ ] Salvar, editar e excluir ideias funciona e persiste ao recarregar (mesmo navegador).
- [ ] Existe uma única função `chamarIA()` isolando a geração, pronta para receber a IA real.
- [ ] O site publica no GitHub Pages e abre por um link.

## 12. Aviso de protótipo (não é produção)

Este é um **protótipo de aprendizagem**. Um MVP real exigiria: um **ambiente de hospedagem com back-end** para guardar a chave de IA com segurança (nunca no navegador), um **banco de dados** para dados compartilhados e duráveis, **autenticação** e tratamento de dados conforme as políticas da empresa. Nada de dados reais ou sensíveis neste protótipo.
