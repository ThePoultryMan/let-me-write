<template>
  <editor-content :editor="editor" />
</template>

<script>
import { Editor, EditorContent } from "@tiptap/vue-2";
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

  beforeDestroy() {
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
