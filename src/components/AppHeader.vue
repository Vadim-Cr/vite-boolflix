<script>

export default {
    name: "AppHeader",
    props: ["message"],
    data() {
        return {
            search: '',
        }
    }

};

</script>

<template>
    <header>
        <h1>{{ message }}</h1>
        <div class="search-container">
            <input v-model="search" type="text" placeholder="Search...">
            <button @click="handleSearch">Cerca</button>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use '../components/style/partials/variables' as *;
@use '../components/style/partials/mixins.scss' as *;
@use "../components/style/general.scss";

header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    height: 5rem;
}

.search-container {
    display: flex;
    width: 25%;

    input {
        margin: 1rem;
    }

    button {
        margin: 0.75rem;
    }
}

h1 {
    color: $secondary;
    width: 25%;
}
</style>
