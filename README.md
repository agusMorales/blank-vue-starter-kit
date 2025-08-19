https://github.com/agusMorales/blank-vue-starter-kit/releases

# Laravel Vue Inertia Starter Kit with TypeScript & Tailwind 🚀

[![Release](https://img.shields.io/github/v/release/agusMorales/blank-vue-starter-kit?color=4c1&label=release&style=flat-square)](https://github.com/agusMorales/blank-vue-starter-kit/releases)

![Laravel + Vue hero](https://user-images.githubusercontent.com/120485/149677662-6c6a4b6b-2c4b-4a8b-a6c8-7a7a3c4d2b2e.png)
![Vue logo](https://upload.wikimedia.org/wikipedia/commons/9/95/Vue.js_Logo_2.svg)
![Laravel logo](https://laravel.com/img/logotype.min.svg)

A minimal starter kit that pairs Laravel with a Vue frontend via Inertia. It uses TypeScript, Tailwind CSS, and Vite for fast builds. This repo does not include auth scaffolding. Download the release archive or installer from the Releases page and execute it to install a packaged release.

Table of contents
- Features
- Tech stack
- Quick links
- Requirements
- Installation
- Project layout
- Development workflow
- Commands
- Customize
- Deployment
- Testing
- Troubleshooting
- Contributing
- Code of conduct
- License
- Authors

Features
- Server-driven Vue single-page apps using Inertia.
- TypeScript on the frontend and backend-friendly types.
- Tailwind CSS ready with a base config.
- Vite for fast HMR and small bundles.
- Example pages and basic layout components.
- No built-in auth so you can plug your preferred solution.

Tech stack
- Laravel (backend routing, controllers)
- Inertia.js (bridge between Laravel and Vue)
- Vue 3 (composition API)
- TypeScript (frontend types)
- Tailwind CSS (utility-first styling)
- Vite (dev server and bundler)
- Composer and npm/yarn (package managers)

Quick links
- Releases (download and run release files): https://github.com/agusMorales/blank-vue-starter-kit/releases
- Laravel docs: https://laravel.com/docs/starter-kits
- Inertia docs: https://inertiajs.com
- Tailwind docs: https://tailwindcss.com/docs

Requirements
- PHP 8.1 or newer
- Composer 2.x
- Node.js 16.x or newer
- npm or yarn
- A database server (SQLite, MySQL, PostgreSQL) if you use migrations

Installation

1) Clone the repo
git clone https://github.com/agusMorales/blank-vue-starter-kit.git
cd blank-vue-starter-kit

2) Install backend dependencies
composer install

3) Install frontend dependencies
npm install
# or
yarn

4) Environment
cp .env.example .env
php artisan key:generate
Edit .env for DB and app config.

5) Build assets and run dev
npm run dev
# or
yarn dev

6) Migrate database
php artisan migrate

7) Open app
Visit http://localhost:8000 after starting the dev server
php artisan serve

If you downloaded a packaged release from the Releases page, extract the archive and run the included install script or follow the bundled README inside the release. The release file requires execution to set up compiled assets and dependencies.

Project layout
- app/ — Laravel app code (models, controllers, policies)
- resources/js/ — Vue frontend entry, pages, components
- resources/css/ — Tailwind entry and styles
- routes/ — Laravel routes (web.php)
- database/ — migrations and factories
- vite.config.ts — Vite config for dev and build
- tailwind.config.js — Tailwind config
- tsconfig.json — TypeScript config
- package.json — frontend scripts and deps
- composer.json — PHP deps

Development workflow
- Use Laravel controllers to return Inertia responses.
- Keep page components in resources/js/Pages.
- Reuse layout components in resources/js/Layouts.
- Use props to pass server data to pages.
- Keep API logic in controllers or API routes and use Inertia only for page responses.
- Use Vite for dev HMR and fast builds in production.

Common commands
- Start Laravel dev server
php artisan serve

- Vite dev server
npm run dev
yarn dev

- Build production assets
npm run build
yarn build

- Run tests (PHP)
php artisan test

- Run backend migrations
php artisan migrate

- Install composer deps
composer install

Customize
- Add auth: choose Laravel Breeze, Fortify, or a custom solution. This starter does not include auth to keep the code simple.
- Tailwind: adjust tailwind.config.js to add color palettes, plugins, and utilities.
- TypeScript: update tsconfig.json to enforce stricter rules or relaxed types.
- Components: add shared UI components to resources/js/Components.
- API: add API routes in routes/api.php and create controllers in app/Http/Controllers/API.

Deployment
- Build assets
npm run build

- Configure your web server to point to the Laravel public directory.

- Environment
Set APP_ENV=production and APP_DEBUG=false in .env. Set database and cache credentials.

- Queue and scheduler
Use a process manager (supervisord, systemd) to run queue workers and cron for schedule:run.

- Common hosts
You can deploy to Forge, Vapor, DigitalOcean, Hetzner, or any host that supports PHP and a Node build step.

Testing
- Unit tests (PHP): php artisan test
- Browser / E2E: connect Playwright or Cypress to the dev server and test UI flows.
- Linting
  - ESLint or custom linter for TypeScript
  - phpstan or pest for PHP static analysis

Troubleshooting
- Asset mismatch after deploy
  - Run npm run build on the server or CI and clear caches.
  - php artisan view:clear
  - php artisan config:clear
  - php artisan route:clear
  - php artisan cache:clear

- Inertia page not updating
  - Confirm Vite HMR runs in dev.
  - Ensure Inertia visits use server-side Inertia responses.

- Type errors
  - Check tsconfig paths and imports.
  - Use type guards where server data can vary.

Contributing
- Follow the Laravel contribution guide: https://laravel.com/docs/contributions
- Open issues for bugs and feature requests.
- Create pull requests with clear descriptions and tests or screenshots.
- Keep changes focused and split large work into small PRs.

Code of conduct
- Follow the Laravel community code of conduct: https://laravel.com/docs/contributions#code-of-conduct
- Be respectful and constructive in issues and PRs.

Releases and installable packages
- Visit the Releases page to download packaged builds and scripts:
https://github.com/agusMorales/blank-vue-starter-kit/releases
- Download the release archive or installer and execute the included script to install a pre-built version of this starter kit. The release artifacts may include a compressed project archive and post-install scripts that set up dependencies and compiled assets.

License
This project uses the MIT License. See LICENSE file for details.

Authors
- Original starter: Adapted and maintained by the community
- Repository owner: Agus Morales

Assets and acknowledgements
- Laravel (logo and docs): https://laravel.com
- Vue (logo and docs): https://vuejs.org
- Inertia: https://inertiajs.com
- Tailwind CSS: https://tailwindcss.com

Reach the Releases page again for packaged downloads and installers:
[Get releases and install](https://github.com/agusMorales/blank-vue-starter-kit/releases)