<template>
  <div>
    <p> {{ name }}
      <br>
      {{ age }}

      <br>
      <span> this is from ref to show how to use the generics with ref

      {{ageWithRef}}
      </span>
    </p>
  </div>
</template>

<script lang="ts">
import {defineComponent, reactive, ref, toRefs} from 'vue';


export default defineComponent({
  name: 'App',
  components: {},
  setup() {
    const state = reactive({
      name: 'link',
      age: 23 as string | number

    })

    //  this is the same like above but here we use the ref from vue

    const ageWithRef = ref<string | number>(24)
    return {...toRefs(state),ageWithRef}
  }

});
</script>

<style>

</style>
