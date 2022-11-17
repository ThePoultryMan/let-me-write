<template>
  <div>
    <div class="flex justify-center px-16">
      <button
      class="bg-gray-200 w-6 rounded-lg"
      @click="editor.chain().focus().toggleBold().run()"
      >B</button>
    </div>
    <editor-content :editor="editor" />
  </div>
</template>

<script>
import { Editor, EditorContent } from "@tiptap/vue-3";
import StarterKit from "@tiptap/starter-kit"; // eslint-disable-line

export default {
  components: {
    EditorContent
  },

  data() {
    return {
      editor: null,
    }
  },

  mounted() {
    this.editor = new Editor({
      extensions: [
        StarterKit,
      ],
    })
  },

  beforeUnmount() {
    this.editor.destroy();
  },
}
</script>

<style>
/* stylelint-disable */
.ProseMirror {
  border: none;
  outline: none;
}
/* styleling-enable */
</style>
