<template>
    <div class="about">
        <h1>Profile of {{userId}}</h1>
    </div>
</template>

<script>
export default {
    name: "ViewProfile",
    data(){
        return{
            userId : this.$route.params.user_id
        }
    },
    methods :{
        updateId(){
            this.userId = this.$route.params.user_id
        }
    },
    watch : {
        $route : 'updateId'
    }
}
</script>


<style>

</style>