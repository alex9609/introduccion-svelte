<script>
	let texto = ''
	let numero = 0
	let rango = 0
	//Cuando tenemos un checkbox siempre tenemos dos valores
	//true o false
	let check = false

	let frutas = ['tomate','palta','frutilla']
	let radio =''
	let arrayResultado = []

	$: console.log(arrayResultado)
</script>

<div>
	<h1>Bindings</h1>
	<h2>Texto</h2>
	<input type="text" bind:value={texto}>
	<p>texto : {texto}</p>

	<h2>Number</h2>
	<input type="number" bind:value={numero}>
	<p>numero : {numero}</p>

	<h2>Rango</h2>
	<input type="range" bind:value={rango} min=0 max=10>
	<p>rango : {rango}</p>

	<h3>checkbox</h3>
	<input type="checkbox" bind:checked={check}>
	Aceptar politicas de la empresa
	<button disabled={!check}>Enviar</button>
	<p>checkbox : {check}</p>

	<h3>Array de frutas</h3>
	{#each frutas as fruta}
		<br>
		<input type="radio" value={fruta} bind:group={radio}>
		{fruta}
	{/each}
	<p>fruta: {radio}</p>

	<h3>Multiples opciones</h3>
	{#each frutas as fruta}
		<br>
		<input type="checkbox" value={fruta} bind:group={arrayResultado}>
		{fruta}
	{/each}
	<p>array resultado: {arrayResultado}</p>

</div>

