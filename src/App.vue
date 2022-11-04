
<template>
  <v-app>
    <v-main>
      <LoginUser>  
      
        <h1>test</h1>

      </LoginUser>

      <!-- <HelloWorld/> -->


    </v-main>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
import LoginUser from './components/Login/LoginUser.vue';

export default {
  name: 'App',

  components: {
    // HelloWorld,
    LoginUser,
  },

  data: () => ({
    //
  }),
}
</script>
