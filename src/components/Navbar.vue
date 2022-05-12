<template>
    <header>
        <div class="logo">
            logo
        </div>
        <ul>
            <li><router-link to="/">Home</router-link></li>
            <li> <router-link to="/about">About</router-link></li>
        </ul>
        <label for="check">
            &#9776;
            <input type="checkbox" id="check" @change="change">
        </label>
    </header>
</template>

<script>
    export default {
       name: 'NavbarComponent',
       
       methods: {
           change(e){
               if(e.target.checked) document.getElementsByTagName('ul')[0].classList.add('small-navbar');
               else document.getElementsByTagName('ul')[0].classList.remove('small-navbar');     
           }
       }
    }
</script>

<style>
    header {
        background-color: white;
        color: black;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 12px;
        height: 70px;
        box-shadow: 0 0 10px 2px rgb(0 0 0/ 10%);
        position: relative;
    }

    .logo {
        font-size: 1.5rem;
        font-weight: bold;
        line-height: 1;
        text-transform: uppercase;
    }

    header ul {
        display: flex;
        height: 100%;
    }

    header ul > li a {
        display: flex;
        color: black;
        justify-content: center;
        align-items: center;
        padding: 0px 15px;
        height: calc(100% - 2px);
    }

    header ul > li a:hover {
        opacity: .9;
        color: #42b983;
    }

    header ul > li a.router-link-exact-active {
        color: #42b983;
        border-bottom: 2px solid #42b983 ;
    }

    header input , label {
        display: none;
    }

    .small-navbar {
        visibility: visible;
        right: 0;
    }

    @media (max-width: 600px) {
        header > label {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 30px;
            width: 30px;
            box-shadow: 0 0 10px 0 rgb(0 0 0/ 10%);
            line-height: 1.5;
            cursor: pointer;
            border-radius: 4px;
        }
        header ul {
            flex-direction: column;
            visibility: hidden;
            position: fixed;
            width: 200px;
            right: -200px;
            top: 70px;
            background-color: white;
            transition: all 300ms;
            box-shadow: 0 15px 15px 0 rgb(0 0 0/ 10%);
        }

        header ul > li {
            height: 70px;
        }
    }
</style>
