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
  props: ['first', 'last', 'age']
}
</script>
