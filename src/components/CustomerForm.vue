<template>
  <div class="customer-form">
    <form @submit.prevent="submit">
      <div class="form-group">
        <label for="name">Nama</label>
        <input type="text" v-model="customer.name" class="form-control" placeholder="Masukan nama pelanggan">
      </div>
      <div class="form-group">
        <label for="email">Email</label>
        <input type="text" v-model="customer.email" class="form-control" placeholder="Masukan email pelanggan">
      </div>
      <div class="form-group">
        <label for="address">Alamat</label>
        <textarea type="text" v-model="customer.address" class="form-control" 
          placeholder="Masukan alamat pelanggan"> </textarea>
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'CustomerForm',
  data(){
    return {
      customer: {
        name: '',
        email:'',
        address: ''
      }
    }
  },
  methods: {
    submit(){
      this.$emit('add-customer', this.customer)
      this.customer = {
        name: '',
        email: '',
        address: '',
      }
    }
  }
}
</script>

<style>

</style>