<template>
  <div>
    我是父组件
    <Zi :arr="arr"></Zi>
  </div>
</template>

<script>
import Zi from './components/zi.vue'
export default {
  name: 'Zujian',
  components: {
    Zi,
  },
  data() {
    return {
      arr: [1, 2, 3, 4, 5],
    }
  },
  /* methods: {
    add(val) {
   console.log(val.b);
    },
  }, */
  methods:{
    add(val){
      console.log(val);
    }
  }
}
</script>

<style >
</style>