<template>
  <div class="about">
  shouye>{{jgr}}
  <div v-for="i in arr">
    <h1>{{i.name}}</h1>
    <p>{{i.price}}</p>
  </div>
    
  </div>
</template>
<script>
  export default {
    data(){
      return {
        arr:[],
        jgr:""
      }
    },
    watch:{
      arr:function(){},
      '$route'(){
        if(this.$route.params.id==1){
        this.jgr="全新楼盘"
      }
      if(this.$route.params.id==2){
        this.jgr="二手楼盘"
      }
        this.$http.post("http://localhost:3000/",{abc:this.$route.params.id},{emulateJSON:true}).then(e=>this.arr=e.body)
      }
    },
    created(){
      if(this.$route.params.id==1){
        this.jgr="全新楼盘"
      }
      if(this.$route.params.id==2){
        this.jgr="二手楼盘"
      }
      this.$http.post("http://localhost:3000/",{abc:this.$route.params.id},{emulateJSON:true}).then(e=>this.arr=e.body)
    }
  }
</script>
