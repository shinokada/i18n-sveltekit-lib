<script>
  import { i, language, languages, switchLanguage } from '@inlang/sdk-js'
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

<h1>Welcome to SvelteKit</h1>
<h2>{i('intro')}</h2>
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