<template>
    <div class="Base">
        <Counter />
    </div>
</template>

<script>
import Counter from "./Counter.vue";
export default {
    name: "Base",
    components: {
        Counter
    }
};
</script>

<style lang="scss" scoped>

.Base {
    max-width: 500px;
    margin: 0 auto;
    padding: 5rem 5rem 8rem 5rem;
    background-color: whitesmoke;
}

.special {
    h1 {
        color: mediumaquamarine;
    }
}

h1 {
    color: red;
}
</style>
