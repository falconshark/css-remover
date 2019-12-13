<template>
<div class="remover">
  <div class="form-group type">
    <label for="type">Type:</label>
    <select v-model="type">
      <option value="class">Class</option>
      <option value="style">Style</option>
    </select>
  </div>
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
      if(this.type === 'class'){
        const regax = /class[ \t]*=[ \t]*"[^"]+"/g;
        this.output = code.replace(regax, '');
      }else{
        const regax = /style[ \t]*=[ \t]*"[^"]+"/g;
        this.output = code.replace(regax, '');
      }
    }
  },
  data () {
    return {
      type: 'class',
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
.type label{
  margin-right: 1em;
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
