<template>
  <VirtualList :listData="list" :estimatedItemSize="100" v-slot="slotProps">
    <Item :item="slotProps.item" />
  </VirtualList>
  <button id="button">button</button><br>
  <ul id="container"></ul>
</template>

<script>
import VirtualList from './virtual-list.vue'
import Item from './item.vue'
import { defineComponent, reactive, toRefs } from 'vue'

import faker from 'faker';

let list = [];
for (let id = 0; id < 1000; id++) {
  list.push({
    id,
    value: faker.lorem.sentences() // 长文本
  })
}

export default defineComponent({
  components: {
    VirtualList,
    Item
  },
  setup(props, ctx) {
    const data = reactive({
      list
    })
    return {
      ...toRefs(data),

    }
  }
})
</script>
<style lang="scss" scoped ></style>
