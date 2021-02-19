<template>
  <UserComponent />
</template>

<script>
// @ is an alias to /src
import UserComponent from '@/components/UserComponent.vue'

export default {
  name: 'Home',
  components: {
    UserComponent
  }
}
</script>