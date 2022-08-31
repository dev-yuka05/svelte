<script>
	export let name;
	let today = new Date();
	let year = today.getFullYear();
	let month = today.getMonth() + 1;
	let date = today.getDate();
    let num = 0;
</script>
<main>
    <h1>{name}님, {num}명째 기다리는중</h1>

	{#if num != 0}
		<button on:click={() => {num++;}}>대기열에 +1하기 </button>
		<button on:click={() => {num--;}}>대기열에 -1하기</button>
	{/if}

	{#if num == 0}
		<input bind:value={name}>
		<button on:click={() => {num++;}}>대기열 추가</button>
	{/if}

	<div>
		<p>{ year }년 {month}월 { date }일</p>
	</div>
</main>