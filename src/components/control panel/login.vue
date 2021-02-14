<template>
  <div>
    <b-form @keyup.enter="clickEnter" @submit="onSubmit">
      <b-row cols="1" cols-md="4" cols-sm="2" cols-lg="6" cols-xl="6">
        <b-col cols="12" md="3" sm="6" lg="4" xl="4">
          <b-form-group
            :id="'input-group-1'"
            label="Usuario:"
            :label-for="'input-1'"
          >
            <b-form-input
              :id="'input-1'"
              v-model="users.name"
              type="text"
              placeholder="Ingrese usuario"
              required
            ></b-form-input>
          </b-form-group>
        </b-col>
        <b-col cols="12" md="4" sm="6" lg="4" xl="4"
          ><b-form-group
            :id="'input-group-2'"
            label="Contraseña:"
            :label-for="'input-2'"
          >
            <b-form-input
              :id="'input-2'"
              v-model="users.password"
              type="password"
              placeholder="Ingrese contraseña"
              required
            ></b-form-input> </b-form-group
        ></b-col>
      </b-row>
      <b-button class="register-button m-5" type="submit">Ingresar</b-button>
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
    clickEnter(){
      const buttonEnter = document.querySelector('.register-button')
      buttonEnter.click();
    },
  },
};
</script>

<style>

</style>