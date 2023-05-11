<script>
  import { i, language, languages, switchLanguage } from '@inlang/sdk-js'
	import { Alert, Button, SpeedDial, SpeedDialButton } from 'flowbite-svelte';
	import Us from './utils/Us.svelte'
	import De from './utils/De.svelte'
	import Ja from './utils/Ja.svelte'
  console.log(language) // => e.g 'en'
  import { Mycomponent } from '$lib'
  async function switchLanguageToEnglish() {
		console.log('switching language to English ...')
		await switchLanguage('en')
		console.log('... language switched to English')
	}
  async function switchLanguageToGerman() {
		console.log('switching language to German ...')
		await switchLanguage('de')
		console.log('... language switched to German')
	}
	async function switchLanguageToJapanese() {
		console.log('switching language to Japanese ...')
		await switchLanguage('ja')
	}
	let btnDefaultClass = 'w-24 h-24 shadow-sm'
</script>

<h1 class="text-4xl">Welcome to SvelteKit</h1>
<h2 class="text-3xl">{i('intro')}</h2>
<div class="p-8">
	<Alert>
		<span class="font-medium">Language: {language}</span> 
	</Alert>
</div>

<h3 class="text-2xl">Languages</h3>
<ul>
	{#each languages as language}
		<li>{language}</li>
	{/each}
</ul>

<Button on:click={switchLanguageToEnglish} color='blue'>
	Show page in English
</Button>

<Button on:click={switchLanguageToGerman}>
	Show page in German
</Button>

<Button on:click={switchLanguageToJapanese} color="red">
	Show page in Japanese
</Button>


<p>
  {i('welcome')}
</p>

<SpeedDial defaultClass="absolute right-6 bottom-6" trigger='click'>
	<SpeedDialButton name="English" size="xs">
			<Us on:click={switchLanguageToEnglish}/>
	</SpeedDialButton>
	<SpeedDialButton name="German" size="xs">
			<De on:click={switchLanguageToGerman}/>
	</SpeedDialButton>
	<SpeedDialButton name="Japanese" size="xs">
			<Ja on:click={switchLanguageToJapanese} />
	</SpeedDialButton>
</SpeedDial>