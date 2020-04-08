<template>
  <div style="height: 500px; width: 500px; border: 1px solid red; position: relative;">
    <vue-draggable-resizable :w="100" :h="100" :x="10" :y="10" @dragging="onDrag" @resizing="onResize" :parent="true">
      <h3>1</h3><br>     
    </vue-draggable-resizable>
    <vue-draggable-resizable :w="100" :h="100"  :x="120" :y="10" @dragging="onDrag" @resizing="onResize" :parent="true" class-name-resizable="my-resizable-class">
      <h3>2</h3><br>
    </vue-draggable-resizable>
    <vue-draggable-resizable :w="100" :h="100"  :x="240" :y="10" @dragging="onDrag" @resizing="onResize" :parent="true">
      <h3>3</h3><br>
    </vue-draggable-resizable>
  </div>
</template>

<script>
import Vue from 'vue'
import VueDraggableResizable from 'vue-draggable-resizable'

// optionally import default styles
import 'vue-draggable-resizable/dist/VueDraggableResizable.css'

Vue.component('vue-draggable-resizable', VueDraggableResizable)


export default {
  data: function () {
    return {
      width: 0,
      height: 0,
      x: 0,
      y: 0
    }
  },
  methods: {
    onResize: function (x, y, width, height) {
      this.x = x
      this.y = y
      this.width = width
      this.height = height
    },
    onDrag: function (x, y) {
      this.x = x
      this.y = y
    }
  }
}
// <span>X: {{ x }} / Y: {{ y }} - Width: {{ width }} / Height: {{ height }}</span>
</script>