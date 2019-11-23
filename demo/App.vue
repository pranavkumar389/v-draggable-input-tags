<template>
  <div id="app">
    <v-draggable-input-tags
      v-model="tag"
      :tags="tags"
      :tags-filte-duplicates="false"
      @tags-changed="newTags => tags = newTags"
      :isDraggable="true"
      placeholder="Add new option"
      :allowEditTags="true">
      <div slot="tag-actions" class="ti-actions" slot-scope="props">
        <i class="fa fa-close"
          v-show="!props.edit"
          @click="props.performDelete(props.index);">
        </i>
        <i class="fa fa-undo"
          v-show="props.edit"
          @click="props.cancelEdit(props.index);">
        </i>
      </div>
      </v-draggable-input-tags>
  </div>
</template>

<script>
import VDraggableInputTags from '../src/v-draggable-input-tags.vue'

export default {
  name: 'app',
  components: {
    VDraggableInputTags
  },
  data: () => {
    return {
      tag: '',
      tags: []
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
