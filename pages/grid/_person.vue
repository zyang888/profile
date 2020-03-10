<template>
  <div>
    <h1>Person Page</h1>
    <h2>{{first}}</h2>
    <h2>{{last}}</h2>
    <h2>{{age}}</h2>
</div>
</template>

<script>

export default {
  name: 'personpage',
  props: ['first', 'last', 'age'],
  head () {
    return {
      title: 'person',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'person', name: 'person', content: 'person description' }
      ]
    }
  }
}
</script>
