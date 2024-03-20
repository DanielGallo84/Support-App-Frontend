<script setup>

// import { useAuthStore } from "../stores/user";
// const store = useAuthStore();

</script>
    
<template>
    <header class="wrapper">

    <div id="headerContainer">

        <img src="/images/company-logo.png" alt="">
        <RouterLink class="routerLink" to="/">LOG OUT</RouterLink>

</div>

</header>

   
</template>

<style lang="scss" scoped>

@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond&family=Space+Grotesk&display=swap');

    #headerContainer {

        width: 100%;
        height: 10vh;

        background-image: linear-gradient(rgba(143, 253, 194, 1) 80%, white);
        //background-image: linear-gradient(red, yellow);
        
        display: flex;
        justify-content: space-between;
        flex-direction: row;
        align-items: center;

        font-family: 'Space Grotesk', serif;
        color: white;
        width: 100%;

        .headerLink {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            margin-right: 15px;
            gap: 1rem;
        }

        .headerLinkLogged {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            margin-right: 15px;
            gap: 1rem;
        }

        .routerLink {
            text-decoration: none;
            color: white;
        }

        img {
            height: 90%;
        }
    }
    @media only screen and (min-width: 768px){
        // #headerContainer{
        //     img{
        //         margin-left: 3%;
        //     }
        //     .headerLink{
        //         margin-right: 3%;
        //     }
        //     .headerLinkLogged{
        //         margin-right: 3%;
        //     }
        // }
    }

</style>