# CloneNubank

Réplica da interface da home do Nubank, com backend em Node.js/Express servindo
o conteúdo dinâmico das seções da página via MongoDB.

## Destaques técnicos

- **Armazenamento de imagens via GridFS**, um bucket por seção da página
  (carrossel, blocos, cards), guardando o arquivo e seus metadados (título,
  texto, link) como uma unidade só, sem precisar de storage externo.
- **Frontend fiel ao design original**, com carrossel (Slick), navbar, hero e
  cards de produto replicando a experiência visual do app real.

## Tecnologias

- Node.js + Express
- MongoDB — driver nativo + GridFS para armazenamento de imagens
- HTML + Bootstrap 5 + jQuery + Slick Carousel (via CDN)
- Sass para estilização
- Docker *(containeriza o frontend estático)*

## Endpoints principais

Padrão consistente para os 6 recursos de conteúdo (`carrosel`, `duploCards`,
`backgroud`, `bloco`, `elementos`, `cardCards`):

- `POST /:recurso` — upload de imagem + metadados
- `GET /:recurso` — lista os itens
- `GET /:recurso/:filename` — stream da imagem

## Como rodar localmente

⚠️ **Nota importante**: o frontend hoje aponta para uma URL de produção fixa
que está fora do ar. Para rodar ponta a ponta localmente, é necessário
primeiro atualizar essa URL no `Frontend/js/script.js` para apontar para o
backend local.

\`\`\`bash
# Backend
cd Backend
npm install
\`\`\`

Crie um `.env` com sua string de conexão MongoDB:
\`\`\`
MONGODB_URI=<sua_string_de_conexão>
PORT=<porta>
\`\`\`

\`\`\`bash
npm start
\`\`\`

\`\`\`bash
# Frontend
cd Frontend
npm install
npm start
\`\`\`

## Limitações conhecidas

Projeto de estudo focado em replicar uma interface real e explorar GridFS —
lacunas conscientes:

- Backend de produção atualmente indisponível
- Sem autenticação (tela de login é só visual)
- Sem testes automatizados (validado manualmente via Postman)
- Sem validação de tipo/tamanho de arquivo no upload
