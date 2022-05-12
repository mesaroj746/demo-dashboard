<template>
    <div class="bottombar">
        <router-link :to="`${a.path}`" v-for="a in menus" :key="a"> {{ a.text }}</router-link>
    </div>
</template>

<script>
export default {
    name: "BottomBar",
    data: () => ({
        menus : [
            {text: "About" , path: "/about"},
            {text: "Home" , path: "/"},
            {text: "Contact" , path: "/contact"},
        ]
    })
}
</script>

<style>

.bottombar {
    background-color: #42b983;
    position: fixed;
    bottom: 0;
    width: 100%;
    height: 60px;
    border-top-left-radius: 25px;
    border-top-right-radius: 25px;
    display: flex;
    justify-content: space-around;
    align-items: center;
}

.bottombar a {
    color: white;
}

.bottombar a.router-link-exact-active {
    color: red;
    overflow: hidden;
    border-radius: 20px;
    padding: 8px 20px;
    background-color: rgb(255 255 255 /10%);  
}

@media (min-width: 600px){
    .bottombar {
        display: none;
    }
}

</style>