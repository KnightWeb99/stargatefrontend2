<!-- eslint-disable vue/valid-template-root -->
<template>
 <v-form @submit.prevent="submitUser">
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

<v-divider></v-divider>
<v-card-actions>


<v-btn @click="submitUser">
  Submit  
</v-btn>

</v-card-actions>

</v-card>

</v-form>   

</template>


<script>

export default{

data(){

return{
  name:'',
  email:'',
  password:'',
  password_confirmation: this.password,

}


},
methods:{
   
submitUser(){

//this will let us ask the parent can we send this data 
this.$emit('add-user',
this.name,
this.email,
this.password,
this.password_confirmation,

);

console.log('name');
console.log(this.name);

console.log('email');
console.log(this.email);

console.log('password');
console.log(this.password);

console.log('Confir-password');
console.log(this.password_confirmation);


}
    
},





}





</script>