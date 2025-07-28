### 📂 when the folder react-seed exists

```bash
npx create-nx-workspace@latest . \
  --preset=react \
  --bundler=vite \
  --appName=react-app \
  --style=css \
  --nxCloud=false
```

- Install Tailwind:

  ```bash
  npm install -D tailwindcss postcss autoprefixer
  npx tailwindcss init -p
  ```

- Edit `tailwind.config.js`:

  ```js
  /** @type {import('tailwindcss').Config} */
  module.exports = {
    content: [
      './apps/**/*.{js,ts,jsx,tsx}',
      './libs/**/*.{js,ts,jsx,tsx}',
    ],
    theme: {
      extend: {},
    },
    plugins: [],
  }
  ```

- Update `app.css`:

  ```css
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  ```

- Install Signals:

  ```bash
  npm install @preact/signals-react
  ```

- Add new app or lib:

  ```bash
  nx g @nx/react:app new-app --bundler=vite
  nx g @nx/react:lib ui-lib
  ```
