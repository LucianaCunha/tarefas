# Tarefas

Projeto Django simples para gerenciar tarefas (to-do). Esta documentação rápida explica como configurar e rodar o projeto localmente para quem baixar o repositório.

## Visão geral

Aplicação web Django com uma app `tarefas_app` e templates básicos. Ideal como base para estudos ou como pequena aplicação de demonstração.

## Pré-requisitos

- Python 3.8+ instalado
- [Poetry](https://python-poetry.org/) (recomendado) ou `pip` e um ambiente virtual

## Instalação (passo a passo)

1. Clone o repositório:

```powershell
git clone <url-do-repositorio>
cd tarefas
```

2. Usando Poetry (recomendado):

```powershell
poetry install
poetry shell
```

Se você não usa Poetry, crie um virtualenv e instale dependências manualmente (se houver um `requirements.txt`):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

3. Configurações de ambiente

Por segurança, configure variáveis de ambiente para produção. Em desenvolvimento normalmente não é necessário, mas você pode definir:

- `SECRET_KEY` — chave secreta do Django
- `DEBUG` — `True` ou `False`
- `DATABASE_URL` — string de conexão (se for diferente do SQLite)

Em Windows PowerShell você pode exportar temporariamente assim:

```powershell
$env:SECRET_KEY = "sua_chave_aqui"
$env:DEBUG = "True"
```

4. Migrar o banco de dados

```powershell
poetry run python manage.py migrate
```

5. Criar um superusuário (opcional)

```powershell
poetry run python manage.py createsuperuser
```

6. Rodar o servidor de desenvolvimento

```powershell
poetry run python manage.py runserver
```

Abra `http://127.0.0.1:8000/` no navegador.

## Comandos úteis

- Rodar servidor: `poetry run python manage.py runserver`
- Aplicar migrações: `poetry run python manage.py migrate`
- Criar superuser: `poetry run python manage.py createsuperuser`
- Rodar testes: `poetry run python manage.py test`

Se não usar Poetry substitua `poetry run` por `python` dentro do virtualenv ativado.

## Estrutura principal do projeto

- `manage.py` : comando de gerenciamento do Django
- `config/` : configurações do projeto (`settings.py`, `urls.py`, `wsgi.py`, `asgi.py`)
- `tarefas_app/` : app principal com modelos, views e templates
- `templates/` : templates HTML

## Testes

Se houver testes definidos, rode:

```powershell
poetry run python manage.py test
```

## Tela
<img width="1595" height="605" alt="image" src="https://github.com/user-attachments/assets/aa7dea91-6b26-4aea-9b12-41d2f5fdbd1b" />

## Licença

Adicione aqui a informação de licença do projeto (se houver).


