<template>
  <div id="container">
    <header>
      <h1>daftar nama user</h1>
    </header>
    <div class="list">
      <ul v-for="user in users" :key="user.id" style="list-style: none">
        <li>
          <router-link :to="{name: 'UserDetail', params:{id: user.id}}">
            {{ user.name }}
          </router-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      users: []
    }
  },
  created() {
    this.getAllUser()
  },
  methods: {
    getAllUser() {
      axios.get('https://jsonplaceholder.typicode.com/users')
        .then((response) => {
          this.users = response.data 
          console.log(users)
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>

<style scoped>
.list {
    margin-left: -50px;
}
</style>