<template>
  <div>
    <b-form @submit="onSubmit" @reset="onReset" novalidate>

        <h2>{{form.name}}</h2>

      <b-form-group id="input-group-1" label="Your Name:" label-for="input-1">
        <b-form-input
            id="input-1"
            v-model="form.name"
            placeholder="Enter name"
            type="text"
        ></b-form-input>
      </b-form-group>

<!--      <b-form-group id="input-group-2" label="Your Surname:" label-for="input-2">-->
<!--        <b-form-input-->
<!--            id="input-2"-->
<!--            v-model="surname"-->
<!--            placeholder="Enter surname"-->
<!--        ></b-form-input>-->
<!--      </b-form-group>-->

<!--      <b-form-group id="input-group-2" label="Your Telephone:" label-for="input-3">-->
<!--        <b-form-input-->
<!--            id="input-3"-->
<!--            v-model="phone"-->
<!--            placeholder="Enter phone"-->
<!--            v-mask="'+7(###)-###-##-##'"-->
<!--        ></b-form-input>-->
<!--      </b-form-group>-->

      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>

  </div>
</template>

<script>

import { required } from 'vuelidate/lib/validators'


export default {
  data() {
    return {
      form: {
        name: '',
        surname: '',
        phone: ''
      }
    }
  },

  validations: {
    name: {
        required
      }
  },

  methods: {
    onSubmit(event) {
      event.preventDefault()
      console.log(this.form.name)
    },

    onReset(event) {
      event.preventDefault()
      this.form.email = ''
      this.form.name = ''
    }
  }
}
</script>

<style scoped>

</style>


