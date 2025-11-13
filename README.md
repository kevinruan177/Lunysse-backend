# Lunysse API

## Descrição do Projeto
O **Lunysse API** é um sistema de gerenciamento e agendamento de consultas psicológicas. Ele permite que psicólogos gerenciem pacientes, consultas, solicitações de agendamento e relatórios de desempenho, incluindo alertas de risco com análise de frequência de sessões. O sistema também integra funcionalidades de análise de risco baseada em métricas de frequência de pacientes (*ML-style analysis*).



### Objetivos
- Facilitar o gerenciamento de pacientes e agendamentos para psicólogos.
- Oferecer relatórios detalhados e métricas de presença/frequência.
- Alertar sobre pacientes de alto risco com base em padrões de comportamento.
- Servir como backend seguro com autenticação via JWT.

---

## Estrutura de Pastas

/lunysse-api
│
├─ core/
│ ├─ database.py # Configuração do SQLAlchemy
│
├─ models/
│ ├─ models.py # Models do banco de dados
│
├─ routers/
│ ├─ auth.py # Rotas de autenticação
│ ├─ appointments.py # Rotas de agendamentos
│ ├─ patients.py # Rotas de pacientes
│ ├─ psychologists.py # Rotas de psicólogos
│ ├─ requests.py # Rotas de solicitações
│ ├─ reports.py # Rotas de relatórios
│ ├─ ml_analysis.py # Rotas de análise de risco
│
├─ schemas/
│ ├─ schemas.py # Schemas Pydantic para validação e resposta
│
├─ services/
│ ├─ auth_service.py # Serviços de autenticação
│ ├─ report_service.py # Geração de relatórios
│ ├─ ml_services.py # Lógica de análise de risco
│
├─ Utils.py # Funções utilitárias (hash, JWT, idade)
├─ main.py # Inicialização do FastAPI
├─ seed.py # Script para popular o banco com dados de teste
├─ test_runner.py # Testes automáticos do sistema
├─ requirements.txt # Dependências do projeto
└─ .env # Variáveis de ambiente (não versionar)

yaml
Copiar código

---

## Instalação e Execução

1. **Clone o repositório**
```bash
git clone https://github.com/kevinruan177/Lunysse-backend.git
cd lunysse-api
Crie e ative um ambiente virtual

bash
Copiar código
python -m venv venv
# Windows
venv\Scripts\activate
# Linux / Mac
source venv/bin/activate
Instale as dependências

bash
Copiar código
pip install -r requirements.txt
Configure o arquivo .env

env
Copiar código
SECRET_KEY=sua_chave_secreta
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
CORS_ORIGINS=http://localhost:3000
Inicialize o banco e rode o servidor

bash
Copiar código
python seed.py       # Popula o banco com dados de teste
uvicorn main:app --reload
Acesse a API

Base URL: http://localhost:8000

Documentação automática: http://localhost:8000/docs

Testes Automáticos
Para validar todas as funcionalidades do sistema:

bash
Copiar código
python test_runner.py
O script testa:

Autenticação e tokens JWT

Listagem e detalhes de pacientes

Listagem de psicólogos

Agendamentos

Solicitações

Geração de relatórios

Análise de risco (ML Analysis)

Tecnologias e Dependências
Python 3.10+

FastAPI: Framework web

SQLAlchemy: ORM para banco de dados

SQLite (padrão) ou outro banco relacional

Pydantic: Validação de dados

Passlib: Hash de senhas (bcrypt)

python-jose: JWT

Requests: Testes automáticos da API

dotenv: Carregamento de variáveis de ambiente

Créditos
Desenvolvido por Kevin Ruan da Costa Santos como projeto de sistema de agendamento psicológico com análises de risco de pacientes.
