# Notas do site — Batista Legacy Church

- **Status:** site pronto (proposta), em 20/10/2026
- **Dossiê:** `01-captacao/igrejas/batista-legacy-church-espirito-santo-do-pinhal/dossie.md`
- **Conceito:** "a cruz sobre o monte". As linhas onduladas do logo viram um relevo 3D (Three.js) com a cruz
  iluminada no topo. O visual é noturno e de pôster, como as artes do Instagram deles. É um site da **rede** (3 unidades),
  não só de Pinhal.
- **Paleta:** Navy & Carmesim adaptada ao logo: navy `#0F1626`/`#1B2740`, vinho `#7A1E26`, areia `#E8DDCB`,
  papel `#F4EEE3` e acento **amarelo** `#F5D56B` (o amarelo dos cards do "Comunicado oficial").
- **Tipografia:** Anton (títulos pôster) + Instrument Serif itálico (palavra de destaque) + Archivo (texto) +
  Homemade Apple (notas manuscritas).
- **Referências usadas:** IMG_0473 (luz âmbar, serifada com palavra dourada, faixa glass de números no hero) e
  IMG_0479 (nav pill com item ativo, trilho lateral de ícones, cards com setas). A EVO usou 0471/0472; a Renovo, 0480/0475.
- **Headline:** "Vivendo o LEGADO de Cristo."

## Seções
1. Abertura (cruz se desenhando + LEGACY, 1x por sessão)
2. Hero 3D: relevo + cruz + partículas de luz; segue o mouse e a rolagem; números (6 anos · 3 casas · 2026);
   cartão "Próximo culto" com contagem regressiva da unidade escolhida
3. **Unidades**: abas Pinhal / São João / São Paulo, com horários, destaque do próximo culto, mapa, "Como chegar" e
   Instagram. A unidade escolhida fica salva no navegador.
4. Quem somos: texto do comunicado, com as palavras acendendo na rolagem + colagem de polaroids com parallax
5. Pilares: cartões 3D que viram (Intencional, Relacional e Social, com o texto oficial)
6. Versículo do ano: 1 Co 15:58 + letreiro "2026 · Ano da Unidade"
7. Pastores: os 3 casais (medalhões com iniciais)
8. Ministérios: carrossel 3D (setas, arrastar, teclado): GCs, Florescer, Legacy One, Geração Legacy, Instituto
   Legacy, Ministério de Dança e Acampamento
9. GCs: casinhas isométricas que acendem uma a uma + foto real do GC
10. Linha do legado (agenda): faixa horizontal presa na rolagem, de 2020 até "Algo histórico vai acontecer"
11. Contribua: cartão PIX 3D do projeto "Construindo um Legado" (copiar chave)
12. Primeira vez? (FAQ)
13. Contato: formulário que monta a mensagem e abre o direct da unidade escolhida
14. Rodapé com as 3 unidades

## Pendências (dados a confirmar com a igreja)
- [ ] **WhatsApp** oficial (por unidade?). Sem ele, o formulário e o botão flutuante abrem o direct do Instagram
- [ ] **PIX de dízimos e ofertas** gerais. Hoje só aparece o PIX do projeto (`construindoumlegadoblc@gmail.com`)
- [ ] **Fotos dos pastores** e qual casal lidera cada unidade
- [ ] Confirmar o que são **Legacy One** (juventude?) e **Geração Legacy** (adolescentes? crianças?), além de dias e horários
- [ ] Ministério de Dança e Florescer: há encontros fixos?
- [ ] Nome do culto de domingo e de sábado em cada unidade (usei nomes genéricos)
- [ ] O que é o "algo histórico". Quando for anunciado, atualizar o último card da agenda
- [ ] Logo oficial em vetor (o `logo-legacy.svg` e a cruz do site foram recriados como placeholder)
- [ ] Links de YouTube/Facebook (o perfil de São João tem "outros 4 links" não vistos)
- [ ] E-mail de contato (o perfil tem o botão "Email", mas o endereço não aparece)

## Imagens que precisam de autorização
- Recortes do Instagram (`assets/img/ig-*.jpg` e `gc-terca.jpg`): protótipo apenas. Pedir os originais em alta.
- Unsplash (livres): `louvor.jpg`, `kids.jpg`, `mulheres.jpg`, `jovens.jpg`, `comunidade.jpg`, `estudo.jpg`.
  O ideal é trocar por fotos reais dos ministérios.

## Argumento para a abordagem
- O domínio **batistalegacychurch.com.br** já existe, mas mostra **"Sua conexão não é particular"** no Chrome
  (certificado SSL vencido) e, por trás, só exibe a página genérica da Eklesia. Print:
  `01-captacao/igrejas/batista-legacy-church-espirito-santo-do-pinhal/fotos/dominio-certificado-vencido-2026-10-20.png`.
  O site novo pode ir para esse mesmo domínio, com HTTPS automático na Vercel.
- Eles são uma rede com 3 unidades: um site só, com seletor de unidade, resolve a confusão de horários e endereços.

## Deploy (GitHub + Vercel)
- Kit pronto: `vercel.json`, `.gitignore`, `.vercelignore`, `robots.txt`, `sitemap.xml`, `404.html`, `README.md`
  (passo a passo). URL de prévia prevista: `https://batista-legacy-church.vercel.app`.
- Three.js r128 fica local em `assets/js/vendor/three.min.js` (sem depender de CDN). Sem WebGL, aparece um relevo em SVG.
