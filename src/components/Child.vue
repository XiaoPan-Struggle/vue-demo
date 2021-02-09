<template>
  <div class="child">
    {{high}}
    <button @click="$emit('update:high',high+1)"> + 1 </button>
  </div>
</template>

<script>
export default {
  name:"Child",
  props:["high"]
};
</script>


<style>
.child{
  border: 1px solid green;
}
</style>