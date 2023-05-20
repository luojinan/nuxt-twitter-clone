<template>
  <div class="min-h-full" :class="{ 'dark': isDark }">
    <div class="grid grid-cols-12 bg-slate-400 mx-auto sm:px-6 lg:px-8 lg:max-w-7xl lg:gap-5">
      <div class="hidden bg-red-500 md:block">
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