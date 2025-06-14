# Vue 3 + TypeScript + Vite

This template should help get you started developing with Vue 3 and TypeScript in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

Learn more about the recommended Project Setup and IDE Support in the [Vue Docs TypeScript Guide](https://vuejs.org/guide/typescript/overview.html#project-setup).


# How to Run This Project

## Prerequisites

- [Node.js](https://nodejs.org/) installed (version X.X.X or higher)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/) installed

## Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. Install dependencies:
   ```sh
   npm install
   ```

## Running the Project

To start the development server, run:
```sh
npm run dev
```


## Vite + Vue + TypeScript Setup

Follow these steps to create a new Vite project with Vue and TypeScript:

1. Create a new Vite project:
   ```sh
   npm create vite@latest
   ```
2. When prompted:
   - Enter your project name.
   - Select **Vue** as the framework.
   - Select **TypeScript** as the variant.

3. Navigate to your project directory:
   ```sh
   cd your-project-name
   ```

4. Install dependencies and start the development server:
   ```sh
   npm install
   npm run dev
   ```

The development server will start, and you can view your app in the browser (usually at [http://localhost:5173](http://localhost:5173)).



## Tailwind CSS Setup in Vite + Vue

Follow these steps to set up Tailwind CSS in your Vite + Vue project.  
For more details, see the [official Tailwind CSS Vite guide](https://tailwindcss.com/docs/installation/using-vite).

1. **Install Tailwind CSS and the Vite plugin:**
   ```sh
   npm install tailwindcss @tailwindcss/vite
   ```

2. **Add Tailwind CSS plugin to your `vite.config.ts`:**
   ```ts
   // vite.config.ts
   import { defineConfig } from 'vite'
   import vue from '@vitejs/plugin-vue'
   import tailwindcss from '@tailwindcss/vite'

   export default defineConfig({
     plugins: [vue(), tailwindcss()]
   })
   ```

3. **Import Tailwind CSS in your main stylesheet (e.g., `style.css`):**
   ```css
   /* style.css */
   @import "tailwindcss";
   ```

4. **Test your setup and start the development server:**
   ```sh
   npm run dev
   ```

You should now be able to use Tailwind CSS utility classes in your