<template>
  <div class="hello">
    <fly :list='list'></fly>
  </div>
</template>

<script>
import fly from './fly'
export default {
  name: 'HelloWorld',
  components: {
    fly
  },
  data () {
    return {
      list:[
        {name:'第一条乱飞的数据'},
        {name:'第一发大水发的'},{
          name:'对方是否都感受到法国'
        },{
          name:'东方饭店更舒服的'
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
