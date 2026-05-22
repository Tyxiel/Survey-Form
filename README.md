# tyxiel-survey-form

> 📋 Formulário de pesquisa estático para coleta de feedback de usuários. Interface limpa e responsiva com múltiplos tipos de entrada, validação nativa e design visualmente atraente.

[🇧🇷 Português](#-visão-geral-pt) | [🇺🇸 English](#-overview-en)

---

## 📋 Table of Contents

- [Visão Geral (PT)](#-visão-geral-pt)
- [Overview (EN)](#-overview-en)
- [Tech Stack](#-tech-stack)
- [Prerequisites](#-prerequisites)
- [Getting Started](#-getting-started)
- [Architecture](#-architecture)
- [Form Fields Reference](#-form-fields-reference)
- [Environment Variables](#-environment-variables)
- [Available Scripts](#-available-scripts)
- [Testing](#-testing)
- [Deployment](#-deployment)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🇧🇷 Visão Geral (PT)

Formulário de pesquisa estático desenvolvido para coletar feedback de usuários sobre um website. Inclui campos para nome, e-mail, idade, nível de satisfação (dropdown), facilidade de uso (radio buttons), frequência de uso (checkboxes) e comentários adicionais (textarea). Totalmente responsivo, sem dependências JavaScript e com validação HTML5 nativa.

### Principais Funcionalidades

- ✅ Validação nativa HTML5 (`required`, `type="email"`, `min`/`max`)
- ✅ Múltiplos tipos de input: text, email, number, select, radio, checkbox, textarea
- ✅ Design responsivo com container centralizado e background com overlay
- ✅ Acessibilidade: labels associados via `for`, IDs semânticos, contraste adequado
- ✅ Zero JavaScript: formulário funcional apenas com HTML/CSS
- ✅ Imagem de background externa (Unsplash) com filtro de brilho
- ✅ License AGPL v3 para software livre

### Limitações Conhecidas

| Limitação | Impacto | Workaround |
|-----------|---------|------------|
| Sem backend para processar submissions | Dados não são salvos | Integrar com Formspree, Netlify Forms ou backend próprio |
| Validação apenas no client-side | Usuários podem burlar | Adicionar validação server-side ao integrar backend |
| Imagem de background externa | Dependência de CDN | Hospedar imagem localmente ou usar base64 |
| Sem feedback visual pós-submissão | Usuário não sabe se enviou | Adicionar JavaScript para `preventDefault` + mensagem de sucesso |

---

## 🇺🇸 Overview (EN)

Static survey form designed to collect user feedback about a website. Includes fields for name, email, age, satisfaction level (dropdown), ease of use (radio buttons), usage frequency (checkboxes), and additional comments (textarea). Fully responsive, zero JavaScript dependencies, with native HTML5 validation.

### Key Features

- ✅ Native HTML5 validation (`required`, `type="email"`, `min`/`max`)
- ✅ Multiple input types: text, email, number, select, radio, checkbox, textarea
- ✅ Responsive design with centered container and background overlay
- ✅ Accessibility: labels with `for` attributes, semantic IDs, proper contrast
- ✅ Zero JavaScript: fully functional form with HTML/CSS only
- ✅ External background image (Unsplash) with brightness filter
- ✅ AGPL v3 license for free software

### Known Limitations

| Limitation | Impact | Workaround |
|------------|--------|------------|
| No backend to process submissions | Data is not saved | Integrate with Formspree, Netlify Forms, or custom backend |
| Client-side validation only | Users can bypass | Add server-side validation when integrating backend |
| External background image | CDN dependency | Host image locally or use base64 encoding |
| No visual feedback after submit | Users don't know if sent | Add JavaScript for `preventDefault` + success message |

---

## 🛠 Tech Stack

| Category | Technology | Version/Purpose |
|----------|-----------|-----------------|
| **Markup** | HTML5 | Semantic form structure, ARIA-ready IDs, native validation |
| **Styling** | CSS3 | Gradients, filters, transitions, responsive layout |
| **Interactivity** | None (Pure HTML/CSS) | Form works without JavaScript |
| **Images** | Unsplash (CDN) | Background photo with attribution |
| **Hosting** | Any static host | GitHub Pages, Netlify, Vercel, or local file |
| **License** | GNU AGPL v3 | Copyleft license for network software |

### Why This Stack?

- **Zero build step**: Edit `.html`/`.css` and refresh — no compilation needed.
- **Maximum compatibility**: Works in all modern browsers without polyfills.
- **Lightweight**: ~3KB CSS + ~2KB HTML = instant load times.
- **Educational**: Demonstrates native form validation, CSS layout techniques, and accessibility best practices.

---

## 📦 Prerequisites

| Tool | Version | Purpose | Install Command |
|------|---------|---------|----------------|
| **Web Browser** | Chrome 55+, Firefox 52+, Edge 15+, Safari 10+ | Render form and apply CSS | [Download](https://www.google.com/chrome/) |
| **Text Editor** | Any (VS Code recommended) | Edit source files | [VS Code](https://code.visualstudio.com/) |
| **Git** | 2.30+ (optional) | Clone repo and manage versions | `sudo apt install git` / `brew install git` |
| **Node.js** | Not required | — | — |

> 💡 **No package manager, bundler, or runtime needed.** This is a pure static site.

### Form Validation Rules (Native HTML5)

| Field | Type | Validation | Description |
|-------|------|-----------|-------------|
| `#name` | `text` | `required` | Must not be empty |
| `#email` | `email` | `required` | Must match email format |
| `#number` | `number` | `min="13" max="120"` | Age between 13 and 120 |
| `#dropdown` | `select` | `required` (via `disabled selected` placeholder) | Must select an option |
| Radio group | `radio` | One must be `checked` (default: "Very Easy") | Single selection |
| Checkboxes | `checkbox` | Optional (multiple allowed) | Zero or more selections |
| `textarea` | `textarea` | Optional | Free-form comments |

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/tyxiel/tyxiel-survey-form.git
cd tyxiel-survey-form
```

### 2. Open Locally

**Option A: Direct file open (quick test)**
```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows
start index.html
```

**Option B: Local server (recommended for accurate testing)**
```bash
# Python 3
python3 -m http.server 8000
# Then open: http://localhost:8000

# Or with Node.js (if installed)
npx serve .
```

### 3. Using the Form

1. **Name**: Enter your full name (required)
2. **Email**: Enter a valid email address (required, format validated)
3. **Age**: Optional; enter a number between 13 and 120
4. **Satisfaction**: Select one option from the dropdown
5. **Ease of Use**: Select one radio option (default: "Very Easy")
6. **Usage Frequency**: Check any number of options (optional)
7. **Comments**: Add optional feedback in the textarea
8. **Submit**: Click the button (form will attempt to submit)

### 4. Verify Functionality

| Feature | Test Steps | Expected Result |
|---------|-----------|----------------|
| **Required validation** | Leave Name empty, click Submit | Browser shows "Please fill out this field" |
| **Email format** | Enter "invalid-email", click Submit | Browser shows "Please enter a valid email" |
| **Age range** | Enter "10" or "150" in Age | Browser shows "Value must be between 13 and 120" |
| **Dropdown** | Try to submit without selecting | Browser blocks submission (placeholder is disabled) |
| **Radio group** | Click different radio options | Only one remains selected |
| **Checkboxes** | Check multiple boxes | All checked values are retained |
| **Responsive layout** | Resize browser to ≤768px | Container scales, text remains readable |
| **Background image** | Load page | Unsplash winter image appears with brightness filter |

### 5. Customize (Optional)

**Update colors** in `styles.css`:
```css
/* Change gradient colors */
.container {
  background: linear-gradient(45deg, #YOUR_COLOR_1, #YOUR_COLOR_2);
}

/* Change submit button style */
#submit {
  background-color: #YOUR_COLOR;
  border-color: #YOUR_BORDER_COLOR;
}
```

**Change background image**:
```css
.bg-image {
  /* Replace URL with your image */
  background-image: url("https://your-domain.com/your-image.jpg");
  
  /* Or use a local path */
  background-image: url("./assets/background.jpg");
}
```

**Add form submission handler** (optional JavaScript):
```html
<!-- Add before </body> in index.html -->
<script>
  document.getElementById('survey-form').addEventListener('submit', function(e) {
    e.preventDefault(); // Prevent actual submission
    
    // Collect form data
    const data = {
      name: document.getElementById('name').value,
      email: document.getElementById('email').value,
      // ... collect other fields
    };
    
    // Show success message
    alert('Obrigado pelo seu feedback!');
    
    // Optionally send to backend:
    // fetch('https://your-api.com/submit', { method: 'POST', body: JSON.stringify(data) });
    
    // Reset form
    this.reset();
  });
</script>
```

---

## 🏗 Architecture

### Directory Structure

```
tyxiel-survey-form/
├── index.html    # Main entry: HTML structure + form + metadata
├── styles.css    # All visual styling: layout, colors, responsiveness
├── LICENSE       # GNU AGPL v3 license text
└── README.md     # This documentation
```

### File Responsibilities

#### `index.html` — Form Structure

```html
<!-- Semantic HTML5 with accessibility attributes -->
<form id="survey-form">
  
  <!-- Text Input: Name (required) -->
  <label id="name-label" for="name">
    <h3>Name</h3>
    <input required type="text" id="name" placeholder="Enter your name">
  </label>
  
  <!-- Email Input (required, format validated) -->
  <label id="email-label" for="email">
    <h3>Email</h3>
    <input required type="email" id="email" placeholder="Enter your email">
  </label>
  
  <!-- Number Input: Age (optional, range 13-120) -->
  <label id="number-label" for="number">
    <h3>Age</h3>
    <p class="optional">(optional)</p>
    <input type="number" id="number" min="13" max="120" placeholder="Enter your age">
  </label>
  
  <!-- Dropdown: Satisfaction Level -->
  <label id="dropdown-label" for="dropdown">
    <h3>How satisfied are you with our services?</h3>
    <select id="dropdown">
      <option disabled selected value="">Select an option</option>
      <option value="very-satisfied">Very Satisfied</option>
      <!-- ... more options -->
    </select>
  </label>
  
  <!-- Radio Group: Ease of Use -->
  <h3 id="ease">Ease of Use:</h3>
  <label class="radio-form">
    <input type="radio" name="ease-of-use" checked value="very-easy">
    <p>Very Easy</p>
  </label>
  <!-- ... more radio options -->
  
  <!-- Checkbox Group: Usage Frequency -->
  <h3 id="usage">Usage Frequency:</h3>
  <label class="checkbox-form">
    <input type="checkbox" value="daily">
    <span>Daily</span>
  </label>
  <!-- ... more checkbox options -->
  
  <!-- Textarea: Open Comments -->
  <h3>Any other thing you would like to share with us?</h3>
  <label for="textarea">
    <textarea rows="3" placeholder="It would be good to have......"></textarea>
  </label>
  
  <!-- Submit Button -->
  <input id="submit" type="submit" value="Submit">
</form>
```

#### `styles.css` — Design System

```css
/* 1. Reset and base typography */
* { 
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial, Helvetica, sans-serif;
}

/* 2. Full-viewport background with overlay */
.bg-image {
  position: fixed;
  width: 100%;
  height: 100%;
  background-image: url("unsplash-winter.jpg");
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  filter: brightness(0.9); /* Subtle darkening for text contrast */
  z-index: -1;
}

/* 3. Centered form container with gradient */
.container {
  width: 560px;
  max-width: 95vw; /* Responsive fallback */
  background: linear-gradient(45deg, #E6B5A3E6, #F2CCBBE6);
  margin: 20px auto;
  border-radius: 0.5rem;
  z-index: 2;
}

/* 4. Form field styling */
#name, #email, #number {
  width: 100%;
  height: 30px;
  padding: 5px;
  border: 1px solid lightpink;
  border-radius: 0.5rem;
}

/* 5. Hide number input spinners (cross-browser) */
#number-label > input::-webkit-outer-spin-button,
#number-label > input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
#number-label > input[type=number] {
  -moz-appearance: textfield;
  appearance: textfield;
}

/* 6. Radio/Checkbox custom layout */
.radio-form, .checkbox-form {
  display: flex;
  align-items: center;
  gap: 8px;
  margin: 5px 0;
}

/* 7. Submit button with hover feedback */
#submit {
  width: 95%;
  padding: 10px;
  font-size: 1.3rem;
  border-radius: 0.5em;
  border: 1px solid pink;
  background-color: antiquewhite;
  cursor: pointer;
  transition: background-color 0.2s;
}
#submit:hover {
  background-color: #f0e0d0;
}

/* 8. Footer attribution styling */
footer {
  background: linear-gradient(45deg, #E6B5A3E6, #F2CCBBE6);
  width: 280px;
  margin: 0 auto 20px;
  padding: 5px;
  border-radius: 0.5rem;
  text-align: center;
  color: white;
}
```

### Form Submission Flow (Without Backend)

```
User fills form → Clicks "Submit"
       ↓
Browser validates required fields + formats
       ↓
If invalid: Browser shows native error message
       ↓
If valid: Browser attempts to submit to current URL (index.html)
       ↓
Page reloads with form data in URL query string (GET method default)
       ↓
No data is saved (static site limitation)
```

> ⚠️ **Important**: Without a backend, form submissions do not persist data. See [Deployment](#-deployment) for integration options.

### Accessibility Features

```html
<!-- Semantic IDs for labeling and testing -->
<label id="name-label" for="name">Name</label>
<input id="name" required>

<!-- ARIA-ready structure (can be enhanced) -->
<!-- Add aria-describedby for helper text if needed -->

<!-- Sufficient color contrast -->
/* White text on dark gradient background */
color: white;
background: linear-gradient(...);

<!-- Focus indicators (browser default) -->
/* Inputs show outline on focus */

<!-- Reduced motion support (optional enhancement) */
@media (prefers-reduced-motion: reduce) {
  * { transition: none !important; }
}
```

---

## 📝 Form Fields Reference

### Input Fields Table

| Field ID | Label | Type | Required | Validation | Placeholder |
|----------|-------|------|----------|-----------|-------------|
| `#name` | Name | `text` | ✅ Yes | Non-empty | "Enter your name" |
| `#email` | Email | `email` | ✅ Yes | Valid email format | "Enter your email" |
| `#number` | Age | `number` | ❌ No | `min=13`, `max=120` | "Enter your age" |
| `#dropdown` | Satisfaction | `select` | ✅ Yes* | Must select non-placeholder | "Select an option" |
| `name="ease-of-use"` | Ease of Use | `radio` | ❌ No* | Single selection | — |
| `checkbox` group | Usage Frequency | `checkbox` | ❌ No | Multiple allowed | — |
| `textarea` | Comments | `textarea` | ❌ No | Free text | "It would be good to have......" |

\* *Dropdown is "required" via UX pattern (disabled placeholder), not HTML `required` attribute.*

### Dropdown Options

```html
<select id="dropdown">
  <option disabled selected value="">Select an option</option>
  <option value="very-satisfied">Very Satisfied</option>
  <option value="satisfied">Satisfied</option>
  <option value="neutral">Neutral</option>
  <option value="unsatisfied">Unsatisfied</option>
  <option value="very-unsatisfied">Very Unsatisfied</option>
</select>
```

### Radio Options (Ease of Use)

| Value | Label | Default |
|-------|-------|---------|
| `very-easy` | Very Easy | ✅ Checked |
| `somewhat-easy` | Somewhat Easy | ❌ |
| `not-easy` | Not Easy | ❌ |

### Checkbox Options (Usage Frequency)

| Value | Label |
|-------|-------|
| `daily` | Daily |
| `weekly` | Weekly |
| `monthly` | Monthly |
| `less-frenquently` | Less frequently |
| `rarely` | Rarely |

> 🔍 **Note**: There is a typo in the value `less-frenquently` (should be `less-frequently`). Consider fixing in a future update.

---

## 🔐 Environment Variables

**None required.** This is a fully static, client-side form with no backend, server-side rendering, or sensitive configuration.

> ⚠️ **Security Note**: Since there is no backend, no user data is transmitted to a server by default. If you integrate a submission endpoint, ensure:
> - Use HTTPS for all API calls
> - Sanitize and validate all inputs server-side
> - Never expose API keys in client-side code

---

## ⚙️ Available Scripts

| Command | Description | Use Case |
|---------|-------------|----------|
| `python3 -m http.server 8000` | Start local dev server | Test form validation and layout |
| `npx serve .` | Alternative local server (Node) | Quick preview with clean URLs |
| `open index.html` | Open file directly in browser | Fastest local testing |
| `git add . && git commit -m "msg"` | Stage and commit changes | Version control workflow |
| `git push origin main` | Deploy to GitHub Pages | Trigger auto-deploy (if configured) |

### GitHub Pages Deployment Workflow

```bash
# 1. Ensure you're on the main branch
git checkout main

# 2. Commit your changes
git add .
git commit -m "feat: improve form accessibility labels"

# 3. Push to trigger deployment
git push origin main

# 4. Wait ~1-2 minutes, then visit:
# https://tyxiel.github.io/tyxiel-survey-form/
```

> 🔄 **Auto-deploy**: GitHub Pages rebuilds automatically on push to `main`. No build step required.

---

## 🧪 Testing

### Manual Testing Checklist

```markdown
## Validation Tests
- [ ] Submit empty form → Browser shows error for Name field
- [ ] Enter invalid email ("test") → Browser shows format error
- [ ] Enter age=10 or age=150 → Browser shows range error
- [ ] Leave dropdown on "Select an option" → Browser blocks submit
- [ ] All required fields valid → Form "submits" (page reloads)

## UI/UX Tests
- [ ] Container centered on desktop (≥1024px)
- [ ] Container scales on mobile (≤560px) without horizontal scroll
- [ ] Input fields have visible focus states
- [ ] Submit button has hover cursor and visual feedback
- [ ] Text color (white) contrasts with gradient background
- [ ] Background image loads and has brightness filter applied

## Accessibility Tests
- [ ] Tab navigation cycles through all inputs in logical order
- [ ] Labels are clickable and focus associated input
- [ ] Screen reader announces field labels correctly
- [ ] Color contrast ratio ≥ 4.5:1 for body text (verify with tool)

## Cross-Browser Tests
- [ ] Chrome: Validation messages appear correctly
- [ ] Firefox: Number input spinners hidden
- [ ] Safari: Gradient renders without artifacts
- [ ] Edge: Form layout matches design
```

### Automated Testing (Optional)

Since this is a static form, automated tests are optional. If desired:

```bash
# Install Playwright for E2E testing
npm init -y
npm install -D @playwright/test

# Create test: tests/form-validation.spec.js
import { test, expect } from '@playwright/test';

test('valida campos obrigatórios', async ({ page }) => {
  await page.goto('http://localhost:8000');
  
  // Tentar submeter sem preencher
  await page.click('#submit');
  
  // Verificar mensagem de erro do navegador
  const nameInput = page.locator('#name');
  await expect(nameInput).toBeInvalid();
});

test('preenche formulário com sucesso', async ({ page }) => {
  await page.goto('http://localhost:8000');
  
  await page.fill('#name', 'Test User');
  await page.fill('#email', 'test@example.com');
  await page.fill('#number', '25');
  await page.selectOption('#dropdown', 'satisfied');
  await page.check('input[value="daily"]');
  
  await page.click('#submit');
  // Observar recarregamento da página (comportamento padrão)
});
```

### Accessibility Audit (Optional)

```bash
# Install Lighthouse CLI
npm install -g @lhci/cli

# Run audit
lhci autorun --collect.url=http://localhost:8000
```

Or use Chrome DevTools → Lighthouse tab → Generate report.

---

## 🌍 Deployment

### GitHub Pages (Recommended)

**Automatic Setup**:
1. Go to repo **Settings** → **Pages**
2. Set **Source** to `Deploy from branch`
3. Select branch: `main`, folder: `/ (root)`
4. Save → Wait for deployment URL

**No configuration files needed** — pure static site.

### Adding Form Submission (Backend Integration Options)

Since the form has no backend, choose one of these to actually collect responses:

#### Option 1: Formspree (No Code)
```html
<!-- Update <form> tag in index.html -->
<form id="survey-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```
1. Sign up at [formspree.io](https://formspree.io)
2. Create new form, get endpoint URL
3. Replace `YOUR_FORM_ID` in the action attribute
4. Deploy — submissions arrive in your email

#### Option 2: Netlify Forms (Zero Config)
```html
<!-- Add netlify attribute to form -->
<form id="survey-form" name="survey" method="POST" data-netlify="true">
  <!-- Add hidden honeypot field for spam protection -->
  <input type="hidden" name="form-name" value="survey" />
</form>
```
1. Deploy to Netlify
2. Enable "Form Detection" in site settings
3. Submissions appear in Netlify dashboard

#### Option 3: Custom Backend (Advanced)
```javascript
// Example: serverless function (Vercel/Netlify)
// api/submit-survey.js
export default async function handler(req, res) {
  if (req.method !== 'POST') return res.status(405).end();
  
  const { name, email, age, satisfaction } = req.body;
  
  // Validate server-side
  if (!name || !email) {
    return res.status(400).json({ error: 'Missing required fields' });
  }
  
  // Save to database or send email
  // await db.surveys.create({ name, email, age, satisfaction });
  
  res.status(200).json({ success: true });
}
```

Then update form to use fetch:
```html
<script>
document.getElementById('survey-form').addEventListener('submit', async (e) => {
  e.preventDefault();
  const formData = new FormData(e.target);
  const data = Object.fromEntries(formData);
  
  const response = await fetch('/api/submit-survey', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(data)
  });
  
  if (response.ok) {
    alert('Obrigado pelo seu feedback!');
    e.target.reset();
  } else {
    alert('Erro ao enviar. Tente novamente.');
  }
});
</script>
```

### Alternative: Vercel / Netlify (Drag & Drop)

```bash
# 1. Build (no build step needed)
# 2. Drag the entire folder to Netlify Drop or run `vercel --prod`
# 3. Site is live instantly
```

### Custom Domain (Optional)

1. Add `CNAME` file to repo root:
   ```
   pesquisa.seudominio.com.br
   ```
2. Configure DNS with your registrar:
   ```
   Type: CNAME
   Name: pesquisa
   Value: tyxiel.github.io
   ```

---

## 🔧 Troubleshooting

### ❌ Formulário não valida campos obrigatórios

**Cause**: Browser não suporta HTML5 validation ou JavaScript interferindo.

**Solution**:
1. Teste em navegador moderno (Chrome, Firefox, Edge)
2. Verifique se há JavaScript removendo atributos `required`
3. Inspecione o input: deve ter `required` no HTML renderizado

### ❌ Background image não carrega

**Cause**: URL do Unsplash bloqueada, CORS, ou rede lenta.

**Solution**:
```css
/* Fallback: cor sólida se imagem falhar */
.bg-image {
  background-image: url("unsplash-url"), linear-gradient(45deg, #E6B5A3, #F2CCBB);
  background-color: #E6B5A3; /* Cor de fallback */
}

/* Ou hospede a imagem localmente */
.bg-image {
  background-image: url("./assets/background.jpg");
}
```

### ❌ Layout quebrado em mobile

**Cause**: Container com largura fixa (`560px`) sem media query.

**Solution**:
```css
.container {
  width: 560px;
  max-width: 95vw; /* Garante que não ultrapasse a tela */
  margin: 20px auto;
}

/* Opcional: ajuste para telas muito pequenas */
@media (max-width: 400px) {
  .container {
    width: 95vw;
    padding: 10px;
  }
  #survey-form {
    padding: 0.5rem;
  }
}
```

### ❌ Radio buttons não alternam seleção

**Cause**: Inputs não compartilham o mesmo atributo `name`.

**Solution**:
```html
<!-- Todos os radios do mesmo grupo devem ter name="ease-of-use" -->
<input type="radio" name="ease-of-use" value="very-easy">
<input type="radio" name="ease-of-use" value="somewhat-easy">
<input type="radio" name="ease-of-use" value="not-easy">
```

### ❌ Submit recarrega a página sem feedback

**Cause**: Comportamento padrão de forms HTML sem JavaScript.

**Solution**: Adicione um handler para interceptar o submit:
```html
<script>
document.getElementById('survey-form').addEventListener('submit', function(e) {
  e.preventDefault();
  
  // Coletar dados
  const formData = new FormData(this);
  console.log('Dados do formulário:', Object.fromEntries(formData));
  
  // Mostrar mensagem de sucesso
  alert('Obrigado! Seu feedback foi registrado (localmente).');
  
  // Opcional: resetar formulário
  // this.reset();
});
</script>
```

### ❌ Número com setas de incremento (spinners) aparece no Chrome

**Cause**: CSS para esconder spinners não foi aplicado corretamente.

**Solution**: Verifique se estas regras estão presentes em `styles.css`:
```css
#number-label > input::-webkit-outer-spin-button,
#number-label > input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
#number-label > input[type=number] {
  -moz-appearance: textfield;
  appearance: textfield;
}
```

---

## 🤝 Contributing

Contributions are welcome! This project follows the [GNU AGPL v3](LICENSE) license.

### How to Contribute

1. Fork the repository
2. Create a feature branch: `git checkout -b feat/add-phone-field`
3. Commit changes: `git commit -m 'feat: add optional phone field with mask'`
4. Push to branch: `git push origin feat/add-phone-field`
5. Open a Pull Request

### Contribution Guidelines

- ✅ Keep changes focused and atomic (one feature/fix per PR)
- ✅ Test form validation manually in at least 2 browsers
- ✅ Follow existing code style:
  - HTML: Semantic tags, `id` selectors for JS hooks, labels with `for`
  - CSS: No preprocessors, mobile-first approach, consistent spacing
- ✅ Maintain accessibility: labels, contrast, keyboard navigation
- ✅ Update this README if adding user-facing features

### Suggested Improvements

```markdown
✨ Features
- [ ] Campo opcional de telefone com máscara (XX) XXXXX-XXXX
- [ ] Integração com backend (Formspree, Netlify Forms, ou API própria)
- [ ] Mensagem de sucesso personalizada pós-submissão
- [ ] Barra de progresso visual para formulários longos
- [ ] Suporte a múltiplos idiomas (i18n)
- [ ] Upload de arquivo opcional (print de erro, sugestão)

🔧 Technical
- [ ] Corrigir typo: `less-frenquently` → `less-frequently`
- [ ] Adicionar `aria-label` ou `aria-describedby` para campos complexos
- [ ] Extrair cores para CSS custom properties (:root)
- [ ] Adicionar meta tags para SEO básico (description, og:image)
- [ ] Configurar ESLint + Stylelint para consistência

♿ Accessibility
- [ ] Garantir foco visível em todos os elementos interativos
- [ ] Adicionar `role="status"` para mensagens dinâmicas (se adicionar JS)
- [ ] Testar com leitor de tela (NVDA, VoiceOver)
- [ ] Adicionar suporte a `prefers-reduced-motion` nas transições

🎨 Design
- [ ] Animação sutil de entrada para o container (fade-in)
- [ ] Ícones visuais para cada tipo de campo (opcional)
- [ ] Modo escuro via `prefers-color-scheme`
- [ ] Ajustar espaçamento para melhor legibilidade em mobile
```

### Reporting Issues

Use the [GitHub Issues](https://github.com/tyxiel/tyxiel-survey-form/issues) tab with:

- 🐛 **Bug Report**: Steps to reproduce, browser/OS, field tested, expected vs actual
- 💡 **Feature Request**: Use case, proposed solution, priority (low/medium/high)
- ❓ **Question**: Clear description of what you're trying to achieve

---

## 📜 License

Distributed under the **GNU Affero General Public License v3.0**. See [`LICENSE`](LICENSE) for full text.

### What This Means

| You Can | You Must |
|---------|----------|
| ✅ Use commercially | 🔓 Disclose source code if modified and served over network |
| ✅ Modify and redistribute | 🔗 Provide source to network users of modified version |
| ✅ Patent use | 📝 Include license and copyright notices |
| ✅ Private use | 🔄 Share improvements under same license |

> ℹ️ **AGPL Specific**: If you host a modified version on a server and users interact with it over a network (e.g., deploy to Vercel), you **must** make the source code of your modifications available to those users.

### Quick Start with License Compliance

```bash
# When forking/modifying:
# 1. Keep LICENSE file intact
# 2. Add your copyright to modified files:
<!-- Copyright (C) 2026 Your Name -->

# 3. If deploying modified version publicly:
#    - Add a "Source" link in footer pointing to your fork
#    - Or include a modal with source code download option

# Example footer addition in index.html:
<footer>
  <p>
    No Copyright - Made by <a href="https://github.com/Tyxiel">Tyxiel</a>
    | Modified by <a href="https://github.com/you">You</a>
    | <a href="https://github.com/you/tyxiel-survey-form">Source Code</a>
  </p>
</footer>
```

---

## 🙏 Acknowledgments

- [Unsplash](https://unsplash.com/) — For the beautiful winter background photo by [Daniil Silantev](https://unsplash.com/@betagamma)
- [freeCodeCamp](https://www.freecodecamp.org/) — For the Responsive Web Design curriculum and certification project
- [MDN Web Docs](https://developer.mozilla.org/) — For reliable HTML form and CSS documentation
- [GitHub Pages](https://pages.github.com/) — For hassle-free static hosting

---

> 💡 **Pro Tip**: Always test form validation with edge cases: empty strings, extremely long inputs, special characters in name, and email addresses with plus addressing (`user+tag@example.com`). When integrating a backend, never trust client-side validation alone — always validate server-side too.

*Built with ❤️ by [Tyxiel](https://github.com/Tyxiel)*
