<template>
  <div id="app">
    <!-- <todo-list :shouldShowContent="false">

      <template slot="title">
        <h1>I am the text from parent Component.</h1>
      </template>

      <template slot="content">
        <p>
          Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
        </p>
      </template>
      
    </todo-list>
    
    <users-list>
      <template slot-scope="slotProps">
        <span v-if="slotProps.user.isGoingToExit">
          Jeste nego sta
        </span>
          {{ slotProps.user.isGoingToExit | goingToExit }}
      </template>
    </users-list> -->

    <!-- FILTERI -->
  <!-- <div>{{ (message1, message)  | capitalize(message1, message)  }}</div>  -->
  <!-- prvo ce prikazati prvi objekat levo od | -->

  <div v-for="(user, index) in users" :key="index">
    <ThreeSlots>
      <template slot="userName">
          {{user.name}}
      </template>

      <template>
        <slot>
          <p>Bezveze text</p>
        </slot>
      </template>

      <template slot="exit">
          {{user.isGoingToExit | goingToExit}}
      </template>
      </ThreeSlots>
  </div>
  
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TodoList from './components/TodoList.vue'
import UsersList from './components/UsersList.vue'
import ThreeSlots from './components/ThreeSlots.vue'


export default {
  name: 'app',
  components: {
    HelloWorld,
    TodoList,
    UsersList,
    ThreeSlots
  },
    data(){
      return {
        message: 'Ovo je message',
        message1: 'Ovo je message 1',

        users: [
                        { name:'Misa', isGoingToExit: true },
                        { name:'Pera', isGoingToExit: false },
                        { name:'Zika', isGoingToExit: true },
                        { name:'Mika', isGoingToExit: false },
                        { name:'Uros', isGoingToExit: false },
                        { name:'Srna', isGoingToExit: true },
                        { name:'Bora', isGoingToExit: false },
                        { name:'Laza', isGoingToExit: false },
                        { name:'Mira', isGoingToExit: true }
                    ],
        
      }
    },

  filters: {
    capitalize: function (value, value1) {
      if (!value && !value1) {
        return ''
      }
      value = value.toString()
      value1 = value1.toString()
      
      return  value.charAt(0).toUpperCase() + value.slice(1) + value1.charAt(0).toUpperCase() + value1.slice(1)

    },
  

    toLowerCase: function (value) {
        if (!value) {
          return ''
        }
        value = value.toString()
        return  value.charAt(0).toLowerCase() + value.slice(1)
    },

  }
  

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
