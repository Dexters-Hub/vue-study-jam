<script>
import ListItem from './components/ListItem.vue'
import UserCard from './components/UserCard.vue'
import BaseButton from './components/BaseButton.vue'
export default {
  data() {
    return {
      message: 'Hello World!',
      show: true,
      list: [1, 2, 3],
      userList: {
        name: 'John',
        email: 'john@example.com'
      }
    }
  },
  components: {
    ListItem,
    UserCard,
    BaseButton
  },
  computed: {
    // computed example
    evenNumbers() {
      return this.list.filter((item) => item % 2 === 0)
    }
  },

  watch: {
    // watch example
    list: {
      handler() {
        console.log('List changed')
      },
      deep: true
    }
  },

  methods: {
    // evalauate to evaluate
    evaluate() {
      this.list.push(this.list.length + 1)
    }
  }
  // watchers and computed
}
</script>

<template>
  <h1>Welcome to the Study Jam - How nice of you to join!!</h1>

  <h1>Day - 2</h1>
  <!-- props -->
  <ListItem :list="list" />

  <!-- emits -->
  <UserCard :user="userList" @evaluate="evaluate" />

  <BaseButton :left="true"> </BaseButton>

  <!-- computed -->
  <p v-if="evenNumbers.length">Even Numbers: {{ evenNumbers }}</p>

  <!-- watch -->
  <button @click="evaluate">Evaluate</button>

  <!-- v-if, v-else, v-else-if -->
  <h1>Day - 1</h1>
  <h1 v-if="message.length % 2 == 0">{{ message }}</h1>
  <p v-else>There is nothing</p>

  <button @click="show = !show">Toggle List</button>
  <button @click="list.push(list.length + 1)">Push Number</button>
  <button @click="list.pop()">Pop Number</button>
  <button class="reverse-button" @click="list.reverse()">Reverse List</button>

  <ul v-if="show && list.length">
    <li v-for="(item, index) of list" :key="index">{{ item }}</li>
  </ul>

  <p v-else-if="list.length">List is not empty, but hidden.</p>
  <p v-else>List is empty.</p>
</template>
