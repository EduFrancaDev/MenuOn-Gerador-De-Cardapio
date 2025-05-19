🍽️ Menu On - Gerador de Cardápios Online

Menu On é uma plataforma digital pensada para modernizar o gerenciamento de cardápios em restaurantes, lanchonetes, bares e demais estabelecimentos do setor alimentício. Com uma interface simples e funcional, o sistema permite o cadastro e exibição de pratos, bebidas e sobremesas — tudo acessível por meio de um QR Code.

🚀 Funcionalidades
Cadastro de restaurante com tipo e categoria

Registro de pratos, bebidas e sobremesas com nome, descrição e imagem

Visualização de cardápio via link ou QR Code

Organização dos itens em categorias

Interface responsiva com HTML, CSS e JavaScript

Backend robusto com Flask + PostgreSQL

🛠️ Tecnologias Utilizadas
Tecnologia	Descrição	Justificativa
Python	Linguagem de programação	Base principal do backend
Flask	Microframework web	Leve e ideal para construção de APIs
PostgreSQL	Banco de dados relacional	Seguro, escalável e confiável
HTML/CSS/JavaScript	Front-end clássico	Total controle da interface com código limpo e responsivo
Git & GitHub	Controle de versão	Colaboração e versionamento de código

🎯 Objetivo do Projeto
O Menu On busca oferecer uma solução acessível e tecnológica para micro e pequenas empresas do setor alimentício. O sistema reduz custos com impressão de cardápios e melhora a experiência dos clientes ao acessar as opções de forma rápida, visual e interativa, por meio do celular.

Gerador de cardápio para restaurantes

Criar ambiente virtual:

python3 -m venv venv
source venv/bin/activate

Instalar as dependências:

pip install -r requirements.txt

Rodar servidor Flask:

python run.py

Docker:

1. Subindo o container
   No terminal, com Docker rodando:
   docker compose up -d
   "-d roda em background"

Se for a primeira vez, ele baixa a imagem (~200 MB).

2. Verifique se tudo está vivo

   docker compose ps
   Você deve ver algo como:

markdown
Copiar
Editar
Name Command State Ports

---

meu-postgres_db_1 docker-entrypoint.sh postgres Up 0.0.0.0:5432->5432/tcp
E, para logs:

docker compose logs -f db

3. Conectando ao banco
   Via terminal (psql)

psql -h localhost -U douglas -d meu_banco

4. Derruba o Docker
   docker compose down

EDUARDO passo a passo para fazer funcionar (ngrok):

1 passo

abrir vscode

2 passo

ativar ambiente virtual

comando: .\venv\Scripts\Activate.ps1

3 passo

abrir novo terminal (clicar no +)

abrir app Docker Desktop (baleinha) e verificar se não tem nenhum contêiner rodando

agora comando para buildar e dar up ao mesmo tempo

docker compose up --build -d (comando para dar kill no Docker é: Docker compose down -v)

abrir app denovo e ver se contêiner ta rodando

4 passo

abrir o DBeaver (topeirinha) e testar conexão com Docker

5 passo

expor o ngrok

vscode

comando: cd ngrok

comando: .\ngrok http 5000

(ATENÇÃO: Atualizar a URL do endpoint Cadastrar_user.py com a URL do ngrok) + ctrl + s

7 passo

rodar o flask python run.py

8 passo

abrir Postman

requisição tipo POST

copiar a url do ngrok e colar la e na frente /criar-tabelas

## ver na topeirinha se as tabelas foram criadas

pra dar kill em tudo

parar servidor flask Ctrl + C
parar o ngrok com Ctrl + C
dar kill no docker com docker compose down -d

data base ficará limpo assim
