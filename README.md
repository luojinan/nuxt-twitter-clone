
npx nuxi init nuxt-teitter-clone

pnpm add -D @nuxtjs/tailwindcss

[官方文档](https://nuxt.com/modules/tailwindcss)

nuxt.config.ts
```js
// https://nuxt.com/docs/api/configuration/nuxt-config
export default defineNuxtConfig({
  modules: [
    '@nuxtjs/tailwindcss'
  ]
})
```

npx tailwindcss init

tailwind.config.js
```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [],
  theme: {
    extend: {},
  },
  plugins: [],
}
```