# 🚀 React Seed Monorepo

A modern **React monorepo** setup using **Turborepo**, supporting:

- ✅ Next.js 15 (`main-app`)
- ✅ Tailwind CSS 4
- ✅ SCSS/SASS styling
- ✅ TypeScript
- ✅ Shared libraries (`common-lib`)
- ✅ Monorepo tooling with `turbo`

---

## 📁 Project Structure

```
react-seed/
├── apps/
│   └── main-app/         # Next.js 15 + Tailwind + SCSS
├── libs/
│   └── common-lib/       # Reusable components + Tailwind
├── package.json          # Root monorepo config
├── turbo.json            # Turborepo pipeline
└── README.md
```

---

## 📦 Installation (Step-by-step)

### 1. Clone the repository

```bash
git clone https://github.com/lkovari/react-seed.git
cd react-seed
```

### 2. Install Node.js and npm if needed

```bash
# macOS (Homebrew)
brew install node

# Debian/Ubuntu
sudo apt install nodejs npm
```

Minimum required:

- Node.js `>= 20`
- npm `>= 10`

Verify installation:

```bash
node -v
npm -v
```

### 3. Install all monorepo dependencies

```bash
npm install
```

This automatically installs:

- all dependencies in `apps/main-app`
- all dependencies in `libs/common-lib`

---

## 🧪 Development

Run the dev server:

```bash
npm run dev
```

This will run:

```bash
turbo run dev
```

Which starts `main-app` in dev mode using `--turbopack`.

---

## 🏗️ Build

Build all apps and libs:

```bash
npm run build
```

Build individual app or lib:

```bash
cd apps/main-app
npm run build

# or

cd libs/common-lib
npm run build
```

---

## 🔍 Linting

```bash
npm run lint
```

This runs `turbo run lint` across the workspace.

---

## 🧹 Formatting

Format code using Prettier:

```bash
npm run format
```

---

## 🎨 Tailwind + SCSS Setup

Both `main-app` and `common-lib` use Tailwind CSS and Sass.

### Required files and setup:

#### 1. `tailwind.config.js`

Place this file in both:

- `apps/main-app/tailwind.config.js`
- `libs/common-lib/tailwind.config.js`

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./src/**/*.{js,ts,jsx,tsx}'],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

#### 2. `postcss.config.js`

Place this file in both:

```js
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};
```

#### 3. Global SCSS file

Example `libs/styles/globals.scss`:

```scss
@tailwind base;
@tailwind components;
@tailwind utilities;

/* Custom styles here */
```

Import it in your layout:

```tsx
import '../styles/globals.scss';
```

#### 4. TypeScript config (`tsconfig.json`)

Example for `apps/main-app/tsconfig.json`:

```json
{
  "compilerOptions": {
    "target": "ES2022",
    "module": "ESNext",
    "lib": ["DOM", "ES2022"],
    "jsx": "react-jsx",
    "moduleResolution": "bundler",
    "esModuleInterop": true,
    "strict": true,
    "skipLibCheck": true,
    "baseUrl": "./src"
  },
  "include": ["src"]
}
```

---

## 📚 Tech Stack

| Tool         | Version |
| ------------ | ------- |
| React        | 19.1.0  |
| Next.js      | 15.4.4  |
| TypeScript   | ^5      |
| Sass / SCSS  | ^1.89.2 |
| Tailwind CSS | ^4.1.11 |
| TurboRepo    | ^2.5.5  |
| Node.js      | >= 20   |
| npm          | >= 10   |
