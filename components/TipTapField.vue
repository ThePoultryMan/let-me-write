<template>
  <div>
    <div class="flex justify-center text-center">
      <button
        class="bg-gray-200 w-6 rounded-l-lg"
        :class="{ 'font-bold': isActive('bold') }"
        @click="editor.chain().focus().toggleBold().run()"
      >B</button>
      <button
        class="bg-gray-200 w-6"
        :class="{ 'italic': isActive('italic') }"
        @click="editor.chain().focus().toggleItalic().run()"
      >I</button>
      <button
        class="bg-gray-200 w-6"
        :class="{ 'underline': isActive('underline') }"
        @click="editor.chain().focus().toggleUnderline().run()"
      >U</button>
      <button
        class="bg-gray-200 w-6 rounded-r-lg"
        :class="{ 'line-through': isActive('strike') }"
        @click="editor.chain().focus().toggleStrike().run()"
      >S</button>
    </div>
    <editor-content :editor="editor" />
  </div>
</template>

<script>
import { Editor, EditorContent } from "@tiptap/vue-3";
import StarterKit from "@tiptap/starter-kit"; // eslint-disable-line
import Underline from "@tiptap/extension-underline"

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
        Underline,
      ],
    })
  },

  beforeUnmount() {
    this.editor.destroy();
  },

  methods: {
    isActive: function(type) {
      if(this.editor != null) {
        return this.editor.isActive(type);
      } else {
        return false;
      }
    }
  }
}
</script>

<style>
/* stylelint-disable */
.ProseMirror {
  border: none;
  outline: none;
}
/* stylelint-enable */
</style>
