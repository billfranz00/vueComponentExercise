<template>
	<li class="list-group-item"
		@click="serverSelected"
	>
		Server #{{id}}
	</li>
</template>

<script type="text/javascript">
	import { serverBus } from '../../main';
	export default {
		props: ['id'],
		methods: {
			serverSelected() {
				serverBus.$emit('serverSelected', this.id);
			}
		}
	}
</script>

<style type="text/css">
	.list-group-item {
		cursor: pointer;
	}
</style>