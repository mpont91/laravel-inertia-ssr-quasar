## Laravel + inertia SSR + Quasar

This repository is a boilerplate for a Laravel + inertia SSR + Quasar project.

Unfortunately, it's not working as SSR.

### Requisistes
* Docker, at least, all the documentation was made with docker in mind.

### Installation

Install PHP dependencies
```bash
composer install
```

Copy .env.example to .env
```bash
cp .env.example .env
```

Generate Laravel key
```bash
php artisan key:generate
```

Install JS dependencies
```bash
npm install
```

### Run Laravel backend
```bash
./vendor/bin/sail up -d
```

### Run in development mode
```bash
npm run dev
```

**Enter to localhost with your browser and application will work**

### Run in production with SSR mode
Build for production
```bash
npm run build
```

Run the application in SSR mode
```bash
./vendor/bin/sail node bootstrap/ssr/ssr.mjs
```

**Unfortunately, this mode won't work, showing this error:**

```
(node:24) Warning: To load an ES module, set "type": "module" in the package.json or use the .mjs extension.
(Use `node --trace-warnings ...` to show where the warning was created)
/var/www/html/node_modules/quasar/src/vue-plugin.js:1
import installQuasar from './install-quasar.js'
^^^^^^

SyntaxError: Cannot use import statement outside a module
    at Object.compileFunction (node:vm:360:18)
    at wrapSafe (node:internal/modules/cjs/loader:1055:15)
    at Module._compile (node:internal/modules/cjs/loader:1090:27)
    at Object.Module._extensions..js (node:internal/modules/cjs/loader:1180:10)
    at Module.load (node:internal/modules/cjs/loader:1004:32)
    at Function.Module._load (node:internal/modules/cjs/loader:839:12)
    at ModuleWrap.<anonymous> (node:internal/modules/esm/translators:170:29)
    at ModuleJob.run (node:internal/modules/esm/module_job:193:25)
    at async Promise.all (index 0)
    at async ESMLoader.import (node:internal/modules/esm/loader:533:24)
```

