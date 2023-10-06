<template>
  <div>
    <ModelListValueAndTextExample />
    <ModelListStringOptionExample />
    <ModelListNumberOptionExample />
    <ModelListCustomSlotsExample />
  </div>
</template>

<script>
import { ModelListSelect } from "vue-search-select"
import ModelListValueAndTextExample from './_ModelListValueAndText.vue'
import ModelListStringOptionExample from './_ModelListStringOption.vue'
import ModelListNumberOptionExample from './_ModelListNumberOption.vue'
import ModelListCustomSlotsExample from "./_ModelListCustomSlots.vue"

export default {
  data() {
    return {
      
      
      
    }
  },
  methods: {
    
    /* sample 3 */
    
  },
  components: {
    ModelListSelect,
    ModelListValueAndTextExample,
    ModelListStringOptionExample,
    ModelListNumberOptionExample,
    ModelListCustomSlotsExample
},
}
</script>
