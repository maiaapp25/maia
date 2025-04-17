# MAIA — Mercado AI Agent

Maia (Mercado AI Agent) é uma automação inteligente dedicada ao Mercado Livre, sua função é analisar os anúncios do vendedor e manter uma margem líquida pré-configurada pelo usuário, o que garante a venda com lucro.
Maia também participa, automaticamente, de promoções criadas pelo Mercado Livre, respeitando um teto de porcentagem também pré-configurado pelo usuário.

Ela foi desenvolvida para analisar os anúncios do vendedor, cruzar os dados com os custos fornecidos e ajustar automaticamente os preços de venda, garantindo uma margem líquida pré-configurada pelo usuário. MAIA também participa, automaticamente, de todas as promoções oferecidas pelo Mercado Livre, respeitando um teto de porcentagem de desconto definido por você.

🎯 **Entendemos que participar de todas as promoções disponíveis — desde que com lucro garantido — é uma das estratégias mais poderosas para vender mais no Mercado Livre.** Essa abordagem aquece o algoritmo de relevância da sua conta, o que naturalmente aumenta a exposição dos seus anúncios.

MAIA é simples, eficiente e intuitiva, proporcionando mais tranquilidade e segurança no dia a dia do seu varejo eletrônico.

## Problemas que MAIA resolve:

- O Mercado Livre muda com frequência:
    - O valor do frete embutido nos anúncios acima de R$79
    - As promoções e cards disponibilizados na Central de Promoções
    - A categoria do produto ou taxas pertinentes à categoria

- Gerenciar muitos anúncios e promoções de forma eficaz se torna inviável, prejudicando a rotina e performance do seller
- Erros de cálculo podem gerar vendas no prejuízo
- Ferramentas manuais de precificação são extremamente trabalhosas e tomam muito tempo
- Muitos vendedores ignoram promoções por medo de afetarem seus lucros, MAIA resolve isso com inteligência e velocidade, garantindo tranquilidade com poucos cliques em uma interface simplificada e intuitiva.

## O que a MAIA faz:

- Analisa periodicamente todos os anúncios da sua conta
- Permite upload de uma planilha personalizada, onde o vendedor informa:
  - SKU
  - Custo
  - Impostos (opcional, pode ser determinado em um campo geral para todos os anúncios ou individualmente para cada anúncio)
  - Margem líquida desejada (opcional, pode ser determinado em um campo geral para todos os anúncios ou individualmente para cada anúncio)
- Cruza essas informações com os dados dos anúncios coletados
- Calcula automaticamente os preços de venda ideais com a margem almejada, ajustando os preços de venda automaticamente.
- Participa automaticamente de promoções, respeitando o limite máximo de desconto configurado (ex: até 10%)

Configuração e Estrutura do Projeto
1. Requisitos
Antes de rodar MAIA (Mercado AI Agent), você precisará garantir que tem os seguintes requisitos instalados:

Python 3.8 ou superior

pip (gerenciador de pacotes Python)

Git (para controle de versão)

Flask para a parte web do projeto

Pandas para manipulação de dados

Apscheduler para agendamentos em background

dotenv para carregar variáveis de ambiente

Requests para interagir com a API do Mercado Livre

2. Como Configurar o Ambiente
2.1. Clonando o Repositório
Primeiro, clone o repositório para sua máquina local:

bash
Copiar
Editar
git clone https://github.com/maiaapp25/maia.git
cd maia
2.2. Criando e Ativando o Ambiente Virtual
Para evitar conflitos com outras versões de bibliotecas Python, recomendamos criar um ambiente virtual:

bash
Copiar
Editar
python3 -m venv venv
Para ativar o ambiente virtual:

Windows:

bash
Copiar
Editar
venv\Scripts\activate
Mac/Linux:

bash
Copiar
Editar
source venv/bin/activate
2.3. Instalando Dependências
Com o ambiente virtual ativado, instale as dependências necessárias:

bash
Copiar
Editar
pip install -r requirements.txt
Nota: Se o arquivo requirements.txt ainda não existir, podemos criar um mais tarde, incluindo as dependências necessárias.

2.4. Configuração de Variáveis de Ambiente
O projeto usa um arquivo .env para armazenar informações sensíveis, como credenciais de API. Para configurar o seu ambiente, crie um arquivo .env na raiz do projeto e adicione as seguintes variáveis (você pode obter as credenciais necessárias no Mercado Livre):

bash
Copiar
Editar
MERCADO_LIVRE_APP_ID=<seu-app-id>
MERCADO_LIVRE_APP_SECRET=<seu-app-secret>
MERCADO_LIVRE_ACCESS_TOKEN=<seu-access-token>
Essas variáveis são usadas para autenticar e interagir com a API do Mercado Livre.

2.5. Inicializando o Projeto
Com as dependências instaladas e as variáveis de ambiente configuradas, você pode iniciar o servidor local:

bash
Copiar
Editar
flask run
O servidor estará rodando em http://127.0.0.1:5000/. A partir daí, você pode interagir com a automação MAIA.

3. Estrutura de Arquivos
Aqui está uma visão geral da estrutura do projeto:

bash
Copiar
Editar
maia/
│
├── app.py                   # Arquivo principal para rodar o Flask
├── .env                     # Arquivo de variáveis de ambiente
├── requirements.txt         # Arquivo com as dependências do projeto
├── README.md                # Este arquivo de documentação
└── maia_module/              # Diretório com a lógica do MAIA (funcionalidades)
    ├── auth.py              # Funções de autenticação com o Mercado Livre
    ├── scheduler.py         # Lógica de agendamento para monitorar preços
    └── utils.py             # Funções auxiliares (ex: cálculo de margem)
3.1. Detalhes do Código
app.py: É o arquivo principal que roda o servidor Flask.

auth.py: Contém funções responsáveis pela autenticação e interação com a API do Mercado Livre.

scheduler.py: Lida com a execução periódica de tarefas, como monitoramento de preços e promoções.

utils.py: Funções auxiliares usadas em vários lugares do projeto, como cálculos de margens e manipulação de dados.

4. Como Usar
Agora que o projeto está configurado, o MAIA vai monitorar os anúncios do Mercado Livre e ajustá-los automaticamente para garantir que estejam sempre com a margem líquida correta. Basta fornecer um arquivo com as informações dos produtos e MAIA fará o resto.

4. Como Rodar o Projeto
Para rodar o projeto localmente, siga as instruções abaixo:

Clonar o Repositório

No terminal, digite o comando abaixo para clonar o repositório:

bash
Copiar
Editar
git clone https://github.com/maiaapp25/maia.git
Criar um Ambiente Virtual

No terminal, navegue até o diretório do projeto e crie um ambiente virtual:

bash
Copiar
Editar
python3 -m venv venv
Ativar o Ambiente Virtual

Para ativar o ambiente, use o seguinte comando:

No Windows:

bash
Copiar
Editar
venv\Scripts\activate
No macOS/Linux:

bash
Copiar
Editar
source venv/bin/activate
Instalar as Dependências

Instale as bibliotecas necessárias (depois de ter ativado o ambiente virtual):

bash
Copiar
Editar
pip install -r requirements.txt
Configurar as Variáveis de Ambiente

Para garantir que o projeto tenha acesso às informações sensíveis, você precisará criar um arquivo .env no diretório raiz do projeto. Esse arquivo pode conter informações como:

Chave da API do Mercado Livre

Credenciais de banco de dados

Configurações adicionais

Exemplo de arquivo .env:

ini
Copiar
Editar
MERCADO_LIVRE_API_KEY=your_api_key_here
DB_CONNECTION_STRING=your_db_connection_string_here
Rodar a Aplicação

Depois de configurar tudo, rode a aplicação com o seguinte comando:

bash
Copiar
Editar
python app.py
Acessar Localmente

A aplicação estará rodando em http://127.0.0.1:5000/. Abra esse endereço no seu navegador para interagir com o projeto.
