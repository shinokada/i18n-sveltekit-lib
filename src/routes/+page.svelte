<script>
  import { i, language, languages, switchLanguage } from '@inlang/sdk-js'
	import { Alert } from 'flowbite-svelte';
  console.log(language) // => e.g 'en'
  import { Mycomponent } from '$lib'
  async function switchLanguageToEnglish() {
		console.log('switching language to English ...')
		await switchLanguage('en')
		console.log('... language switched to English')
	}
  async function switchLanguageToGerman() {
		console.log('switching language to Japanese ...')
		await switchLanguage('de')
		console.log('... language switched to Japanese')
	}
</script>

<h1 class="text-4xl">Welcome to SvelteKit</h1>
<h2 class="text-3xl">{i('intro')}</h2>
<div class="p-8">
	<Alert>
		<span class="font-medium">Info alert!</span> Change a few things up and try submitting again.
	</Alert>
</div>
<Mycomponent name="Joe" />
<ul>
	{#each languages as language}
		<li>{language}</li>
	{/each}
</ul>

<button on:click={switchLanguageToEnglish}>
	Show page in English
</button>

<button on:click={switchLanguageToGerman}>
	Show page in German
</button>

<p>Flowbite
  {i('welcome')}
</p>