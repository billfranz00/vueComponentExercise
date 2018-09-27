<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!overallStatus">Server Details are currently not updated</p>
        <p else>{{ overallStatus }}</p>
        <button @click="refreshStatus">Refresh Status</button>
    </div>

</template>

<script>
	export default {
		props: {
			overallStatus: String
		},
		methods: {
			refreshStatus() {
				this.overallStatus = 'Normal';
				this.$emit('refreshStatus', this.overallStatus);
			}
		}
	}
</script>

<style>

</style>
