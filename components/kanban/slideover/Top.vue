<script setup lang="ts">
import dayjs from 'dayjs'
import { useDealSlideStore } from '~/store/deal-slide.store'

const store = useDealSlideStore()
</script>

<template>
	<div class="border-border bg-black/20 rounded p-3">
		<div class="uppercase bold text-xl mb-4">О проекте</div>
		<KanbanSlideoverLabel label-text="Студент">
			<h2>
				{{ store.card?.name }}
			</h2>
		</KanbanSlideoverLabel>
		<KanbanSlideoverLabel label-text="Группа">
			{{ store.card.price }}
		</KanbanSlideoverLabel>
		<KanbanSlideoverLabel label-text="Статус">
			<UiBadge variant="outline">
				{{ store.card?.status }}
			</UiBadge>
		</KanbanSlideoverLabel>
		<KanbanSlideoverLabel label-text="Тема">
			{{ store.card?.companyName }}
		</KanbanSlideoverLabel>
		<KanbanSlideoverLabel label-text="Дата создания">
			{{ dayjs(store.card?.$createdAt).format('DD MMMM YYYY') }}
		</KanbanSlideoverLabel>
	</div>
</template>
