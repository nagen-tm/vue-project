<template>
  <form @submit.prevent="submitForm">
    <div class="form-control" :class="{invalid: userNameValidity === 'invalid'}">
      <label for="user-name">Your Name</label>
      <input id="user-name" name="user-name" type="text" v-model.trim="userName" @blur="validateInput" />
      <p v-if="userNameValidity === 'invalid'">Please enter a valid name!</p>
    </div>
    <div class="form-control" :class="{invalid: emailValidity === 'invalid'}">
      <label for="email">Your Email</label>
      <input id="email" name="email" type="text" v-model.trim="email" @blur="validateInput" />
      <p v-if="emailValidity === 'invalid'">Please enter a valid email!</p>
    </div>
    <div class="form-control">
      <input type="checkbox" id="confirm-terms" name="confirm-terms" v-model="confirm" />
      <label for="confirm-terms">Agree to terms of use?</label>
    </div>
    <div>
      <button>Save Data</button>
    </div>
  </form>
</template>

<script >
import { ref } from 'vue'

  const userName = ref('')
  const userAge = ref('')
  const referrer = ref('')
  const confirm = false
  const userNameValidity= 'pending'
  const emailValidity = 'pending'

  function submitForm() {
    console.log(this.userName)

    // this.userName = '';
    // this.userAge = null;
    // this.referrer = 'wom';
    // this.confirm = false;
  }

  function validateInput(){
    if (this.userName === '') {
      this.userNameValidity = 'invalid';
    } else {
      this.userNameValidity = 'valid';
    }
  }



// export default {
//   data() {
//     return {
//       userName: '',
//       userAge: null,
//       referrer: 'wom',
//       interest: [],
//       how: null,
//       confirm: false,
//       userNameValidity: 'pending'
//     };
//   },
//   methods: {
//     submitForm() {
//       console.log('Username: ' + this.userName);
//       this.userName = '';
//       console.log('User age:');
//       console.log(this.userAge + 5);
//       console.log(this.$refs.ageInput.value + 5);
//       console.log(31);
//       this.userAge = null;
//       console.log('Referrer: ' + this.referrer);
//       this.referrer = 'wom';
//       console.log('Checkboxes');
//       console.log(this.interest);
//       console.log('Radio buttons');
//       console.log(this.how);
//       this.interest = [];
//       this.how = null;
//       console.log('Confirm?');
//       console.log(this.confirm);
//       this.confirm = false;
//     },
//     validateInput() {
//       if (this.userName === '') {
//         this.userNameValidity = 'invalid';
//       } else {
//         this.userNameValidity = 'valid';
//       }
//     }
//   },
// };
</script>

<style scoped>
form {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 2rem;
  background-color: #ffffff;
}

.form-control {
  margin: 0.5rem 0;
}

.form-control.invalid input {
  border-color: red;
}

.form-control.invalid label {
  color: red;
}

label {
  font-weight: bold;
}

h2 {
  font-size: 1rem;
  margin: 0.5rem 0;
}

input,
select {
  display: block;
  width: 100%;
  font: inherit;
  margin-top: 0.5rem;
}

select {
  width: auto;
}

input[type='checkbox'],
input[type='radio'] {
  display: inline-block;
  width: auto;
  margin-right: 1rem;
}

input[type='checkbox'] + label,
input[type='radio'] + label {
  font-weight: normal;
}

button {
  font: inherit;
  border: 1px solid #0076bb;
  background-color: #0076bb;
  color: white;
  cursor: pointer;
  padding: 0.75rem 2rem;
  border-radius: 30px;
}

button:hover,
button:active {
  border-color: #002350;
  background-color: #002350;
}
</style>