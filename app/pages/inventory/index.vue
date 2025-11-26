<template>
  <v-card
    title="Inventory"
    flat
  >
    <template v-slot:text>
      <v-text-field
        v-model="search"
        label="Search"
        prepend-inner-icon="mdi-magnify"
        variant="outlined"
        hide-details
        single-line
      ></v-text-field>
    </template>

    <v-data-table
      :headers="headers"
      :items="inventory.data"
      :search="search"
    ></v-data-table>
  </v-card>
</template>
<script setup>  


  const { data: inventory } = await useFetch('http://localhost:1337/api/inventories');

  const search = ref('')
  const headers = [
    {key: 'product_name', title: 'product name'},
    { key: 'product_description', title: 'Description' },
    { key: 'quantity', title: 'quantity' },
    { key : 'condition', title : 'condition'},
    { key : 'location', title : 'location'},
    { key : 'createdAt', title : 'Date created'},


  ]
  const desserts = [
    
  ]
</script>