# Ember - Sistema de Doações, Bans, Tela de Carregamento e Página Inicial

Este repositório contém tutoriais detalhados em inglês e português sobre como instalar e configurar o sistema Ember, que inclui funcionalidades de doações, bans, tela de carregamento e página inicial, utilizando o AAPanel.

## Índice

- [Introdução](#introdução)
- [Requisitos](#requisitos)
- [Instalação](#instalação)
  - [Inglês](#instalação-em-inglês)
  - [Português](#instalação-em-português)

## Introdução

O Ember é uma solução completa para gerenciamento de doações, bans, tela de carregamento e página inicial. Este guia irá ajudá-lo a configurar seu site usando o AAPanel, um painel de controle de hospedagem web simples e eficiente.

## Requisitos

Antes de começar, certifique-se de ter:

- Um servidor com AAPanel instalado
- Acesso ao domínio que você deseja usar
- Credenciais de administrador para AAPanel

## Instalação

### Instalação em Inglês

#### Installation of Ember - donation system, bans, loading screen & landing/index page via AAPANEL

1. **Install AAPanel**

2. **Initial Setup**
   - When you start and access AAPanel, it will ask if you want to install website dependencies.
   - Install NGINX, MySQL, PHP 8.1, phpMyAdmin, and other dependencies as needed.

3. **Add Website**
   - Go to the "Website" section and click on "Add Site."
   - Enter your domain name in the "Domain name" field.
   - In the "Database" section, select MySQL.
   - Set the PHP version to 8.1.
   - Confirm to generate the configurations.

4. **Website Configuration**
   - In the "Website" section, click on the root path displayed `/www/wwwroot/{DOMAIN}`
     - Delete all files within this folder. (Some files might not delete in bulk, so delete them one by one if necessary)
   - Upload the Web folder downloaded from the Ember site.
   - Configure the `config.php` file.
     - MySQL credentials can be found under the "Databases" category. Retrieve and save them to put into this file.
   - After uploading, go back to the "Website" section, click on the domain, and a configuration pop-up will open.
     - Go to the "Site directory" category and set the main directory to the web folder you uploaded. Save it.
     - Set the "Running directory" to the Public folder. Save it.

5. **URL Rewrite Configuration**
   - Go to "URL rewrite" and insert the following content:

```nginx
location / {
    try_files $uri $uri/ /index.php?$query_string;
}

```

### Instalação em português

## Instalação do Ember - sistema de doações, bans, tela de carregamento e página inicial via AAPANEL

### Guia Passo a Passo

1. **Instale o AAPanel**

2. **Configuração Inicial**
   - Quando você iniciar e acessar o AAPanel, ele perguntará se você deseja instalar as dependências do site.
   - Instale NGINX, MySQL, PHP 8.1, phpMyAdmin e outras dependências conforme necessário.

3. **Adicionar Website**
   - Vá para a seção "Website" e clique em "Add Site".
   - Insira o nome do seu domínio no campo "Domain name".
   - Na seção "Database", selecione MySQL.
   - Defina a versão do PHP para 8.1.
   - Confirme para gerar as configurações.

4. **Configuração do Website**
   - Na seção "Website", clique no caminho raiz exibido `/www/wwwroot/{DOMAIN}`
     - Delete todos os arquivos dentro desta pasta. (Alguns arquivos podem não ser deletados em massa, então apague-os um por um, se necessário)
   - Faça o upload da pasta Web baixada do site da Ember.
   - Configure o arquivo `config.php`.
     - As credenciais do MySQL podem ser encontradas na categoria "Databases". Recupere e salve-as para colocar neste arquivo.
   - Após o upload, volte à seção "Website", clique no domínio e um pop-up de configuração será aberto.
     - Vá até a categoria "Site directory" e defina o diretório principal até a pasta web que você enviou. Salve.
     - Defina o "Running directory" para a pasta Public. Salve.

5. **Configuração de Reescrita de URL**
   - Vá para "URL rewrite" e insira o seguinte conteúdo:

```nginx
location / {
    try_files $uri $uri/ /index.php?$query_string;
}

```
