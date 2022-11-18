<template>
  <header class="flex justify-start relative py-0.5 pl-4 gap-x-4 bg-gray-300">
    <NuxtLink to="/"><h1 class="text-lg">let me write</h1></NuxtLink>
    <div class="w-px h-6 mt-0.5 bg-gray-400" />
    <button @click="active = !active">preferences</button>
    <div 
    v-show="active"
    class="pref-menu border-solid border border-gray-800"
    >
      <h3>preferences</h3>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      active: false,
    }
  },
}
</script>

<style>
.pref-menu {
  position: absolute;
  left: 142px;
  top: 24px;
}
</style>
