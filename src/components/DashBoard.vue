<template>
<div class="container-fluid">
  <MenuPage />
</div>

</template>
<script>
import MenuPage from './MenuPage.vue'
export default {
    name : 'DashBoard',
    components : {
        MenuPage
    },
    data(){
        return {

        }
    }
}
</script>
<style>
.container-fluid{
    margin : 0;
    padding: 0;
}
</style>