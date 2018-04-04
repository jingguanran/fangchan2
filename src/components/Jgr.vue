<template>
    <div style="border:1px solid black">
    <div v-for="i in arr">
    {{i.name}}:{{i.price}}
    </div>
    </div>
</template>
<script>
    export default {
        props:{
            a:String
        },
        data(){
            return {
                arr:[]
            }
        },
        created(){
            this.$http.post('http://localhost:3000',{abc:this.a},{emulateJSON:true}).then(e=>this.arr=e.body)
        }
    }
</script>