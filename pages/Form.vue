<template>
<section>
<formhelper>
  <div name="form-header">
    <h3>This is the title of the form</h3>
    <p>Information about the form</p>
  </div>
  <div slot="form-fields">
<input type="text" placeholder="name" required />
<input type="password" placeholder="password" requred />
  </div>
  <div slot="form-controls">
    <button v-on:click="clicked()">Submit</button>
  </div>
</formhelper>
<img v-show="!toggle" src="../assets/OFFbulb.jpg">
<img v-show="toggle" src="../assets/ONbulb.jpg">
</section>
</template>

<script>
import formhelper from '@/components/formhelper'
import myButton from '@/mixins/myButton'

export default {
  name: 'slotpage',
  components: {
    formhelper: formhelper
  },
  data () {
    return {
      toggle: false
    }
  },
  mixins: [myButton],
  head () {
    return {
      title: 'Form',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'Form', name: 'Form', content: 'Form description' }
      ]
    }
  },
}
</script>
