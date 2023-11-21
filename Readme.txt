******
Here is the full tutorial of this project
https://www.youtube.com/watch?v=_W3R2VwRyF4
******

Installations
 <------------------------>
 1. Create a new vite app by 
 npm create vite@latest ./

  2. Install Tailwind Css by 
  npm install -D tailwindcss postcss autoprefixer
  and then initialize it by
  npx tailwindcss init -p

  3.In tailwind.config.js file edit all with 
  ((((
  /** @type {import('tailwindcss').Config} */
const defaultTheme = require("tailwindcss/defaultTheme");

module.exports = {
  darkMode: ["class"],
  content: [
    "./pages/**/*.{ts,tsx}",
    "./components/**/*.{ts,tsx}",
    "./app/**/*.{ts,tsx}",
    "./src/**/*.{ts,tsx}",
  ],
  theme: {
    container: {
      center: true,
      padding: "2rem",
      screens: {
        "2xl": "1400px",
      },
    },
    extend: {
      colors: {
        "primary-500": "#877EFF",
        "primary-600": "#5D5FEF",
        "secondary-500": "#FFB620",
        "off-white": "#D0DFFF",
        red: "#FF5A5A",
        "dark-1": "#000000",
        "dark-2": "#09090A",
        "dark-3": "#101012",
        "dark-4": "#1F1F22",
        "light-1": "#FFFFFF",
        "light-2": "#EFEFEF",
        "light-3": "#7878A3",
        "light-4": "#5C5C7B",
      },
      screens: {
        xs: "480px",
      },
      width: {
        420: "420px",
        465: "465px",
      },
      fontFamily: {
        inter: ["Inter", "sans-serif"],
      },
      keyframes: {
        "accordion-down": {
          from: { height: 0 },
          to: { height: "var(--radix-accordion-content-height)" },
        },
        "accordion-up": {
          from: { height: "var(--radix-accordion-content-height)" },
          to: { height: 0 },
        },
      },
      animation: {
        "accordion-down": "accordion-down 0.2s ease-out",
        "accordion-up": "accordion-up 0.2s ease-out",
      },
    },
  },
  plugins: [require("tailwindcss-animate")],
};

  ))))

  4. Run the command 
  npm install tailwindcss-animate

  5. Install react-router-dom by
  npm install react-router-dom

  6. Go to ui.shadcn.com
  Paste this command in terminal 
  # (so you can import "path" without error)
npm i -D @types/node

Change the tsconfig.json file with this code

(((
{
  "compilerOptions": {
    "target": "ES2020",
    "useDefineForClassFields": true,
    "lib": ["ES2020", "DOM", "DOM.Iterable"],
    "module": "ESNext",
    "skipLibCheck": true,

    /* Bundler mode */
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": true,
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx",

    /* Linting */
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noFallthroughCasesInSwitch": true
    //Shadcn
        "baseUrl": ".",
      "paths": {
        "@/*": [
          "./src/*"
        ]
      }
    },
  "include": ["src"],
  "references": [{ "path": "./tsconfig.node.json" }]
}
)))

7. Open vite.config.ts file and replace all code with this code 
(((
import path from "path"
import react from "@vitejs/plugin-react"
import { defineConfig } from "vite"

export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
})
)))
 

 And then initialize it by this command 

 npx shadcn-ui@latest init
