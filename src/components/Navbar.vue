<template>
    <nav class="main-nav">
        <ul>
            <li><router-link :to ="{name : 'Home'}">Home</router-link></li>
            <li><router-link :to ="{name : 'About'}">About</router-link></li>
        </ul>
        <h2>User profiles</h2>
        <ul>
            <li v-for="(id,index) in userIds" :key="index">
                <router-link :to="{name: 'ViewProfile', params:{user_id: id}}">Profile {{id}}</router-link>
            </li>
        </ul>
        <h2>Navigation control</h2>
        <ul>
            <li><button @click="goBack">Go Back</button></li>
            <li><button @click="goHome">Redirect to home</button></li>
                        <li><button @click="goForward">Go Forward</button></li>

        </ul>
    </nav>
</template>

<script>
export default {
    name : 'Navbar',
    data(){
        return{
            userIds: ['1','2','3','4']
        }
    },
    methods:{
        goHome(){
            this.$router.push({name : 'Home'})
        },
        goBack(){
            this.$router.go(-1)
        },
        goForward(){
            this.$router.go(1)
        }
    }
}
</script>

<style>
ul{
    list-style: none;
    padding:0;
}
ul li{
    display: inline-block;
    padding: 20px;
}
a{
    color:#262262;
    text-decoration:none;
}
.router-link-exact-active{
    border-bottom: 2px solid #262262;
    font-weight: bolder;
}
</style>