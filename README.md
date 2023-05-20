# Nuxt3

[B站视频](https://www.bilibili.com/video/BV1714y1v7of)

[源码 github](https://github.com/insidewebdev/twitter-clone)

```bash
npx nuxi init nuxt-teitter-clone
cd nuxt-teitter-clone
pnpm i
```

![](https://kingan-md-img.oss-cn-guangzhou.aliyuncs.com/blog/20230520161043.png)

🤔 `.npmrc` 用于 `pnpm环境`，是做什么的？

🤔 内置配置(`Vite`)收拢到 `.nuxt` 的架构方式(`Umi等`)优点和原理？

![](https://kingan-md-img.oss-cn-guangzhou.aliyuncs.com/blog/20230520160732.png)

## 初始化 tailwindcss 环境

[@nuxtjs/tailwindcss 官方文档](https://nuxt.com/modules/tailwindcss)

```bash
pnpm add -D @nuxtjs/tailwindcss
```

👇 `nuxt.config.ts`
```js
// https://nuxt.com/docs/api/configuration/nuxt-config
export default defineNuxtConfig({
  modules: [
    '@nuxtjs/tailwindcss'
  ]
})
```
```bash
npx tailwindcss init
```

👇 `tailwind.config.js`
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