# Manual de Natal — Site Pronto para GitHub Pages

## 📁 Arquivos Gerados

```
Solicitacoes/
├── manual-de-natal.html   # Site completo (HTML + CSS + JS)
├── manifest.json          # PWA manifest
├── sw.js                  # Service Worker (offline)
└── prompt-manual-natal-lovable.md  # Prompt para Lovable
```

---

## 🚀 Como Publicar no GitHub Pages (GRÁTIS)

### Opção 1: Upload Direto (Mais Simples)

1. **Crie um repositório** no GitHub:
   - Acesse https://github.com/new
   - Owner: `damasceno70-collab` (sua org já conectada no Lovable)
   - Nome: `manual-de-natal`
   - Público ✅
   - **Não** inicialize com README

2. **Faça upload dos arquivos**:
   - Na página do repo → "Add file" → "Upload files"
   - Arraste: `manual-de-natal.html`, `manifest.json`, `sw.js`
   - Commit: "Add Manual de Natal site"

3. **Ative GitHub Pages**:
   - Settings → Pages (menu lateral)
   - Source: "Deploy from a branch"
   - Branch: `main` / `/ (root)`
   - Save

4. **Acesse seu site**:
   - `https://damasceno70-collab.github.io/manual-de-natal/`
   - (Pode levar 1-2 minutos para ficar no ar)

---

### Opção 2: Via Git Local (Se Preferir)

```bash
# Na pasta Solicitacoes
git init
git add manual-de-natal.html manifest.json sw.js
git commit -m "Add Manual de Natal site"
git branch -M main
git remote add origin https://github.com/damasceno70-collab/manual-de-natal.git
git push -u origin main
```
Depois ative GitHub Pages nas settings do repo.

---

## 🎨 O Que o Site Tem

| Seção | Funcionalidade |
|-------|----------------|
| **Hero** | Banner natalino + cards de destaques |
| **Categorias** | 5 cards clicáveis (Árvores, Velas, Embalagens, Comidinhas, Família) |
| **Dicas** | 8 projetos completos com filtros (custo, tempo, dificuldade) |
| **Modal de Detalhes** | Materiais, passo a passo, dica extra, botão PDF |
| **Newsletter** | Formulário funcional (simula cadastro) |
| **Footer** | Links, redes sociais, crédito GitHub |

### Recursos Técnicos
- ✅ **React-like** mas **HTML puro** (zero build, zero dependências)
- ✅ **Tailwind-style** via CSS custom properties
- ✅ **Responsivo** (mobile-first, breakpoints 600/768/900px)
- ✅ **Acessível** (ARIA, skip link, foco visível, contraste AA)
- ✅ **PWA Ready** (manifest + service worker para offline)
- ✅ **SEO Otimizado** (meta tags, semantic HTML, structured data ready)
- ✅ **Performance** (CSS/JS inline, sem requests externos exceto fonts)
- ✅ **Tema Natalino** (verde pinheiro #1B4D3E, vermelho #C0392B, dourado #D4A843, creme #FDF6E3)

---

## 🔧 Personalizações Rápidas

### Cores (edite `:root` no `<style>`)
```css
:root {
  --pine: #1B4D3E;        /* Verde principal */
  --red-soft: #C0392B;    /* Vermelho natalino */
  --gold: #D4A843;        /* Dourado */
  --cream: #FDF6E3;       /* Creme fundo */
}
```

### Adicionar Mais Dicas
Edite o array `tipsData` no `<script>` final do HTML. Cada dica segue o schema:
```js
{
  id: 9,
  title: "Nova Dica",
  category: "arvores",  // arvores, velas, embalagens, comidinhas, familia
  cost: "gratis",       // gratis, custo-10, custo-30
  time: "tempo-15",     // tempo-15, tempo-1h, tempo-tarde
  difficulty: "facil",  // facil, medio, dificil
  materials: ["Item 1", "Item 2"],
  steps: ["Passo 1", "Passo 2"],
  extra: "Dica especial...",
  pdfName: "nova-dica.pdf"
}
```

### Newsletter Real
Substitua o `setTimeout` no `newsletterForm.addEventListener('submit')` por chamada real:
```js
// Exemplo com Formspree (grátis até 50/mês)
fetch('https://formspree.io/f/SEU_ID', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ email })
})
```

### PDFs Reais
1. Gere PDFs das dicas (Canva, Word → PDF)
2. Coloque na raiz do repo: `arvore-papel-kraft.pdf`, etc.
3. O botão "Baixar PDF" já aponta para esses arquivos

---

## 📱 Testar Localmente

```bash
# Python 3
cd Solicitacoes
python -m http.server 8000
# Abra http://localhost:8000/manual-de-natal.html

# Ou Node.js
npx serve .
```

---

## 📄 Licença

MIT — Use, modifique, compartilhe à vontade. Créditos ao Manual de Natal são bem-vindos mas não obrigatórios.

---

## 🤝 Próximos Passos Sugeridos

- [ ] Subir no GitHub Pages (Opção 1 acima)
- [ ] Testar no celular (PWA install prompt)
- [ ] Criar 2-3 PDFs reais no Canva
- [ ] Configurar Formspree/Netlify Forms na newsletter
- [ ] (Opcional) Domínio próprio: `manualdenatal.com.br` → CNAME no GitHub Pages
- [ ] (Opcional) Analytics: Plausible.io ou GA4 via env var

---

**Dúvidas? O arquivo `manual-de-natal.html` abre direto no navegador — teste antes de subir!**