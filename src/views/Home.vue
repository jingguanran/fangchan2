<template>
  <div class="home">
   <Jgr a="1" />
   <Jgr a="2"/>
   <Jgr a="3"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Jgr from '@/components/Jgr.vue'

export default {
  name: 'home',
  data(){
    return {
      c:0
    }
  },
  components: {
    Jgr:Jgr
  }
}
</script>
