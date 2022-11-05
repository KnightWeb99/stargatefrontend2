<!-- eslint-disable no-undef -->
<!-- eslint-disable no-unused-vars -->
<!-- eslint-disable vue/valid-template-root -->
<!-- /* eslint-disable */ -->
<template>
 <v-form @submit.prevent="login()">
<v-card>

<v-text-field
v-model="name"
type="text"
label="Your name"
>

</v-text-field>


<v-text-field
v-model="email"
type="text"
label="Your Email"
>
</v-text-field>



<v-text-field
v-model="password"
type="password"
label="password shh"
>
</v-text-field>


<v-text-field
v-model="password_confirmation"
type="password"
label="Confirm your password"
>
</v-text-field>

<div v-if="error">
          {{error}}
        </div>

        <div v-if="success" id="success">
          Logged in Successfully
        </div>

<v-divider></v-divider>
<v-card-actions>


<v-btn type="submit">
  Submit  
</v-btn>

</v-card-actions>

</v-card>

</v-form>   

</template>


<script>
import axios from 'axios';

export default{

data(){

return{
  name:'',
  email:'',
  password:'',
  password_confirmation: this.password,
  error:null,
  success:false,

}


},
methods:{
   
  /* eslint-disable */
// submitUser(){

// //this will let us ask the parent can we send this data 
// this.$emit('add-user',
// this.name,
// this.email,
// this.password,
// this.password_confirmation,

// );

// console.log('name');
// console.log(this.name);

// console.log('email');
// console.log(this.email);

// console.log('password');
// console.log(this.password);

// console.log('Confir-password');
// console.log(this.password_confirmation);


// }

login: async function() {
        const auth = { name: this.name, email: this.email, password: this.password, password_confirmation: this.password  };
        // Correct username is 'foo' and password is 'bar'
        const url = 'http://localhost:8000/api/login';
        this.success = false;
        this.error = null;

        try {
          const res = await axios.post(url, { auth }).then(res => res.data);
          this.success = true;
        } catch (err) {
          this.error = err.message;
        }
      }
    },


    






}





</script>