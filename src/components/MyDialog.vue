<template>
<v-card>
  <v-card-text>
  This is my Dialog
  <div>  value: {{value }} </div>
  <div>  computed: {{computedValue}} </div>
  <div>  watched: {{watchedResult}} </div>
  </v-card-text>
  <v-card-actions>
  <v-btn @click="$emit('close')">Close</v-btn>
  </v-card-actions>
</v-card>
</template>

<script>
export default {
  name: "MyDialog",
  props: {
    value: {
      type: String,
    }
  },
  data: () => ({
    watchedResult:''
  }),
  watch:{
    value( val){
      console.log('value has changed '+val)
      this.watchedResult=val
    }
  },
  computed:{
    computedValue(){
      return "computed" + this.value
    }
  }
}
</script>

<style scoped>

</style>