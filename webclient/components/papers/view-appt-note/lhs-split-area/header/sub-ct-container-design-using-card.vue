/* Single instance component names Components that should only ever have a single active instance should begin with the
The prefix, to denote that there can be only one. Ref:
https://vuejs.org/v2/style-guide/#Single-instance-component-names-strongly-recommended */

<template>
  <div style="display: grid; grid-template-columns: repeat(9, 1fr)">
    <!-- Following el-card style is set to overflow visible and height 65px. This is because tooltip on appointment slider wasn't fully visible as el-card overflow property by default set to hidden. Also since slider is generating on the fly, it was causing malformation on mouse overing/tooltip. Hence overflow is visible and height set to 65px. -->
    <div style="grid-column: 1/10">
      <ctSlider></ctSlider>
    </div>
  </div>
</template>

<script>
// import ctSlider from './time-series-of-appointments-component-made-with-high-charts.vue'
import ctSlider from './time-series-of-appointments-component-made-with-vue-slider.vue'

import ctTogleHealthOther from './toggle-health-other-component.vue'
import ctCoding from '@/components/papers/appt-coding/dashboard.vue'

export default {
  components: { ctSlider, ctCoding },
}
</script>

<style scoped>
#TheLeftSideDisplayAreaHeader {
  height: 30px;
  margin-bottom: 6px;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
}
</style>
