<template>
  <b-container fluid class="pl-0 pt-5">
    <b-row class="justify-content-center">
      <b-col cols="auto" sm="auto">
        <b-card>
            <b-img fluid :src="require('../assets/LogoCFCnegro.png')" class="pb-5"></b-img>
            <h2>{{title}}</h2>
            <b-row class="justify-content-center py-3" align-h="center" cols="1">
              <b-col cols="9" align-self="center">
                <User/>
              </b-col>
            </b-row>
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import User from '@/components/register/user.vue'
export default {
components:{
    User
},
mounted() {
    this.title = localStorage.title
    this.event_id = localStorage.event_id
},
data() {
  return {
      event_id: 0,
      title: '',
  }
},

}
</script>

<style scoped>
.card {
  width: 100%;
  height: 100%;
  background-color: #ffffff;
  border-color: #000000;
  min-height: 800px !important;
  max-width: 1000px;
  min-width: 400px;
}
img{
  max-width: 270px;
}
</style>