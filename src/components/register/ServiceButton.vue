<template>
<div>
    <b-card
    class="card-button"
    :title="dataEvent.title"
    @click="newView(dataEvent.id, dataEvent.title)" 
    >
    <b-row cols="2" >
        <b-col>
            <span class="material-icons">
            person
            </span>
            <span>{{dataEvent.places}}</span>
        </b-col>
        <b-col>
            <span class="material-icons">
            child_care
            </span>
            <span>{{dataEvent.places_kids}}</span>
        </b-col>

    </b-row>
            
    </b-card>
</div>
</template>

<script>
export default {
    props:{
        dataEvent:{
            type: Object,
            default:{}
        }
    },
data() {
    return {
        
    }
},
methods: {
  newView(eventId, title){
    localStorage.event_id = eventId;
    localStorage.title = title;
    this.$router.push({name: 'Register'})
  }
},
}
</script>
 
<style>
.card-button{
    cursor: pointer;
    width: 100%;
    max-width: 400px;
    min-width: 200px;
    background-color: #f8f8f8 !important;
    filter: drop-shadow(2px 2px 1px #dddddd);
}
</style>