# Nuxt3

[B站视频](https://www.bilibili.com/video/BV1714y1v7of)

[源码 github](https://github.com/insidewebdev/twitter-clone)

![](https://kingan-md-img.oss-cn-guangzhou.aliyuncs.com/blog/20230520163939.png)

```bash
npx nuxi init nuxt-teitter-clone
cd nuxt-teitter-clone
pnpm i
```

```bash
git config --local user.email "1017386624@qq.com"
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

## 暗黑模式

暗黑模式切换逻辑写在最外层入口文件

👇 `App.vue`
```vue
<template>
  <div :class="{ 'dark': isDark }">{{ isDark }}</div>
</template>

<script setup>
const isDark = ref(true) // ✨ 自动import ref
</script>
```
`ref()` 来自 `vue`，由 `vite Plugin` 编译时自动补充了这段语句 `import { ref } from 'vue'`

与 tailwindcss 结合演示

## 布局

### 左布局

根据窗口大小 决定宽度



新建组件
`components/Sidebar/Left.vue`
```vue
<template>
  <div>Left</div>
</template>
```
`App.vue`
```vue
<template>
  <div class="min-h-full" :class="{ 'dark': isDark }">
    <div class="grid grid-cols-12 bg-slate-400 mx-auto sm:px-6 lg:px-8 lg:max-w-7xl lg:gap-5">
      <div class="hidden bg-red-500 md:block">
        <!-- ✨ 自动 import 约定式命名目录名文件名 驼峰 -->
        <SidebarLeft />
      </div>
      <div>main</div>
      <div>right</div>
    </div>
  </div>
</template>

<script setup>
const isDark = ref(true)
</script>
```
同理 组件也是由 `vite Plugin` 编译时自动补充了 `import` 语句

并且 `Nuxt` 利用约定式目录，实现组件命名为 `目录名文件名` 驼峰

创建logo组件
![](https://kingan-md-img.oss-cn-guangzhou.aliyuncs.com/blog/20230520175737.png)

组件中使用 `components/Sidebar/Left.vue`
```vue
<template>
  <div>
    <LogoTwitter />
  </div>
</template>
```
效果
![](https://kingan-md-img.oss-cn-guangzhou.aliyuncs.com/blog/20230520175806.png)
