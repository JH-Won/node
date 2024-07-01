<template>
  <v-app>
    <v-main>
      <MonacoEditor @change="onChangeEditor" @keyup.enter="onEnter"
        theme="vs-dark"
        :options="options"
        language="python"
        :width="800"
        :height="800"
        :diffEditor="false"
        :original="original"
        v-model:value="value"
      ></MonacoEditor>
    </v-main>
  </v-app>
</template>

<script>
import MonacoEditor from 'monaco-editor-vue3'

export default {
  components: {
    MonacoEditor
  },

  data() {
    return {
      code: 'const noop = () => {}',
      value: '',
    }
  },

  methods : {
    onChangeEditor() {
      // console.log(this.value)
    },
    onEnter() {
      console.log(this.value)
    }
  },
}
</script>

<style>
.editor {
  width: 600px;
  height: 800px;
}
</style>
