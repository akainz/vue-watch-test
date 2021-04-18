<template>
  <v-container app>
    <v-btn text @click="editWithNoTick">
      Without Tick
    </v-btn>

    <v-btn  text @click="editWithTick">
      With Tick
    </v-btn>

    <v-dialog
        v-model="showDialog"
        persistent
    >
      <MyDialog  :value="dialogValue" v-on:close="showDialog=false"></MyDialog>
    </v-dialog>
  </v-container>
</template>

<script>
import MyDialog from "@/components/MyDialog";
import Vue from 'vue'

export default {
  name: 'HelloWorld',
  components:{MyDialog},
  data: () => ({
    dialogValue: '',
    showDialog: false
  }),
  methods:{
    editWithNoTick(){
      console.log("edit without tick")
      this.dialogValue='hello'
      this.showDialog=true
    },
    editWithTick(){
      console.log("edit with tick")
      this.showDialog=true
      this.dialogValue='xxx'
      Vue.nextTick(() => this.dialogValue='hello')

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
