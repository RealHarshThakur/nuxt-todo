<template>
  <v-app dark>

    <v-app-bar  absolute src="https://picsum.photos/1920/1080?random" color="purple darken-4">    
      
        <v-toolbar-title class="mx-auto display-2 font-weight-bold">Todo App</v-toolbar-title> 
    </v-app-bar>
  <v-content>
      <v-container>
          <nuxt />
      </v-container>
  </v-content>
  </v-app>
</template>

<script>
export default {
  data () {
    return {

      items: [
        {
          to: '/'
        },
      ],
      title: 'Todo'
    }
  }
}
</script>

<style scoped>
.text-center{
  margin: 0 auto;
}
</style>
