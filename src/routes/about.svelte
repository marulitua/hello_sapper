<svelte:head>
	<title>About</title>
</svelte:head>

<h1>About this site</h1>

<p>This is the 'about' page. There's not much here.</p>

<p>{ value }</p>

<button on:click={ add }> Increase </button>

<script>
import wasmInstantiate from "./../rust_src/src/lib.rs";

let value = 0;

var Buffer = require("buffer").Buffer;

let importObject;

/*
async function increment(a) {
	const { instance } = await wasm();
	return instance.exports;
}
*/

wasmInstantiate(importObject | undefined).then(instance => {
  console(instance.exports.add(1, 2)); // 3
});

function add() {
	console.log('add in js');
	/*
	increment()
		.then(({ add }) => {
			console.log(add(value));
		});
	*/
}

</script>
