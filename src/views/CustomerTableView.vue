<template>
  <div>
    <h1 class="mb-4">Daftar Pelanggan</h1>
     <hr>
      <p> 
        <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapseExample" aria-expanded="false" aria-controls="collapseExample">
        Tambah Pelanggan
        </button>
      </p>

    <CustomerTable :customers='customers' />

    <div class="collapse" id="collapseExample">
        <div class="card card-body">
          <h2>Input Data Pelanggan</h2>
          <hr>

          <CustomerForm @add-customer="addCustomer" />

        </div>
      </div>
  </div>
</template>

<script>
// @ is an alias to /src
import CustomerTable from '@/components/CustomerTable.vue'
import CustomerForm from '@/components/CustomerForm.vue'

export default {
  name: 'CustomerTableView',
  components: {
    CustomerTable,
    CustomerForm
  },
  data() {
    return {
      customers: [
        {
          id: 1,
          name: 'NUNA',
          email: 'bambang@mail.com',
          address: 'Jl.Kenanga',
        },
        {
          id: 2,
          name: 'Dika',
          email: 'dika@mail.com',
          address: 'Jl.Mangga',
        },
        {
          id: 3,
          name: 'Agus',
          email: 'agus@mail.com',
          address: 'Jl.Mataram',
        },
      ],
    }
  },
  methods: {
    addCustomer(customer) {
      this.customers.push(customer)
    }
  }
}
</script>