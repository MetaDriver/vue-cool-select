<template>
  <div class="demo-page-wrap">
    <div>
      <h1 style="text-align: center;">Usage Example 4</h1>

      <b>Selected:</b> {{ selected || 'not chosen' }}.
      <br><br>

      <!--arrows-disable-instant-selection-->
      <cool-select
        v-model="selected"
        :items="items"
        item-value="id"
        item-text="name"
        placeholder="Select name"
        @select="onSelect"
        @focus="onFocus"
        @blur="onBlur"
      />
    </div>
  </div>
</template>

<script>
import { CoolSelect } from '../../../src/main'

export default {
  components: { CoolSelect },
  data () {
    const items = [
      {
        id: '1',
        name: 'Product 1',
        price: '30.0'
      },
      {
        id: '2',
        name: 'Product 2',
        price: '100.0'
      },
      {
        id: '3',
        name: 'Product 3',
        price: '150.0'
      }
    ]

    return {
      selected: items[1],
      items
    }
  },
  methods: {
    onSelect (selected) {
      console.log('onSelect', selected, this.selected)
    },
    onBlur () {
      console.log('blur')
    },
    onFocus () {
      console.log('focus')
    }
  }
}
</script>
