<template>
  <div>
    <b-form @keyup.enter="clickEnter" @submit="onSubmit">
      <b-row cols="1" cols-md="4" cols-sm="2" cols-lg="6" cols-xl="6" v-for="(item, index) in users" :key="'user'+index">
        <b-col cols="12" md="3" sm="6" lg="4" xl="4">
          <b-form-group
            :id="'input-group-1' + index"
            label="DNI/NIE/PASAPORTE:"
            :label-for="'input-1' + index"
          >
            <b-form-input
              :id="'input-1' + index"
              v-model="users[index].dni"
              type="text"
              placeholder="Ingrese su documento"
              required
            ></b-form-input>
          </b-form-group>
        </b-col>
        <b-col cols="12" md="4" sm="6" lg="4" xl="4"
          ><b-form-group
            :id="'input-group-2' + index"
            label="Nombre completo:"
            :label-for="'input-2' + index"
          >
            <b-form-input
              :id="'input-2' + index"
              v-model="users[index].name"
              type="text"
              placeholder="Ingrese su nombre"
              required
            ></b-form-input> </b-form-group
        ></b-col>
        <b-col cols="10" md="4" sm="6" lg="3" xl="3"
          ><b-form-group
            :id="'input-group-3' + index"
            label="Correo electronico:"
            :label-for="'input-3' + index"
          >
            <b-form-input
              :id="'input-3' + index"
              v-model="users[index].email"
              type="email"
              placeholder="Ingrese su correo"
              required
            ></b-form-input> </b-form-group
        ></b-col>
        <b-col align-self="center" cols="1" md="1" sm="1" lg="1" xl="1"
          ><span v-if="index > 0"  class="material-icons material-icons-remove" @click="deleteUser(index)">
            horizontal_rule
          </span></b-col>
      </b-row>
<div>
        <span class="material-icons" @click="createUser">person_add</span>
      </div>
<hr>
      <b-row cols="1" cols-md="4" cols-sm="2" cols-lg="4" cols-xl="4" v-for="(item, index) in children" :key="'child'+index">
        <b-col cols="12" md="4" sm="6" lg="4" xl="4">
          <b-form-group
            :id="'input-group-child-1' + index"
            label="DNI/NIE/PASAPORTE:"
            :label-for="'input-child-1' + index"
          >
            <b-form-input
              :id="'input-child-1' + index"
              v-model="children[index].dni"
              type="text"
              placeholder="Ingrese su documento"
              required
            ></b-form-input>
          </b-form-group>
        </b-col>
        <b-col cols="12" md="4" sm="6" lg="4" xl="4"
          ><b-form-group
            :id="'input-group-child-2' + index"
            label="Nombre completo:"
            :label-for="'input-child-2' + index"
          >
            <b-form-input
              :id="'input-child-2' + index"
              v-model="children[index].name"
              type="text"
              placeholder="Ingrese su nombre"
              required
            ></b-form-input> </b-form-group
        ></b-col>
        <b-col cols="10" md="3" sm="6" lg="3" xl="3"
          ><b-form-group
            :id="'input-group-child-3' + index"
            label="Ingrese la edad:"
            :label-for="'input-child-3' + index"
          >
            <b-form-input
              :id="'input-child-3' + index"
              v-model="children[index].age"
              type="number"
              min="3"
              max="12"
              placeholder="Edad"
              required
            ></b-form-input> </b-form-group
        ></b-col>
        <b-col align-self="center" cols="1" md="1" sm="1" lg="1" xl="1"
          ><span class="material-icons material-icons-remove" @click="deleteChild(index)">
            horizontal_rule
          </span></b-col
        >
      </b-row>
      <div>
        <span class="material-icons" @click="createChild">child_care</span>
      </div>
      <b-button class="register-button m-5" type="submit">Registrar</b-button>
    </b-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [
        {
          name: "",
          email: "",
          dni: "",
        },
      ],
      children: [],
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.users));
      this.$router.push({name:"Registed"})
    },
    createUser() {
      this.users.push({
        name: "",
        email: "",
        dni: "",
      });
    },
    createChild() {
      this.children.push({
        name: "",
        email: "",
        age: 3,
      });
    },
    clickEnter(){
      const buttonEnter = document.querySelector('.register-button')
      buttonEnter.click();
    },
    deleteUser(index) {
      this.users.splice(index, 1);
    },
    deleteChild(index) {
      this.children.splice(index, 1);
    },
  },
};
</script>

<style>
.form-control {
  font-size: 0.7rem !important;
}
.material-icons{
  cursor: pointer;
  font-size: 30px !important;
}
.material-icons-remove{
  color: red !important;
}
.register-button{
  background-color: #f9f9f9 !important;
  font-size: 18px !important;
  border: none  !important;;
  color: #000000 !important;
  filter: drop-shadow(2px 2px 1px #bbbaba);
}
</style>