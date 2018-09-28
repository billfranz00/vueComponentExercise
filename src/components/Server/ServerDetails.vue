<template>
    <div class="col-xs-12 col-sm-6">
       <!--  <p v-if="!overallStatus">Server Details are currently not updated</p>
        <p else>{{ overallStatus }}</p>
        <button @click="refreshStatus">Refresh Status</button> -->
        <p v-if="!server">Please select a Server</p>
        <p v-else>Server #{{ server.id }} selected, Status: {{ server.status }}</p>
        <hr>
        <button @click="resetStatus">Change to Normal</button>
    </div>

</template>

<script>
	import { serverBus } from '../../main';
	export default {
		// props: {
		// 	overallStatus: String
		// },
		// methods: {
		// 	refreshStatus() {
		// 		this.overallStatus = 'Normal';
		// 		this.$emit('refreshStatus', this.overallStatus);
		// 	}
		// }
		data: function() {
			return {
				server: null
			}
		},
		methods: {
			resetStatus() {
				this.server.status = 'Normal'; // Changes status of corresponding server in servers Array (Servers.vue - saved in memory)
			}
		},
		created() {
			serverBus.$on('serverSelected', (server) => {
				this.server = server;
			});
		}
	}
</script>

<style>

</style>
