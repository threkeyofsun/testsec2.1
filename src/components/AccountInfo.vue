<template>
    <div><h1>App Component</h1>
    <ProfilePage username="Hellp"/>
    <RightCol asds="Hel55lp"/>
    </div>
</template>
 
<script>
import ProfilePage from "./ProfilePage.vue";
import RightCol from "./rightColumn.vue";

export default {
 name:"AccountInfo",
 components:{
     ProfilePage,
     RightCol
 },
}
</script>