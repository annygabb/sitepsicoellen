# Relatório de otimização PageSpeed e SEO

## Aplicado

- Imagens de conteúdo convertidas de JPEG/PNG para WebP em qualidade 85.
- Hero com versões responsivas 480w, 720w e 864w, preload, `fetchpriority="high"`, dimensões explícitas e sem lazy loading.
- Imagens abaixo do fold com `loading="lazy"`, `decoding="async"` e dimensões explícitas.
- Logo convertido para WebP.
- Open Graph 1200x630 gerado em `og-image.webp`.
- Favicons 16x16, 32x32, 180x180 e `favicon.ico` gerados.
- Tailwind CDN removido; CSS necessário compilado localmente em `styles.css`.
- GSAP removido do hero e substituído por animação CSS.
- Preloader removido para não atrasar LCP.
- `overflow-x: clip` aplicado.
- Title e description ajustados ao tamanho recomendado.
- Canonical, robots, author, theme-color, Open Graph, Twitter Card e Schema.org completados.
- `robots.txt` e `sitemap.xml` alinhados ao endereço publicado no Vercel.
- Links `target="_blank"` corrigidos para `rel="noopener noreferrer"`.
- Headers de segurança e cache adicionados em `vercel.json`.
- Arquivo principal corrigido de `index.html.html` para `index.html`.

## Comparativo das imagens originais

| Original | Antes | WebP principal | Depois | Redução |
|---|---:|---|---:|---:|
| ellen.jpeg | 154.318 B | ellen.webp | 142.504 B | 7,7% |
| ellenlendo.jpeg | 69.245 B | ellenlendo.webp | 48.078 B | 30,6% |
| logosmefundo.png | 43.342 B | logosmefundo.webp | 8.786 B | 79,7% |

No mobile, o hero pode carregar `ellen-480.webp` (46.738 B), reduzindo cerca de 69,7% em relação ao JPEG original.

## Validação

- JavaScript inline passou em `node --check`.
- 1 H1 presente; estrutura principal preservada.
- Todas as imagens têm `alt`, `width` e `height`.
- Nenhum script externo de Tailwind ou GSAP permanece.
- OG image validada em 1200x630.
- Title: 40 caracteres.
- Meta description: 144 caracteres.

> A nota exata do PageSpeed deve ser medida após o deploy, porque depende também da rede, CDN, servidor, fontes externas e ambiente real do navegador.

## SEO + AEO + GEO — atualização de 24/08/2026

- `title` atualizado com a keyword local principal no início: **Psicóloga em Silvânia-GO**.
- `meta description` revisada e específica para o serviço/localidade.
- `robots` ampliado para previews e snippets, mantendo `index, follow`.
- `robots.txt` mantém rastreamento geral permitido e explicita `OAI-SearchBot`.
- `sitemap.xml` mantém somente a URL HTML indexável e recebeu `lastmod`.
- JSON-LD convertido para um `@graph` com `WebSite`, `WebPage`, `Person`, `LocalBusiness`, catálogo de `Service` e `FAQPage`.
- FAQ estruturada usa exatamente as perguntas e respostas visíveis da página.
- Criado `/llms.txt` em formato compatível com a proposta llms.txt v2.
- Criado `/index.md` como versão textual e LLM-friendly do conteúdo principal.
- `<link rel="alternate" type="text/markdown">` e `<link rel="describedby">` adicionados ao HTML.
- Header HTTP `Link` equivalente configurado no `vercel.json`.
- Open Graph/Twitter receberam títulos, descrições e `image:alt` mais consistentes.

> Observação: `llms.txt` ajuda agentes a localizar e interpretar conteúdo, mas **não substitui** `robots.txt` e não garante citação por IAs.

