## Design System — Copiloto de Inovação
### Versão adaptada com inspiração na Apple Human Interface Guidelines

Este design system define a aparência visual do Copiloto de Inovação.
As funcionalidades existentes devem ser preservadas. A adaptação deve alterar apenas cores, tipografia, espaçamentos, formas, superfícies e estados visuais dos componentes.

---

### 1. Princípios

- **Clareza acima de decoração**
  A interface deve priorizar leitura, compreensão rápida e redução de ruído visual.

- **Hierarquia visual sem esforço**
  Use tamanho, peso tipográfico, cor e espaçamento para deixar evidente o que é principal, secundário ou complementar.

- **Aparência leve, moderna e familiar**
  A interface deve se aproximar de uma experiência nativa, com superfícies claras, cantos arredondados, sombras discretas e interações suaves.

- **Cor com propósito**
  Use cor principalmente para indicar ação, status, feedback ou seleção. Evite usar muitas cores competindo pela atenção.

- **Acessibilidade e contraste**
  Textos, botões e estados devem manter boa legibilidade em diferentes telas, condições de luz e tamanhos de fonte.

- **Consistência entre componentes**
  Botões, campos, cards, abas e tags devem compartilhar a mesma lógica visual de raio, espaçamento, sombra e estados.

---

### 2. Cores

A paleta foi reorganizada para seguir uma lógica mais semântica, inspirada em system colors: fundos, superfícies, textos, separadores, ação e status.

| Token | Uso | Valor |
|---|---|---|
| `--color-bg-primary` | Fundo principal da página | `#F5F5F7` |
| `--color-bg-secondary` | Fundo de áreas agrupadas | `#FFFFFF` |
| `--color-bg-tertiary` | Fundo sutil para blocos internos, áreas vazias ou realces leves | `#F2F2F7` |
| `--color-surface` | Superfície principal de cards, painéis e modais | `#FFFFFF` |
| `--color-surface-elevated` | Superfície elevada, menus, popovers e cards em destaque | `#FFFFFF` |
| `--color-text-primary` | Texto principal | `#1D1D1F` |
| `--color-text-secondary` | Texto secundário, descrições e metadados | `#6E6E73` |
| `--color-text-tertiary` | Texto de apoio, placeholders e informações de baixa prioridade | `#86868B` |
| `--color-separator` | Bordas, divisórias e linhas sutis | `#D2D2D7` |
| `--color-separator-soft` | Divisórias muito discretas | `#E5E5EA` |
| `--color-accent` | Ação principal, links e seleção | `#007AFF` |
| `--color-accent-hover` | Hover de ação principal | `#0066D6` |
| `--color-accent-soft` | Fundo sutil para itens selecionados ou foco | `#EAF4FF` |
| `--color-success` | Sucesso, impacto positivo | `#34C759` |
| `--color-success-soft` | Fundo de tag de sucesso | `#E9F8EE` |
| `--color-warning` | Atenção, esforço ou pendência | `#FF9500` |
| `--color-warning-soft` | Fundo de tag de atenção | `#FFF4E5` |
| `--color-danger` | Erro, exclusão ou ação destrutiva | `#FF3B30` |
| `--color-danger-soft` | Fundo de alerta ou tag destrutiva | `#FFECEB` |
| `--color-focus-ring` | Anel de foco acessível | `#99CFFF` |

#### Regras de uso de cor

- Use `--color-accent` apenas para ações, links, estados ativos e elementos interativos.
- Não use a mesma cor para significados diferentes.
- Evite colorir textos longos. Prefira cor para ações, ícones, estados e realces pontuais.
- Sempre combine status com texto ou ícone, não apenas cor.
- Mantenha fundos neutros e claras diferenciações entre página, grupos e superfícies.

---

### 3. Tipografia

A tipografia deve ser inspirada no sistema da Apple, priorizando legibilidade, hierarquia e adaptação a diferentes densidades de conteúdo.

#### Fonte

```css
font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", "SF Pro Display", "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
```

#### Escala tipográfica

| Token | Uso | Tamanho | Peso | Line-height |
|---|---|---:|---:|---:|
| `--font-large-title` | Título principal da página | `32px` | `700` | `40px` |
| `--font-title-1` | Título de seção importante | `28px` | `700` | `36px` |
| `--font-title-2` | Título de seção | `22px` | `600` | `30px` |
| `--font-title-3` | Título de card ou bloco | `17px` | `600` | `24px` |
| `--font-headline` | Destaques, botões e labels relevantes | `15px` | `600` | `22px` |
| `--font-body` | Texto principal | `15px` | `400` | `22px` |
| `--font-callout` | Texto auxiliar de cards e componentes | `14px` | `400` | `20px` |
| `--font-caption` | Metadados, tags e textos pequenos | `12px` | `500` | `16px` |

#### Regras de tipografia

- Use poucos pesos: regular, medium, semibold e bold.
- Evite pesos muito finos em tamanhos pequenos.
- Títulos devem ser claros e diretos.
- Corpo de texto deve ter line-height confortável.
- Labels de botões devem começar com verbo sempre que possível, como “Gerar ideias”, “Salvar ideia” ou “Revisar sugestão”.
- Evite truncar textos importantes. Quando necessário, permita quebra de linha em descrições e conteúdos de apoio.

---

### 4. Espaçamento, layout e formas

#### Espaçamento

Use uma escala simples baseada em múltiplos de 4px.

| Token | Valor | Uso |
|---|---:|---|
| `--space-1` | `4px` | Ajustes mínimos |
| `--space-2` | `8px` | Gap pequeno |
| `--space-3` | `12px` | Espaço entre conteúdo relacionado |
| `--space-4` | `16px` | Padding padrão |
| `--space-5` | `20px` | Padding confortável |
| `--space-6` | `24px` | Separação entre blocos |
| `--space-8` | `32px` | Separação entre seções |
| `--space-10` | `40px` | Respiro de página |

#### Raios

| Token | Valor | Uso |
|---|---:|---|
| `--radius-sm` | `8px` | Tags, campos compactos |
| `--radius-md` | `12px` | Botões, inputs e controles |
| `--radius-lg` | `16px` | Cards e painéis |
| `--radius-xl` | `20px` | Modais, containers principais |
| `--radius-pill` | `999px` | Pílulas, tags e botões arredondados |

#### Sombras

| Token | Valor | Uso |
|---|---|---|
| `--shadow-sm` | `0 1px 2px rgba(0,0,0,.06)` | Elementos discretos |
| `--shadow-md` | `0 8px 24px rgba(0,0,0,.08)` | Cards elevados |
| `--shadow-lg` | `0 16px 40px rgba(0,0,0,.12)` | Modais e popovers |

#### Layout

- A página deve usar fundo `--color-bg-primary`.
- Cards e painéis devem usar `--color-surface`.
- Use bastante espaço em branco entre seções.
- Prefira alinhamento à esquerda para leitura.
- Agrupe conteúdos relacionados em superfícies claras.
- Use divisórias sutis em vez de bordas muito marcadas.

---

### 5. Componentes

#### 5.1 Botão primário

Uso: ação principal da tela ou do bloco.

```css
background: var(--color-accent);
color: #FFFFFF;
border: none;
border-radius: var(--radius-pill);
font-weight: 600;
min-height: 44px;
padding: 0 18px;
box-shadow: none;
```

Estados:

- **Hover:** usar `--color-accent-hover`.
- **Pressed:** reduzir levemente a escala ou escurecer o fundo.
- **Focus:** aplicar anel `0 0 0 4px var(--color-focus-ring)`.
- **Disabled:** fundo `#D1D1D6`, texto `#FFFFFF`, cursor desabilitado.
- Use no máximo uma ou duas ações primárias por tela.

---

#### 5.2 Botão secundário

Uso: ação complementar sem competir com a ação principal.

```css
background: var(--color-bg-secondary);
color: var(--color-accent);
border: 1px solid var(--color-separator);
border-radius: var(--radius-pill);
font-weight: 600;
min-height: 44px;
padding: 0 18px;
```

Estados:

- **Hover:** fundo `--color-accent-soft`.
- **Pressed:** fundo levemente mais escuro.
- **Focus:** anel `--color-focus-ring`.

---

#### 5.3 Botão destrutivo

Uso: excluir, remover ou descartar algo.

```css
background: var(--color-danger);
color: #FFFFFF;
border-radius: var(--radius-pill);
font-weight: 600;
min-height: 44px;
```

Regras:

- Não usar estilo primário azul para ações destrutivas.
- Sempre deixar o rótulo claro, como “Excluir ideia” ou “Descartar rascunho”.
- Quando a ação for irreversível, combinar com confirmação.

---

#### 5.4 Campo de texto

Uso: inputs, busca, prompts e campos de edição.
