<template>
    <div>
        <nav @click="goBack" v-if="$route.name !== 'LandingPage'" class="go-back-container fixed h-16">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-16" fill="white" viewBox="0 0 24 24" stroke="black">
                <path stroke-linecap="round" stroke-linejoin="round" d="M11 15l-3-3m0 0l3-3m-3 3h8M3 12a9 9 0 1118 0 9 9 0 01-18 0z" />
            </svg>
        </nav>
        <router-view :key="key" />
    </div>
</template>

<script>
export default {
    name: 'layout',
    computed: {
        key() {
            return this.$route.fullPath;
        },
    },
    created(){
        console.log(this.$route)
    },
    methods: {
        goBack(){
            this.$router.go(-1)
        }
    }
}
</script>

<style scoped>
    .go-back-container{
        bottom: 0;
        margin: 10px;
        z-index: 9999;
    }
</style>