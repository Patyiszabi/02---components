<script setup>
    const props =defineProps({
        title: {
            type: String,
            required: true,         
            default: 'My Vue App'
        }
    });

function alertTitle() {
        alert(`The title is: ${props.title}`);
    }

 </script>

<template>
    <nav>
        <ul>
            <li><a href="/" @click="alertTitle">{{ title }}</a></li>
            <li><a href="https://vuejs.org/">Vue.js</a></li>
        </ul>
    </nav>

</template>

<style scoped>
nav {
    width: 100%;
    height: 3rem;
    background-color: #2c3e50;
}

nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    height: 100%;
    align-items: center;
}

nav ul li {
    margin: 0 1rem;
}

nav ul li a {
    color: white;
    text-decoration: none;
}



</style>
