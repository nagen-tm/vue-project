<script setup>
  import {ref} from 'vue';
  import { Field, Form, ErrorMessage } from 'vee-validate';

  const validateEmail = async (value) =>{
    if(!value){
      return 'This field is required.'
    }
    // if the field is not a valid email
    const regex = /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$/i;
    if (!regex.test(value)) {
      return 'This field must be a valid email';
    }
    // All is good
    return true;
  }

  const onSubmit = async () => {

  }
</script>

<template>
  <div class="test-form">
    <Form @submit="onSubmit">
      <Field name="email" type="email" :rules="validateEmail" />
      <ErrorMessage name="email" />

    </Form>
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
