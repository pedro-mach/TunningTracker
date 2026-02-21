🚀 Guia Inicial: TunningTracker (Django) Este guia serve como um passo a passo para configurar o ambiente e a estrutura inicial de qualquer projeto Web utilizando Python
e Django.

1. Isolando o Ambiente (venv) O primeiro passo é garantir que as bibliotecas do projeto não interfiram no seu sistema global.

Criar a pasta e entrar nela:

Bash mkdir TunningTracker && cd TunningTracker Criar o ambiente virtual:

Bash python -m venv venv Ativar o ambiente:

Windows: venv\Scripts\activate

Linux/Mac: source venv/bin/activate

2. Instalação e Estrutura Base Com o ambiente ativo, instalamos o framework e criamos a "espinha dorsal" da aplicação.

Instalar Django: pip install django

Criar o Projeto (Setup): django-admin startproject setup .

Nota: O . no final é crucial para criar os arquivos na pasta atual, evitando pastas duplicadas.

Criar o App (Core): python manage.py startapp core

3. Configurações (setup/settings.py) No arquivo de configurações, precisamos avisar ao Django onde estão nossos arquivos.

Registrar o App: Em INSTALLED_APPS, adicione 'core',.

Caminho dos Templates: Em TEMPLATES, altere a linha DIRS para:

Python 'DIRS': [BASE_DIR / 'templates'], 4. Criando a Primeira Rota (URL + View) O fluxo do Django segue: URL ➔ View ➔ Template.

View (core/views.py):

Python from django.shortcuts import render

def home(request): return render(request, 'index.html') URL (setup/urls.py):

Python from core.views import home urlpatterns = [ path('admin/', admin.site.urls), path('', home, name='home'), ]

5. Frontend e Arquivos Estáticos Para que o site tenha cara de "TunningTracker", precisamos de HTML e CSS.

Pastas na Raiz: Crie as pastas templates/ e static/css/.

Template (templates/index.html): Use {% load static %} no topo para carregar arquivos CSS/Imagens.

CSS (static/css/style.css): Estilize sua página conforme o projeto.

6. Comandos de Inicialização Sempre que retomar o projeto, use estes comandos:

Migrar Banco (Padrão): python manage.py migrate

Rodar Servidor: python manage.py runserver
