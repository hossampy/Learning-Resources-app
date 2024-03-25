<template>
    <li>
        <div>
            <header>
                <h3>{{ title }}</h3>
                <button>Delete</button>
            </header>
        </div>
        <p>{{ description }}</p>
        <nav>
            <a :href="linke">vue linek</a>
        </nav>
    </li>

</template>

<script>
export default {
    props: ['title','description','linke']

}
</script>

<style>

</style>