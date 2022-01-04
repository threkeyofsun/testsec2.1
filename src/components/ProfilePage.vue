// AccountInfo.vue

<template>
 <div>
   <h1>{{message}}</h1>
   {{username}}
 </div>
</template>
 
<script>
export default {
    name:"ProfilePage",
    data(){
        return{
            message:"ข่อกกกก"
        }
    },
 props: ['username']
}
</script>