<script context="module" lang="ts">
	export type Achievement = {
		id: number;
		title: string;
		description: string;
		date: string;
		workAreas: string[];
	};
</script>

<script>
	export let achievement;
	export let handleFilter;
</script>

<div class="p-card" data-achievement-id={achievement.id}>
	<h3>
		{achievement.title}
		<a
			class="p-button--link is-inline is-dense has-icon"
			href="/Achievement/{achievement.id}"
			title="Edit this achievement"><i class="p-icon--plus" /></a
		>
	</h3>
	<p>
		{achievement.description}
	</p>

	<div>
		{#each achievement.workAreas as workArea}
			<button class="p-chip" on:click={() => handleFilter(workArea)}>
				<span class="p-chip__value">{workArea}</span>
			</button>
		{/each}

		<span class="p-chip--information">
			<span class="p-chip__lead">Date</span>
			<span class="p-chip__value">{achievement.date}</span>
		</span>
	</div>
</div>
