# Portfólio — Idalécio Bernardo

Site estático (HTML único, sem servidor, sem base de dados, sem formulários).
As fotos e os vídeos estão dentro do `index.html`.

## O que está nesta pasta

| Ficheiro | Para que serve |
|---|---|
| `index.html` | O portfólio completo (já com as proteções de segurança) |
| `404.html` | Página mostrada quando alguém abre um endereço que não existe |
| `robots.txt` | Aceita motores de busca e pede às empresas de IA que não usem as fotos |
| `.nojekyll` | Diz ao GitHub Pages para servir os ficheiros tal como estão |
| `.gitignore` | Evita enviares vídeos/originais por engano se usares o Git |

---

## 1. Antes de publicar: proteger a conta (10 minutos)

1. Cria conta em **github.com** (se ainda não tens), com um email teu que também tenha 2FA.
2. **Settings → Password and authentication → Two-factor authentication**: ativa com uma app (Google Authenticator, Authy) ou com uma *passkey*.
3. Guarda os **códigos de recuperação** num sítio seguro (gestor de palavras-passe ou papel).
4. Usa uma palavra-passe única e longa, num gestor de palavras-passe.

## 2. Tornar o portfólio público (GitHub Pages)

1. Clica em **New repository** (botão verde ou "+" no topo).
   - Nome: `teuutilizador.github.io` (com o teu nome de utilizador exato).
   - Marca **Public** e clica em **Create repository**.
2. Na página do repositório: **uploading an existing file**.
3. Arrasta **todos** os ficheiros desta pasta (`index.html`, `404.html`, `robots.txt`, `.nojekyll`, `.gitignore`, `README.md`) e clica em **Commit changes**.
   - Se o teu computador esconder ficheiros que começam por ponto (`.nojekyll`, `.gitignore`), cria-os depois em **Add file → Create new file**. O `.nojekyll` pode ficar vazio.
4. **Settings → Pages**:
   - *Source*: **Deploy from a branch**
   - *Branch*: `main` e `/ (root)` → **Save**
5. Espera 1–2 minutos. O site fica em `https://teuutilizador.github.io`.
6. Volta a **Settings → Pages** e marca **Enforce HTTPS** (quando a opção estiver disponível).

> O ficheiro `index.html` tem ~14 MB. O GitHub aceita até 25 MB por upload no navegador, por isso cabe.

## 3. Domínio próprio (opcional, ex.: idaleciobernardo.com)

1. Compra o domínio num registador conhecido (Namecheap, Porkbun, Cloudflare…).
2. **Ativa 2FA no registador**, **renovação automática** e **domain lock** (bloqueio de transferência).
3. No GitHub: **Settings → Pages → Custom domain** → escreve o domínio → Save.
4. No registador (DNS), cria os registos que o GitHub indica
   (4 registos `A` para `@` e um `CNAME` de `www` para `teuutilizador.github.io`;
   os endereços atuais estão em docs.github.com → "Managing a custom domain for your GitHub Pages site").
5. Quando o GitHub validar, marca **Enforce HTTPS**.
6. Se for pedido, ativa a verificação do domínio em *Settings → Pages → Verified domains* para ninguém o poder "roubar".

---

## 4. Como gerir o portfólio no dia a dia

**Mudar um texto pequeno** (email, ano, uma frase)
1. No repositório, abre `index.html` e clica no lápis (**Edit**). O ficheiro é grande, por isso o editor pode demorar. Procura o texto com `Ctrl+F`.
2. **Commit changes**. O site atualiza em ~1 minuto.

**Substituir o site por uma versão nova** (novas fotos, nova série)
1. Descarrega o novo `index.html`.
2. No repositório: **Add file → Upload files** → arrasta o `index.html` (substitui o antigo) → **Commit changes**.
3. Se não aparecer logo, abre o site com `Ctrl+Shift+R` (força a atualização).

**Voltar atrás se algo correr mal**
- Abre o ficheiro → **History** → escolhe uma versão anterior → **Revert** / ou descarrega-a e carrega-a de novo. O GitHub guarda todas as versões.

**Cópias de segurança**
- O GitHub guarda o site, mas **não é o teu arquivo**. Mantém os originais (fotos em alta resolução e vídeos) num disco externo e numa nuvem (Google Drive, iCloud…).
- Faz também uma cópia do repositório: **Code → Download ZIP** de vez em quando.

**Ver se está tudo bem**
- Abre o site num telemóvel e num computador.
- Testa: passar o rato sobre as fotos, ampliar, o botão "Mostrar contacto".

**Estatísticas de visitas (opcional)**
- Usa uma ferramenta que respeite a privacidade (Cloudflare Web Analytics, GoatCounter).
- Como o `index.html` tem uma política de segurança estrita, tens de autorizar o endereço do script dessa ferramenta no `script-src` da linha `Content-Security-Policy` (no início do ficheiro) e no `connect-src`. Pede-me e eu faço-o.

**Aparecer no Google**
- Depois de publicar, vai a **search.google.com/search-console**, adiciona o teu endereço e pede a indexação.
- Põe o link do portfólio no Instagram, LinkedIn e na assinatura do email.

---

## 5. O que já está protegido no `index.html`

- **Política de segurança de conteúdo (CSP):** a página só pode carregar o que ela própria contém (mais as fontes do Google). Scripts, imagens e ligações externas ficam bloqueados.
- **Sem referrer** e sem cookies, sem rastreadores.
- **Email e telefone escondidos de robôs de spam:** só aparecem quando alguém clica em "Mostrar contacto".
- **Proteção contra "clickjacking":** a página não funciona dentro de *iframes* de outros sites.
- **Fotos:** o clique direito e o arrastar das imagens estão bloqueados e há aviso de direitos de autor. É um desincentivo, **não uma proteção total**: quem quiser consegue sempre copiar uma imagem que está online. Para proteger as mais valiosas, põe marca de água ou publica só versões reduzidas.
- **IA:** o `robots.txt` pede às empresas de IA que não usem as fotos para treino (pedido voluntário).
- **HTTPS** forçado (ativa "Enforce HTTPS" no GitHub).

## 6. Regras de ouro

- Nunca publiques no repositório palavras-passe, chaves, contratos nem as fotos originais em alta resolução. O repositório é **público**.
- Confirma que tens autorização para mostrar pessoas, sobretudo menores e clientes.
- Se desconfiares que alguém entrou na tua conta: muda a palavra-passe, revê **Settings → Security log** e termina todas as sessões.
- Mantém o email principal e o registador do domínio também com 2FA.

## 7. Limites e crescimento

- Recomendado: repositório até ~1 GB e site até ~1 GB; o GitHub Pages tem um limite "suave" de ~100 GB de tráfego por mês.
- O portfólio guarda tudo num só ficheiro. Quando o `index.html` passar dos 20–25 MB, o melhor é passar as fotos para uma pasta `fotos/` (carrega mais depressa e deixa de haver limite). Pede-me essa versão.
