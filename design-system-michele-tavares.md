# Design System — Michele Tavares
### Base visual para a landing page · Design de Interiores · Lavras/MG

**O que foi lido na identidade dela:** logo com monograma "MT" em preto/carvão serifado de alto contraste, assinatura "Michele Tavares" em script terracota-mocha, subtítulo em caixa alta espaçada. As fotos dos projetos reforçam a mesma linha: ambientes clean, tons terrosos e amadeirados, muito branco/creme, luz natural. **O sistema abaixo é quase monocromático de propósito** — preto/carvão + terracota-mocha sobre creme — porque aqui quem vende é a fotografia dos projetos, não a paleta da marca.

---

## 1. Cores

### 1.1 Paleta principal — Carvão (estrutura e autoridade)

| Token | Hex | Onde usar |
|---|---|---|
| `--ink-950` | `#1C1815` | Fundo dos blocos escuros (hero, CTA final), rodapé, monograma |
| `--ink-800` | `#2E2823` | Corpo de texto principal sobre claro |
| `--ink-600` | `#5C5349` | Texto secundário |

### 1.2 Paleta secundária — Terracota-mocha (assinatura da marca)

Extraída direto do script "Michele Tavares" da logo — é a cor pessoal da marca, não um terracota genérico.

| Token | Hex | Onde usar |
|---|---|---|
| `--mocha-700` | `#7C6857` | Texto com peso sobre claro |
| `--mocha-600` | `#9C8570` | **Cor de ação principal.** Botão primário, assinatura tipográfica |
| `--mocha-400` | `#B9A28C` | Hover, detalhes, ícones |
| `--mocha-200` | `#E4D9CB` | Fundos suaves, badges |

### 1.3 Paleta de suporte — Neutros quentes (a base, como nas fotos dela)

| Token | Hex | Onde usar |
|---|---|---|
| `--cream-50` | `#FAF6F0` | Fundo padrão da página |
| `--sand-100` | `#F0E7DA` | Fundo de seção alternada |
| `--sand-200` | `#E1D3C0` | Bordas de card, divisores |

### 1.4 Funcional

| Token | Hex | Onde usar |
|---|---|---|
| `--whatsapp` | `#25D366` | Exclusivo do botão flutuante e ícone dos CTAs |
| `--whatsapp-dark` | `#128C7E` | Hover do flutuante |
| `--gold-400` | `#C9A96B` | Estrelas de avaliação (dourado terroso, não amarelo puro) |

### 1.5 Proporção (70/20/10)

Aqui o creme domina mais que nos outros sistemas — **70%** neutros quentes, **20%** carvão (estrutura, hero, rodapé), **10%** mocha (e dentro desses 10%, a maior mancha é sempre o botão principal). É a paleta mais "silenciosa" da agência, para as fotos dos projetos serem o centro das atenções.

---

## 2. Tipografia

**Display / títulos — `Playfair Display`** (Google Fonts) — serifada editorial de alto contraste, a mesma linguagem do monograma da logo. Itálico elegante para a assinatura tipográfica.

**Corpo / interface — `Work Sans`** (Google Fonts) — geométrica limpa, deixa a serifada respirar.

```html
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,500;0,600;0,700;1,500&family=Work+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
```

```css
--font-display:'Playfair Display',Georgia,serif;
--font-body:'Work Sans',-apple-system,'Segoe UI',sans-serif;
```

| Nível | Fonte | Tamanho (desktop → mobile) | Peso |
|---|---|---|---|
| H1 | Playfair Display | 58px → 34px | 600 |
| H2 | Playfair Display | 38px → 28px | 600 |
| H3 | Playfair Display | 24px → 21px | 500 |
| H4 / card | Work Sans | 18px → 17px | 600 |
| Lead | Work Sans | 18px → 16px | 500 |
| Corpo | Work Sans | 16px | 400 |
| Eyebrow | Work Sans | 12px | 600, caixa alta, 0.14em — mesmo espaçamento do subtítulo da logo |

Regra: uma expressão-chave por título em **itálico mocha** — é a mesma relação que o script tem com o monograma na logo dela.

---

## 3. Componentes

**Botão primário:** `background: var(--mocha-600)`, texto branco, `border-radius: 4px` (quase reto — reforça o tom editorial/arquitetônico, nada de cantos muito arredondados), altura mín. 56px, ícone WhatsApp em círculo branco à direita.

**Galeria de portfólio:** grade de fotos com proporção variada (não forçar quadrado), `border-radius: 4px`, sem moldura — a foto é o conteúdo, não precisa de ornamento.

**Cards:** fundo branco ou creme, `border-radius: 6px`, borda finíssima `1px solid var(--sand-200)`, sem sombra pesada — sombra quase imperceptível, típica de editorial de design.

**Flutuante do WhatsApp:** círculo 58px, fundo `--whatsapp`, único lugar com o verde de fato.

---

## 4. Estética

| Token | Valor | Aplicação |
|---|---|---|
| `--r-sm` | 4px | Badges, botões — quase reto |
| `--r-md` | 6px | Cards |
| `--r-lg` | 8px | Fotos de portfólio |
| `--r-xl` | 12px | Blocos de seção |

Sombras muito sutis, quase ausentes — o peso visual vem do contraste preto/creme, não de elevação. Espaçamento generoso: seções com até 128px de respiro vertical no desktop — editorial de design não tem pressa.

---

## 5. Conversão para WhatsApp

1. **A galeria de projetos reais é a autoridade** — em design de interiores, portfólio vende mais que qualquer texto.
2. **+14 anos visível no hero** — número real, forte, sem precisar de mais prova.
3. **Um CTA por seção**, texto em primeira pessoa ("Começar meu projeto"), nunca genérico ("Saiba mais").
4. **Espaço generoso ao redor das fotos** — layout apertado mata a percepção de sofisticação que é o produto sendo vendido.

---

## Tokens prontos (CSS)

```css
:root{
  --ink-950:#1C1815; --ink-800:#2E2823; --ink-600:#5C5349;
  --mocha-700:#7C6857; --mocha-600:#9C8570; --mocha-400:#B9A28C; --mocha-200:#E4D9CB;
  --cream-50:#FAF6F0; --sand-100:#F0E7DA; --sand-200:#E1D3C0;
  --whatsapp:#25D366; --whatsapp-dark:#128C7E; --gold-400:#C9A96B;
  --font-display:'Playfair Display',Georgia,serif;
  --font-body:'Work Sans',-apple-system,'Segoe UI',sans-serif;
  --r-sm:4px; --r-md:6px; --r-lg:8px; --r-xl:12px;
}
```

---

## Tom visual em 3 linhas

1. **Carvão e terracota-mocha sobre creme quente**, extraídos direto da logo dela — paleta quase monocromática, de propósito, para as fotos serem a estrela.
2. **Playfair Display editorial com itálico mocha**, apoiada numa sans geométrica limpa: a mesma relação serifa/script que existe na logo.
3. **Cantos quase retos, sombras quase ausentes, respiro generoso**: portfólio de design fala pela fotografia, não pelo enfeite.
