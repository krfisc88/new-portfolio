<script>
  export let links = [];
  export let brand = {};
</script>

<header>
	<nav>
		<div class="brand">
			<a href="{brand.url}" class="brand-link">
				{brand.title}
			</a>
		</div>
		<ul class="nav-list">
			{#each links as link}
			<li class="nav-item">
				<a class="nav-link" href="{link.url}">{link.title}</a>
			</li>
			{/each}
		</ul>
	</nav>
</header>