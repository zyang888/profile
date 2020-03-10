<template>
  <div>
    <h1>bootstrap vue grid and table example</h1>
    <h2>Click on age to redirect</h2>
    <b-table striped hover :items="tabledata">
      <template v-slot:cell(age)="age_data">
        <!-- `data.value` is the value after formatted by the Formatter -->
        <nuxt-link :to="`/grid/${age_data.value}`">
          {{ age_data.value }}
        </nuxt-link>
      </template>
    </b-table>
  </div>
</template>

<script>
import tabledata from '@/data/tabledata'

export default {
  name: 'gridpage',
  data () {
    return {
      tabledata: tabledata
    }
  },
  head () {
    return {
      title: 'Grid',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'Grid', name: 'Grid', content: 'Grid description' }
      ]
    }
  }
}
</script>
