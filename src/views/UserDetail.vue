<template>
  <UserDetailComponent />
</template>

<script>
// @ is an alias to /src
import UserDetailComponent from '@/components/UserDetailComponent.vue'

export default {
  name: 'Home',
  components: {
    UserDetailComponent
  }
}
</script>