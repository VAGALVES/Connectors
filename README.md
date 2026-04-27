# English Connectors & Compounds

> **VS Consulting · Linguistic Lab** — Framework editorial de inglês intermediário-avançado para falantes de português brasileiro.

Aplicação web estática que cataloga os elementos conectivos do inglês — phrasal verbs, advérbios, conjunções, linking words e collocations — curados por frequência real (Corpus of Contemporary American English / COCA). Cada entrada vem com IPA, áudio integrado, tradução, exemplos contextualizados, armadilhas típicas para brasileiros e sinônimos contrastivos.

## Status do projeto · Faseamento

| Fase | Módulo | Entradas | Status |
|------|--------|----------|--------|
| **A** | § 01 Phrasal Verbs | 102 | ✅ **Disponível** |
| B | § 02 Adverbs | ~80 | 🕐 Em curadoria |
| C | § 03 Conjunctions | ~40 | 🕐 Em curadoria |
| D | § 04 Linking Words | ~50 | 🕐 Em curadoria |
| E | § 05 Collocations | ~100 | 🕐 Em curadoria |

A Fase A já entrega um app totalmente funcional. As fases seguintes preencherão os módulos restantes mantendo o mesmo padrão editorial — atualização incremental sem quebra de versão.

## Características

- **102 phrasal verbs** curados por frequência COCA (1-5 estrelas)
- **Sistema cromático tripartite**: alta freq. (sage), atenção (amber), crítico (terra)
- **Áudio integrado** via Web Speech API (en-US, palavra-chave + cada exemplo)
- **Busca instantânea** por palavra, IPA, significado ou exemplo
- **Filtros**: dificuldade, registro (formal/informal), módulo
- **Armadilhas BR**: erros típicos do brasileiro em destaque
- **Sinônimos contrastivos**: cada entrada lista 2-3 alternativas com nuances de uso
- **PWA completo**: instalável, funciona offline
- **Mobile-first**, dark/light theme com persistência, branding VS Consulting

## Stack

- HTML5 + CSS3 + JavaScript vanilla (zero dependências)
- Tipografia editorial: **Fraunces** (display) + **Instrument Sans** (body) + **JetBrains Mono** (técnico)
- Web Speech API para síntese de voz
- Service Worker para cache offline
- Dados isolados em `data.js` (facilita atualizações modulares por fase)

## Estrutura

```
connectors-vs/
├── index.html          # Aplicação principal
├── data.js             # Banco de dados (102 phrasal verbs + placeholders)
├── manifest.json       # PWA manifest
├── sw.js               # Service worker
├── netlify.toml        # Configuração de deploy
├── og-image.png        # Open Graph (1200×630)
├── icon-192.png        # Ícone PWA
├── icon-512.png        # Ícone PWA
├── apple-touch-icon.png # Ícone iOS (180px)
├── favicon.ico         # Favicon multi-size
├── .gitignore
└── README.md
```

## Deploy via GitHub + Netlify (mobile)

### Subir no GitHub

1. `github.com` → toque em `+` → **`New repository`**
2. Nome: `connectors-vs` · Visibility: **Public** · NÃO marque nada extra → **Create**
3. Na tela do repo vazio, toque em **"uploading an existing file"**
4. Selecione TODOS os arquivos da pasta descompactada
5. Mensagem de commit: `feat: phase A · phrasal verbs · v1.0`
6. **Commit changes**

### Conectar Netlify

1. `app.netlify.com` → **Add new site** → **Import an existing project**
2. **Deploy with GitHub** → autorize
3. Selecione `connectors-vs`
4. Não mude nada (`netlify.toml` configura tudo) → **Deploy**

## Atualizações futuras (Fases B+)

Toda fase futura é uma atualização **incremental no `data.js`**. Para receber:

1. Volte ao chat para gerar a próxima fase
2. Receba o `data.js` atualizado
3. No GitHub mobile, substitua apenas o `data.js`
4. Netlify re-deploya automaticamente

Sem refatoração de UI. Sem quebra de versão. Os módulos "soon" no app vão sendo preenchidos progressivamente.

## Considerações para uso na China

1. **Web Speech API** funciona localmente em Chrome/Edge/Safari
2. **Google Fonts** podem ser bloqueados — Service Worker pré-cacheia tudo na primeira visita
3. **Service Worker** garante operação 100% offline após primeira visita

## Roadmap futuro

- [ ] **Fase B**: 80 advérbios em 6 categorias (frequência, modo, tempo, lugar, grau, certeza)
- [ ] **Fase C**: 40 conjunções (coordenativas + subordinativas + concessivas)
- [ ] **Fase D**: 50 linking words / discourse markers
- [ ] **Fase E**: 100 collocations (verb+noun, adj+noun, advérbio+adjetivo)
- [ ] Sistema de progresso (localStorage) — marcar entradas dominadas
- [ ] Modo "drill" — flashcards com algoritmo de repetição espaçada
- [ ] Exportação para Anki

## Créditos

**VS Consulting · Linguistic Lab**

---

*Versão 1.0 (Fase A) · MMXXVI · Um estudo sobre a arquitetura conectiva do inglês.*
