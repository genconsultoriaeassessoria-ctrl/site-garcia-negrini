# Publicar o site garciaenegriniadvogados.com.br

Pasta pronta para subir. Hospedagem sugerida: **GitHub Pages** (gratuita, com HTTPS). O site é estático: sem servidor, sem banco, sem cookies.

## Antes de publicar (o site ainda é rascunho)
1. O Dr. Ricardo aprova os textos. Tudo em amarelo `[entre colchetes]` precisa ser preenchido ou removido (história do escritório, equipe, CNPJ, prazos da política).
2. O WhatsApp do formulário já está configurado com (11) 96337-9182 (`var WHATSAPP` no fim do `index.html`). Para trocar, edite esse número (só dígitos, com 55 e DDD).
3. Revisar `privacidade.html` com o escritório (prazos de guarda). O CNPJ e os horários (segunda a sexta, 9h às 18h) já estão preenchidos.
4. Remover a faixa de rascunho (`<div class="draft">...</div>`) nas duas páginas.
5. Liberar a indexação (só depois da aprovação): apagar a linha `<meta name="robots" content="noindex, nofollow">` em `index.html` e `privacidade.html`, e substituir o conteúdo do `robots.txt` pelo de `robots.producao.txt` (que já aponta o `sitemap.xml`).
6. Conferir fotos, logomarca e textos: só o que o escritório forneceu ou autorizou. Respeitar o Código de Ética da OAB (Provimento 205/2021): sem promessa de resultado, sem captação agressiva, sem valores.
7. OAB/SP 455.904 e CNPJ 57.595.921/0001-61 já estão no rodapé (confirmados pelo escritório).

## Passo 1: GitHub (conta do escritório, com o Dr. Ricardo como dono)
1. Criar o repositório `site-garcia-negrini`, **público** (o Pages gratuito exige; este repositório só tem o site, nenhum segredo).
2. Enviar o conteúdo desta pasta para o repositório (arrastar os arquivos em *Add file > Upload files*; incluir `.nojekyll` e `CNAME`).
3. *Settings > Pages*: Source = *Deploy from a branch*, branch `main`, pasta `/ (root)`. Em *Custom domain*, `garciaenegriniadvogados.com.br`.

## Passo 2: DNS no GoDaddy (só adicionar registros)
**Não troque os nameservers e não mexa em MX, TXT ou CNAME de e-mail**: os e-mails do domínio (inclusive `contato@`) dependem deles.

Em *Meus produtos > Domínio > DNS*:
| Tipo | Nome | Valor |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | `USUARIO.github.io` (o usuário ou organização do GitHub) |

Se existir um registro **A** em `@` apontando para "estacionado"/"parked" do GoDaddy, apague só esse. Confira os IPs na documentação oficial do GitHub Pages antes de salvar.

## Passo 3: HTTPS
Aguarde a propagação (de minutos a algumas horas). Em *Settings > Pages*, marque **Enforce HTTPS**.

## Teste final
- `https://garciaenegriniadvogados.com.br` e `https://www.garciaenegriniadvogados.com.br` abrem o site.
- O formulário abre o WhatsApp com a mensagem pronta.
- `privacidade.html` abre pelo rodapé.
- Os e-mails do domínio continuam funcionando (enviar e receber um teste).

## SEO (já preparado no site)
Título e descrição com "Mauá - SP", endereço visível, dados estruturados (LegalService) com endereço, telefones e e-mail, mapa do site (`sitemap.xml`), imagem de compartilhamento, site rápido (sem scripts de terceiros) e adaptado ao celular. Para o Google encontrar:
1. Publicar e liberar a indexação (passo 5 de "Antes de publicar").
2. Cadastrar o site no **Google Search Console** (verificar o domínio por registro TXT no GoDaddy, sem mexer nos de e-mail) e enviar `https://garciaenegriniadvogados.com.br/sitemap.xml`.
3. Criar ou reivindicar o **Perfil da Empresa no Google** com o mesmo nome, endereço e telefone do site. É o que mais ajuda a aparecer em "advogado em Mauá".
4. Colocar o endereço do site na bio do Instagram.
5. Com o tempo: uma página para cada área de atuação, com texto próprio e informativo, dentro do Código de Ética da OAB.

## Depois
- Alterações: editar o arquivo no GitHub e salvar; o site atualiza sozinho em instantes.
- O painel interno **não** vai neste repositório. Ele usa a conta do Supabase e deve ficar em outro lugar (repositório separado, com publicação própria).
