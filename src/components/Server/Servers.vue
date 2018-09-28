<!-- <template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <li
                class="list-group-item"
                v-for="server in servers"
                @click="changeStatus"
                :data-id="server.id"
                :data-status="server.status">
                Server #{{ server.id }} -> Status: {{ server.status }}
            </li>
        </ul>
        <p>Status is now {{ overallStatus }}</p>
    </div>
</template> -->

<template>
	<div class="col-xs-12 col-sm-6">
		<ul class="list-group">
			<app-server
				v-for="server in servers"
				:server="server"
			>
			</app-server>
		</ul>
	</div>
</template>

<script>
	import Server from './Server.vue';

	export default {
		data: function() {
			return {
				servers: [
					{id: 1, status: 'Normal'},
					{id: 2, status: 'Critical'},
					{id: 3, status: 'Unknown'},
					{id: 4, status: 'Normal'}
				]
			};
		},
		components: {
			appServer: Server
		}
		// methods: {
		// 	changeStatus() {
		// 		this.overallStatus = event.target.getAttribute("data-status");
		// 		this.$emit('changeStatus', this.overallStatus);
		// 	}
		// },
		// props: {
		// 	overallStatus: String
		// }
	}
</script>

<!-- <style>
	.list-group-item {
		cursor: pointer;
	}
</style> -->
