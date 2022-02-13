# Svelte Simple Apps with Tailwindcss

## Demo [NOT DEPLOYED YET]
https://simple-svelte-tailwind.web.app/

## Short Documentation 

Disclaimer:
- This documentation is using `pnpm`

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
    <script>
    </script>

    <div class="custom-container bg-slate-200">
      <p class="h1">Simple Svelte Apps with Tailwind</p>
    </div>

    <style></style>

    ```
1. run the app `pnpm run dev`

## FirstComponent
1. create file `src/lib/FirstComponent.svelte`
1. edit `FirstComponent.svelte`
    ```html
    <script>
      // every value declare will be reactive in svelte
      // svelte reactivity is by assignments
      let count = 0;

      // method for set count state
      const addCount = () => {
        count++;
      };

      // method for reset count state
      const resetCount = () => {
        count = 0;
      };
    </script>

    <div>
      <h2 class="h2">First Component</h2>
      <h3>
        <!-- conditional rendering -->
        {#if count === 0}
          Don't you dare to click me !
        {:else}
          How dare you click me {count} time{count > 1 ? "s" : ""}
        {/if}
      </h3>
      <p>
        <!-- bind event on click with addCount -->
        <button class="btn" on:click={addCount}>Dare-to-click</button>
      </p>
      <p>
        <!-- bind event on click with resetCount -->
        <button class="btn" on:click={resetCount}>Forget-me-not</button>
      </p>
    </div>
    ```
1. edit `App.svelte`
    ```html
    <script>
      // import the component here
      import FirstComponent from "./lib/FirstComponent.svelte";
    </script>

    <div class="custom-container bg-slate-200">
      <p class="h1">Simple Svelte Apps with Tailwind</p>
      <!-- Create new section to hold FirstComponent -->
      <section>
        <FirstComponent />
      </section>
    </div>

    <style></style>
    ```

## SecondComponent
1. create file `src/lib/SecondComponent.svelte`
1. create file `src/lib/SecondComponentSubContent.svelte`
1. edit file `SecondComponentSubContent.svelte`
    ```html
    <script>
      // get a props from parent component named 'textInput'
      // via export keywords
      export let textInput;
    </script>

    <div>
      {#if textInput === ""}
        <pre>I have nothing to show</pre>
      {:else}
        <pre>I write: {textInput}</pre>
      {/if}
    </div>

    <style></style>
    ```
1. edit file `SecondComponent.svelte`
    ```html
    <script>
      // We will create a child component to hold the content
      import SecondComponentSubContent from "./SecondComponentSubContent.svelte";

      // state for the text
      let textInput = "";
    </script>

    <div>
      <h2 class="h2">Second Component</h2>
      <div class="custom-subcontainer">
        <!-- Form Section -->
        <section class="mr-4">
          <form>
            <!-- Two way data binding automatically using bind:value -->
            <input
              class="form-input"
              type="text"
              placeholder="Write me pl0x"
              bind:value={textInput}
            />
          </form>
        </section>
        <section>
          <!-- Content section  -->

          <!-- pass textInput to SecondComponentSubContent -->
          <SecondComponentSubContent {textInput} />
        </section>
      </div>
    </div>

    <style></style>
    ```
1. edit `App.svelte`
    ```html
    <script>
      // import the component here
      import FirstComponent from "./lib/FirstComponent.svelte";
      // import the second component here
      import SecondComponent from "./lib/SecondComponent.svelte";
    </script>

    <div class="custom-container bg-slate-200">
      <p class="h1">Simple Svelte Apps with Tailwind</p>
      <!-- Create new section to hold FirstComponent -->
      <section>
        <FirstComponent />
      </section>
      <!-- Create new section to hold SecondComponent -->
      <section>
        <SecondComponent />
      </section>
    </div>

    <style></style>
    ```


## ThirdComponent
