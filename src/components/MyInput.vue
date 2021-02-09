<template>
  <div>
    <label>
      <input type="text" @input="oninput" :value="b">
    </label>
  </div>
</template>

<script>
export default {
  name: "MyInput",
  props:['b'],
  methods:{
    oninput(e){
      this.$emit('c',e)
    }
  }
}
</script>

<style scoped>

</style>