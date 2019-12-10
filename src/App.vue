<template>
  <div id="app">
    <vue-editor
      :editorOptions="editorSettings"
      v-model="content">
    </vue-editor>
  </div>
</template>

<script>
  import { VueEditor, Quill } from 'vue2-editor'
  import { ImageDrop } from 'quill-image-drop-module'
  import ImageResize from 'quill-image-resize-vue'
  import QuillBetterTable from 'quill-better-table'
  //import quillTable from 'quill-table-module'

 /* Quill.register(quillTable.TableCell);
  Quill.register(quillTable.TableRow);
  Quill.register(quillTable.Table);
  Quill.register(quillTable.Contain);
  Quill.register('modules/table', quillTable.TableModule);*/

//  Quill.register({
//    'modules/better-table': QuillBetterTable
// }, true)
  Quill.register('modules/betterTable', QuillBetterTable)
  Quill.register('modules/imageDrop', ImageDrop)
  Quill.register('modules/imageResize', ImageResize)

  export default {
    components: {
      VueEditor
    },
    data() {
      return {
        content: '<h1>Initial Content</h1>',
        editorSettings: {
          modules: {
            imageDrop: true,
            imageResize: {},
            betterTable: true
          }
        }
      }
    }
  }
</script>
