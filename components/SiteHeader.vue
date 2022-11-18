<template>
  <header class="flex justify-start relative py-0.5 pl-4 gap-x-4 bg-gray-300">
    <NuxtLink to="/"><h1 class="text-lg">let me write</h1></NuxtLink>
    <div class="w-px h-6 mt-0.5 bg-gray-400" />
    <button @click="active = !active">preferences</button>
    <Transition name="slide-down">
      <div
        v-show="active"
        class="pref-menu border-solid border border-t-0 border-gray-800 rounded-b-md w-36 -z-10"
      >
        <div></div>
      </div>
    </Transition>
  </header>
</template>

<script>
export default {
  data() {
    return {
      active: false,
    };
  },
};
</script>

<style>
.pref-menu {
  position: absolute;
  left: 132px;
  top: 32px;
}

@keyframes slide-down {
  0% {
    top: 0px;
  }
  100% {
    top: 32px;
  }
}

.slide-down-enter-active {
  animation: slide-down 0.25s;
}

.slide-down-leave-active {
  animation: slide-down 0.25s reverse;
}
</style>
