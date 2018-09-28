<template>
    <div class="container">
        <app-header></app-header>
        <hr>
        <div class="row">
            <!-- <servers :overallStatus="status" @changeStatus="status = $event"></servers>
            <app-server-details :overallStatus="status" @refreshStatus="status = $event"></app-server-details> -->
            <servers></servers>
            <app-server-details></app-server-details>
        </div>
        <hr>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import Header from './components/Shared/Header.vue';
    import Footer from './components/Shared/Footer.vue';
    import Servers from './components/Server/Servers.vue';
    import ServerDetails from './components/Server/ServerDetails.vue';

    export default {
        components: {
            appHeader: Header,
            Servers,
            'app-server-details': ServerDetails,
            'app-footer': Footer
        }
        // },
        // data: function() {
        //     return {
        //         status: 'Normal'
        //     }
        // }
    }
</script>

<style>

</style>
