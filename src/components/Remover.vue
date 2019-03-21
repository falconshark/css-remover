<template>
<div class="remover">
  <div class="form-group">
    <label for="code">HTML Code:</label>
    <textarea class="form-control" id="code" v-model="code" rows="7" />
  </div>
  <div class="form-group">
    <button class="btn btn-primary" v-on:click="startRemover">Start! </button>
  </div>
  <div class="form-group">
    <label for="output">Output:</label>
    <textarea class="form-control" id="output" rows="7" readonly="readonly" v-model="output"/>
  </div>
</div>
</template>
<script>
export default {
  name: 'Remover',
  methods: {
    startRemover(){
      const code = this.code;
      const regax = /class[ \t]*=[ \t]*"[^"]+"/g;
      regax.match
      this.output = code.replace(regax, '');
    }
  },
  data () {
    return {
      code: '',
      output: '',
    }
  },
}
</script>

<style lang="scss" scoped>
.form-group{
  margin-bottom: 2em;
}
#code{
  max-width: 50%;
  margin-left: auto;
  margin-right: auto;
}
#output{
  background-color: white;
  max-width: 50%;
  margin-left: auto;
  margin-right: auto;
}
</style>
