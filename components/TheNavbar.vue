<template>
    <nav class="nav">
        <div class="logo">
            <nuxt-link :to="{name: 'index'}" class="logo text-lg">
                Nuxt Fundamentals
            </nuxt-link>
            <span class="subheader">A Vue Treaning course</span>
        </div>
    </nav>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Marvel&display=swap');
    nav{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 70px;
        font-weight: lighter;
        letter-spacing: 0.5px;
    }
    .nav .logo {
        display: flex;
        flex-direction: column;
        justify-content: center;
        font-family: 'Marvel', sans-serif;
    }
    .nav .logo .subheader {
        opacity: 0.7;
        font-size: 0.9rem;
        color: whitesmoke;
        font-weight: 700;
        letter-spacing: 1px;
        font-family: sans-serif;
    }
    .nav .nav-content{
        font-size: 1rem;
    }
    .nav-content ul{
        display: flex;
        list-style: none;
    }
    .nav-content ul li{
        padding: 2px 10px;
    }
    .nav-content ul li:not(:first-of-type){
        border-left: 1px solid rgb(255, 255, 255, .2);
    }


</style>