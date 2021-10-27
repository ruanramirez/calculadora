<template>
	<button class="button"
		@click="$emit('onClick', label)"
		:class="{ double, triple, operation }">
			{{ label }}
	</button>
</template>

<script>
	export default {
		props: {
			label: {},
			operation: { type: Boolean },
			double: { type: Boolean },
			triple: { type: Boolean },
		}
	}
</script>

<style>
	:root {
		--bg-button: #F0F0F0;
		--bg-operation: #FA8231;
		--bg-operation-active: #FA8231cc;
		--bg-active: #CCCCCC;
		--border-button: solid 1px #888888;
		--color-text: #FFFFFF;
	}

	.button {
		font-size: 1.6rem;
		font-weight: 600;
		background-color: var(--bg-button);
		border: none;
		border-right: var(--border-button);
		border-bottom: var(--border-button);
		outline: none;
	}

	.button:active {
		background-color: var(--bg-active);
	}

	.button.double {
		grid-column: span 2;
	}

	.button.triple {
		grid-column: span 3;
	}

	.button.operation {
		background-color: var(--bg-operation);
		color: var(--color-text);
	}

	.button.operation:active {
		background-color: var(--bg-operation-active);
	}

</style>
