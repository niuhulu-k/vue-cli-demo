<template>
  <button id="button" @click="handleClick">button</button><br>
  <ul id="container"></ul>
</template>

<script>
import { defineComponent, onMounted } from 'vue'

export default defineComponent({
  setup(props, ctx) {

    onMounted(() => {
      document.getElementById('button').addEventListener('click',function(){
        // 记录任务开始时间
        let now = Date.now();
        // 插入一万条数据
        const total = 10000;
        // 获取容器
        let ul = document.getElementById('container');
        // 将数据插入容器中
        for (let i = 0; i < total; i++) {
          let li = document.createElement('li');
          li.innerText = ~~(Math.random() * total)
          ul.appendChild(li);
        }
        console.log('JS运行时间：',Date.now() - now);
        setTimeout(()=>{
          console.log('总运行时间：',Date.now() - now);
        },0)
        //
        // print JS运行时间：38
        // print 总运行时间：957
      })

    })

    const handleClick=()=>{
      console.log('ooooooooo')
    }

    return{
      handleClick,
    }


  }
})

</script>
<style lang="scss" scoped ></style>
