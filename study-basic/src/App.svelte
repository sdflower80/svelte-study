<script>
	import BootstrapModal from "./bootstrap/BootstrapModal.svelte";
	export let name;

	let string = `this string contains some <strong>HTML!!!</strong>`;

	document.addEventListener("DOMContentLoaded", function(){

	});
</script>

<main>
	<!-- 변수 처리 -->
	<h1>Hello {name.toUpperCase()}!</h1>

	<!-- HTML 파싱을 허용하게 한다. -->
	<p>{@html string}</p>

	<BootstrapModal/>
</main>

<style>
</style>