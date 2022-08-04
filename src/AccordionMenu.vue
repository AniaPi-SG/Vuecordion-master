<template>
	<div :class="open ? 'faq open' : 'faq'" @click="$emit('toggleOpen', index)">
		<div class="question">{{ faq.header }}</div>
		<div class="answer">{{ faq.content }}</div>
	</div>
</template>

<script>
export default {
	name: 'AccordionMenu',
	props: ['faq', 'index', 'open']
}
</script>