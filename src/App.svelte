<script>
	const cursos = ['html','css','js']
	let numeros = [2,5,7,10,12]

	const agregarNumero = () => {
		let num = Math.floor(Math.random()*(20 -1))+1;
		console.log(num)
		/*numeros.push(num)
		Los 3 puntos antes del array indica que vamos a copiar los valores del array
		*/
		numeros = [...numeros,num]
	}
</script>

<main class="container">
	<h1>Cursos</h1>
	<ul>
		{#each cursos as curse, index}
			 <li>{index +1} - {curse}</li>
		{/each}
	</ul>

	
	{#if numeros.length > 5}
		 <!-- Condicional if -->
		 <h3>Agregaste más de 5 numeros </h3>
		 {:else}
		 <button on:click={agregarNumero} class="btn btn-primary">Agregar número</button>		 
	{/if}
	<ul>
		<p>Números</p>
		{#each numeros as num}
			 <li>{num}</li>
		{/each}
	</ul>

</main>
