<template>
  <div ref="fly-container" class="content">
    <template v-for="(item,index) in newList">
      <span :style="{top:item.y+'px',left:item.x+'px'}">
        {{item.text}}
      </span>
    </template>
  </div>
</template>
<script>
export default {
  name:"fly",
  props:{
    list:{
      type:Array,
      default:[]
    }
  },
  data () {
    return {
      newList:[],
      cWidth:null,
      cHeight:null
    }
  },
  created () {
    this.$nextTick(()=>{
      this.initData()
      this.anit()
    })
  },
  methods: {
    initData(){
      this.cWidth = this.$refs['fly-container'].offsetWidth
      this.cHeight = this.$refs['fly-container'].offsetHeight

      this.list.forEach(item => {
        this.newList.push({x:this.cWidth*(Math.random()),y:this.cHeight*(Math.random()),text:item.name})
      })
    },
    anit(){
      let timer = null
      timer = setInterval(()=>{
        this.newList.forEach(i=>{
          this.changeXY(i)
        })
      },100)
      this.newList.forEach()
    },
    changeXY(i){
      i.x++
      i.y++
    }
  }
}
</script>
<style>
  .content {
    width: 80%;
    height: 300px;
    margin: 0 auto;
    position: relative;
  }
  .content span {
    position: absolute;
  }
</style>


