<template>
    <div>
        <p>FirstName : {{ profile.firstName }}</p>
        <p>LastName : {{ profile.lastName }}</p>
        <p>FullName : {{ fullName }}</p>
    </div>
    <button @click="rename">Rename</button>
</template>

<script setup>
    import { computed, reactive } from 'vue';

    const profile = reactive({
        firstName: "Toto",
        lastName: "Tutu"
    })

    const fullName = computed(() => {
        return `${profile.firstName} ${profile.lastName}`
    })

    function rename() {
        profile.firstName = profile.firstName == "Toto" ? "Titi" : "Toto"
    }
</script>

<style scoped>

</style>
