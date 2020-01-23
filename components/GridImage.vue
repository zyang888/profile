<template>
  <div class="mb-3 pics animation">
    <img class="img-fluid" :src="src" :alt="alt">
  </div>
</template>

<script>
export default {
  name: 'gridimage',
  props: ['src', 'alt']
}
</script>
