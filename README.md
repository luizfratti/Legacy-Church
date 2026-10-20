# Batista Legacy Church — site

Site estático (HTML + CSS + JS puro, sem build). Qualquer hospedagem de arquivos estáticos serve:
Vercel, Netlify, Cloudflare Pages ou GitHub Pages.

```
index.html        página única
404.html          página de erro
assets/           css, js e imagens
vercel.json       headers, cache e URLs limpas (Vercel)
robots.txt        regras para buscadores
sitemap.xml       mapa do site
NOTAS.md          notas internas (não é publicado: está no .vercelignore)
```

## Testar localmente
```bash
python3 -m http.server 8000
# abrir http://localhost:8000
```

## 1. Subir para o GitHub
Crie um repositório **privado** (o `NOTAS.md` tem anotações internas) chamado `batista-legacy-church` em
https://github.com/new, sem README. Depois, dentro desta pasta:

```bash
git init -b main
git add .
git commit -m "Site Batista Legacy Church"
git remote add origin https://github.com/SEU-USUARIO/batista-legacy-church.git
git push -u origin main
```

## 2. Publicar na Vercel
1. https://vercel.com/new → **Import Git Repository** → escolha o repositório.
2. Framework Preset: **Other**. Build Command e Output Directory: deixe em branco.
3. **Deploy**. Em *Project Name* use `batista-legacy-church`. O site fica em `https://batista-legacy-church.vercel.app` (se o nome estiver livre).
   Cada `git push` na `main` publica de novo sozinho.

> Se a Vercel der outro endereço, troque `batista-legacy-church.vercel.app` pelo endereço certo
> em `index.html`, `robots.txt` e `sitemap.xml` (é o que faz a prévia do link no WhatsApp mostrar a foto).

## 3. Domínio próprio (batistalegacychurch.com.br)
1. A igreja **já tem** o domínio `batistalegacychurch.com.br` (hoje aponta para um servidor Apache que só exibe a
   página da Eklesia, com certificado vencido). Quem administra o domínio no Registro.br precisa trocar o DNS.
2. Na Vercel: Project → **Settings → Domains** → adicione `batistalegacychurch.com.br` e `www.batistalegacychurch.com.br`.
3. No Registro.br, em **DNS**, crie os registros que a Vercel mostrar (normalmente):
   - `A` → `@` → `76.76.21.21`
   - `CNAME` → `www` → `cname.vercel-dns.com`
4. Espere a propagação (minutos a algumas horas). O HTTPS é automático.
5. Troque o endereço `https://batista-legacy-church.vercel.app` pelo domínio novo em `index.html`,
   `robots.txt` e `sitemap.xml`, e faça `git push`.

## 4. Liberar no Google (só depois que a igreja aprovar)
Por enquanto o site está como **prévia/proposta** e não aparece no Google. Para liberar:
1. Apague a linha `<meta name="robots" content="noindex, nofollow">` do `index.html`.
2. Apague o header `X-Robots-Tag` do `vercel.json`.
3. Troque as fotos de protótipo (Unsplash, recortes do Instagram e logo recriado) pelos arquivos oficiais
   autorizados pela igreja — ver `NOTAS.md` → *Imagens* e *Pendências*.
4. `git push` e cadastre o domínio no Google Search Console (envie o `sitemap.xml`)
   e atualize o campo "site" no Perfil da Empresa no Google e o link da bio do Instagram.

## Outras hospedagens
- **Netlify / Cloudflare Pages:** importar o repositório, sem comando de build, pasta de publicação `/`.
  (O `vercel.json` é ignorado; o `404.html` funciona nas duas.)
- **GitHub Pages:** Settings → Pages → Branch `main` / root. Atenção: o `NOTAS.md` ficaria público.
