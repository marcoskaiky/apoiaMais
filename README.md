# ApoiaMais — Setup local (XAMPP + MySQL)

Este documento descreve como configurar e rodar o projeto localmente usando XAMPP (Apache + MySQL) no Windows.

Pré-requisitos
- PHP >= 8.2 (o projeto usa Laravel 12)
- Composer
- Node.js (16+ recomendado) e npm
- XAMPP (Apache + MySQL)

Passos rápidos
1. Clone o repositório.
2. Instale dependências PHP:

```bash
composer install
```

3. Copie o `.env.example` para `.env` e atualize as variáveis do DB para MySQL (config abaixo):

```bash
cp .env.example .env
```

4. Gere a APP_KEY:

```bash
php artisan key:generate
```

5. No XAMPP: Inicie Apache e MySQL. Crie a database `apoia_mais` via phpMyAdmin (`http://127.0.0.1/phpmyadmin`) com collation `utf8mb4_unicode_ci`.

6. Atualize o `.env` com as credenciais do MySQL (padrão XAMPP):

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=apoia_mais
DB_USERNAME=root
DB_PASSWORD=
```

7. Rode migrations e seeders (se necessário):

```bash
php artisan migrate
```

8. Instale dependências JS e rode Vite (dev):

```bash
npm install
npm run dev
```

9. Suba o servidor Laravel (opcional — você pode usar o Apache/vhost do XAMPP):

```bash
php artisan serve
```