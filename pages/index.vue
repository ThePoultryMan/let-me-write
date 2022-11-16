<template>
  <div>
    <textarea />
    <hr class="mx-[448px] mt-16" />
    <div class="mx-72 mt-2">
      <client-only>
        <TipTapField />
      </client-only>
    </div>
  </div>
</template>

<script>
export default {
  name: "LetMeWrite",
  head: {
    title: "Let Me Write"
  }
}
</script>
