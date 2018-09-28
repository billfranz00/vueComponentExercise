<template>
    <div class="col-xs-12 col-sm-6">
       <!--  <p v-if="!overallStatus">Server Details are currently not updated</p>
        <p else>{{ overallStatus }}</p>
        <button @click="refreshStatus">Refresh Status</button> -->
        <p>Server Details are currently not updated</p>
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
		created() {
			serverBus.$on('serverSelected', (server) => {
				this.server = server;
			});
		}
	}
</script>

<style>

</style>
