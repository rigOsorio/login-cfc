<template>
  <b-container fluid class="pl-0 pt-5">
    <b-row class="justify-content-center">
      <b-col cols="auto" sm="auto">
        <b-card>
            <b-img fluid :src="require('../assets/LogoCFCnegro.png')" class="pb-5"></b-img>
            <b-row v-for="item in events" :key="item.id" class="justify-content-center py-3" cols="1">
              <b-col cols="9">
                <Login/>  
              </b-col>
            </b-row>
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Login from '@/components/control panel/login.vue'
export default {
components:{
    Login
},
data() {
  return {
    
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