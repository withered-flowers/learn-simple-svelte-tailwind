# Svelte Simple Apps with Tailwindcss

## Demo [NOT DEPLOYED YET]
https://simple-svelte-tailwind.web.app/

## Short Documentation 

Disclaimer:
- This documentation is using `pnpm`
- This code is using Vue v3 with Composition API (not Options API)

## Initialize Apps
1. `pnpm create vite`
1. name your project
1. select Framework: `vue`, 
1. select a variant: `vue`
1. `cd path/to/project/folder`
1. `pnpm install`
1. delete `src/assets/svelte.png`, `src/lib/Counter.svelte`
1. `pnpm install -D tailwindcss postcss autoprefixer`
1. `pnpm exec tailwindcss init -p`
1. rename `postcss.config.js` to `postcss.config.cjs`
1. rename `tailwind.config.js` to `tailwind.config.cjs`
1. edit `tailwind.config.cjs`
    ```js
    module.exports = {
      content: ["./index.html", "./src/**/*.{vue,js,ts,jsx,tsx,svelte,md,mdx}"],
      theme: {
        extend: {},
      },
      plugins: [],
    };
    ```
1. create file `src/index.css`
1. edit `index.css`
    ```css
    @tailwind base;
    @tailwind components;
    @tailwind utilities;

    .custom-container {
      @apply container p-4 min-w-full min-h-screen flex flex-col items-center justify-center text-center;
    }

    .custom-subcontainer {
      @apply flex flex-row justify-center items-center;
    }

    .h1 {
      @apply text-4xl font-medium mb-4;
    }

    .h2 {
      @apply text-2xl font-medium mb-4;
    }

    .btn {
      @apply px-4 py-2 my-2 bg-sky-300 hover:bg-sky-600 text-slate-700 hover:text-slate-300 font-bold rounded-3xl w-48;
    }

    .form-input {
      @apply px-4 py-2 my-2 bg-white border border-gray-300 rounded-3xl w-full;
    }

    table {
      @apply table-auto border border-collapse border-slate-500;
    }

    td,
    th {
      @apply border border-slate-500 p-2;
    }
    ```
1. edit `main.js`
    ```js
    import App from "./App.svelte";
    import "./index.css";

    const app = new App({
      target: document.getElementById("app"),
    });

    export default app;
    ```
1. edit `App.vue`
    ```html
    <script setup>
    // This starter template is using Vue 3 <script setup> SFCs
    // Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
    </script>

    <template>
      <div class="custom-container bg-slate-200">
        <p class="h1">Simple Vue Apps with Tailwind</p>
      </div>
    </template>

    <style></style>
    ```
1. run the app `pnpm run dev`

## FirstComponent


## SecondComponent


## ThirdComponent
