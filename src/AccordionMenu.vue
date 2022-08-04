<template>
	<div :class="open ? 'section open' : 'section'" @click="$emit('toggleOpen', index)">
		<div class="header">{{ section.header }}</div>
		<div class="content">{{ section.content }}</div>
	</div>
</template>

<script>
export default {
	name: 'AccordionMenu',
	props: ['section', 'index', 'open']
}
</script>