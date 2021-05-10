<script>
	import About from "./components/About.svelte"
	import Text from "./components/Text.svelte"
	import Person from "./components/Person.svelte"
	import Skills from "./components/Skills.svelte"
	import Input from "./components/Input.svelte"
	import Photos from "./components/Photos.svelte"
	export let name;
	export let lastName;
	export let twitter;
	let svelteLogo = "https://arepa.s3.amazonaws.com/svelte-logo.png";

	const data = {
		name:"Juan",
		lastName:"Fuentes",
		twitter:"John024x"
	}
</script>

<main>
	<h1>Hello {name} {lastName}!</h1>
	<About />
	<Text />
	<Text anotherText="Twitter:"/>
	<Person {...data}/>
	<Skills />
	<Input />
	<Photos />
	<img src={svelteLogo} alt="Sveltelogo">
</main>

<style>
	:global(body){
		background-color: rgb(239, 245, 223);
		color: black;
	}
	:global(body.dark-mode){
		background-color: rgb(22, 22, 21);
		color: white;
	}
	:global(:root){
		--theme-color: rgb(231, 139, 231);
	}
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
	main img{
		width:30%;
	}
	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>