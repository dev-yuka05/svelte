<script>
	export let name;
	let today = new Date();
	let year = today.getFullYear();
	let month = today.getMonth() + 1;
	let date = today.getDate();
    let num = 0;
	let list = [];

	const listPush = ()=>{
		num++;
		if(!list.includes(name)){
			list[list.length] = name;
		}
	}
</script>
<main>

	{#if !(num <= 0)}
   		<h1>{name}님, {num}명째 기다리는중</h1>
	{:else}
		<h1>{name}님의 순번입니다</h1>
	{/if}

	{#if !(num <= 0)}
		<button on:click={() => {num++;}}>대기열에 +1하기 </button>
		<button on:click={() => {num--;}}>대기열에 -1하기</button>
	{/if}

	{#if num <= 0}
		<input bind:value={name}>
		<button on:click={() => {listPush();}}>대기열 추가</button>
	{/if}


	<ul>
		{#each list as n}
			<li>{n}</li>
		{/each}
	</ul>

	<div>
		<p>{ year }년 {month}월 { date }일</p>
	</div>
</main>