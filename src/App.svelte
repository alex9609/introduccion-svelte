<script>
	let contador = 0;
	let textColor = 'text-primary'
	
	const aumentar = () => {
		contador ++
		/*
		if(contador > 5){
			textColor = 'text-danger'
		}*/
	}
	const reiniciar = () => {
		contador = 0
		
		//textColor = 'text-primary'
	}

	//Declaracion reactiva
	$: if(contador > 5){
		textColor = 'text-danger'
	}else{
		textColor = 'text-primary'
	}

	$: doble =  contador * 2
	$: mensaje = contador > 5 ? 'Es mayor a 5' : 'Es menor a 5'


</script>

<main>
	<h1 class={textColor}>Counter: {contador}</h1>

	<h2>{mensaje}</h2>

	<h3>Doble {doble}</h3>
	<button on:click={aumentar}>Aumentar</button>

	<button on:click={reiniciar}>reiniciar</button>
</main>

<style>
	.text-primary{
		color:blueviolet;
	}

	.text-danger{
		color: orangered;
	}

</style>