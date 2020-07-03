<template>
    <ul>
        <li>
            <router-link :to="{name:'home'}">
                Home
            </router-link>
        </li>
        <template v-if="getAuthenteticated">
            <li>
                {{getUser.name}}
            </li>
            <li>
                <router-link :to="{name:'dashboard'}">
                    Dashboard
                </router-link>
            </li>
            <li>
                <a href="#">
                    Sign out
                </a>
            </li>
        </template>
        <template v-else>
            <li>
                <router-link :to="{name:'signin'}">
                    Sign in
                </router-link>
            </li>
        </template>
    </ul>
</template>

<script>
    import {mapGetters} from 'vuex'

    export default {
        name: "TheNavigation",
        computed: {
            ...mapGetters({
                getAuthenteticated: 'auth/getAuthenteticated',
                getUser: 'auth/getUser'
            }),
        }
    }
</script>

<style scoped>

</style>