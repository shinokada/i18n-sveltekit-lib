<script>
  export let name = 'John'
  import classNames from 'classnames';
  export let btnDefaultClass = 'w-[52px] h-[52px] shadow-sm !p-2';
  let myClass;
  $: myClass = classNames(btnDefaultClass, $$props.class);
</script>

<p class={myClass}>Hello {name}!</p>