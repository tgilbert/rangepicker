<template>
  <div id="app">
    {{ ranges }}
    <button @click="pickerShow">Afficher le calendrier</button>
    <div v-if="isPickerVisible" style="position: static;top: 0;left: 0;right: 0;bottom: 0;overflow: scroll;">
      <range-picker :year="2018" v-model="ranges" @cancel="pickerHide" @submit="pickerHide"/>
    </div>
  </div>
</template>

<script>

import RangePicker from './components/RangePicker'

export default {
  name: 'App',
  data () {
    return {
      isPickerVisible: false,
      ranges: [ [ 1520636400, 1525880015 ], [ 1543100400, 1545064415 ] ]
    }
  },
  components: {
    RangePicker
  },
  methods: {
    pickerShow () {
      this.isPickerVisible = true
    },
    pickerHide () {
      this.isPickerVisible = false
    }
  }
}
</script>
