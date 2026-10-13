# Nubank Home Page API & Interface

Aplicação Full-Stack desenvolvida para estudar o desacoplamento entre front-end e back-end, focando na construção de APIs RESTful dinâmicas e persistência de arquivos binários.

## Tecnologias

- **Back-end:** Node.js, Express, MongoDB (Driver Nativo + GridFS)
- **Front-end:** HTML5, CSS3, Sass, JavaScript (Vanilla/jQuery), Bootstrap 5, Slick Carousel
- **Ferramentas:** Docker, Postman

## Arquitetura e Decisões Técnicas

- **API RESTful Dinâmica:** Estruturação de rotas padronizadas (`POST`, `GET`) para gerenciar 6 recursos distintos de conteúdo (carrosséis, cards e blocos de seção).
- **Gerenciamento de Mídia (GridFS):** Utilização do GridFS do MongoDB para armazenar arquivos de imagem e seus respectivos metadados (título, link, texto) de forma unificada, dispensando serviços externos de storage.
- **Isolamento de Ambiente:** Uso de variáveis de ambiente (`.env`) e containerização básica para organização do fluxo de desenvolvimento.

## Como Executar o Projeto

### Pré-requisitos
- Node.js instalado
- Instância do MongoDB (local ou Atlas)

### 1. Configurando o Back-end
```bash
cd Backend
npm install
