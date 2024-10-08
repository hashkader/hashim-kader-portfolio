<script lang="ts">
	export let text = ""
	import  "../../Fonts/TestSohneMono-KraftigKursiv-BF663d89ccea359.otf" 
</script>

<button>
{text.toUpperCase()}
</button>

<style>
	button{
		font-family: 'TestSohneMono-KraftigKursiv-BF663d89ccea359';
		background-color: #1e1e1e11;
		font-weight: 10000;
		padding: 8px;
		border: none;
		height: 30px;
		border-radius:2px;
	}

</style>