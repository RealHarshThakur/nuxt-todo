<template>
  <div>
    <v-container class ="my-12 mx-3">
      <v-text-field label="Todo" placeholder="List your todo" v-model="task" @keydown.enter="create"></v-text-field>
  
        <v-btn @click="create" block icon color="yellow"   >
          <v-icon left> mdi-plus</v-icon> 
          <v-span> Todo </v-span> 
        </v-btn>
    </v-container>

    <v-divider class="my-12"></v-divider>

    <h2 class="display-3 success--text pl-4">
        Tasks:&nbsp;
      <v-fade-transition leave-absolute>
        <span :key="`tasks-${tasks.length}`">
          {{ tasks.length }}
        </span>
      </v-fade-transition>
    </h2>
    
    <h2 class="display-1 mx-5 my-7 font-weight-medium blue--text">List of todos:</h2>

    <v-container class="my-4 display-1">
      <v-layout v-for="task in tasks" :key="task.id" row wrap> 
        <v-flex lg10 md10>
          <v-card  flat class="  ma-3 pa-2">
            <span>{{task.text}}</span>
          </v-card>
        </v-flex>
        <v-flex class="my-4 " lg2 md2> 
          <v-btn dark small color="error"  @click="remove(task.id)" >
            <v-icon>mdi-minus</v-icon>
          </v-btn>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>


export default {
  data: ()=>({
      tasks: [
        {
          id:"1",
          done: false,
          text: "This is a really really long text and that is all i had to say to make it long enough\
          so that I can check something which is irrelevant to this text, anyways the text isn't long enough\
          yet so I'll be doing this until it is long enough" ,
        },
        {
          id:"2",
          done: false,
          text: 'Eat',
        },
        {
          id:"3",
          done: true,
          text:'Sleep'
        },
        {
          id:"4",
          done: true,
          text:'Sleep again'
        },
        {
          id:"5",
          done: false,
          text:'Filling todo list'
        },

      ],
      task: null,
  }),

 methods: {
      create () {
        this.tasks.push({
          done: false,
          text: this.task,
        })

        this.task = null
      },
    remove(id){

      this.tasks = this.tasks.filter((task)=> task.id!==id);

    }
  },


}
</script>
