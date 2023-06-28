<template>
  <VirtualListComponent/>
<!--  <TestTime/>-->
</template>

<script>
import { VirtualListComponent, TestTime } from './components/index'


import faker from 'faker';

let data = [];
for (let id = 0; id < 1000; id++) {
  data.push({
    id,
    value: faker.lorem.sentences() // 长文本
  })
}

export default {
  name: 'app',
  components: {
    VirtualListComponent,
    TestTime
  },
  data(){
    return {
      data
    };
  },

}
</script>

<style>
html{
  height: 100%;
}
body{
  height: 100%;
  margin:0;
}
#app{
  height:100%;
}

</style>
