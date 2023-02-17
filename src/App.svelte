<script lang="ts">
  import svelteLogo from './assets/svelte.svg'
  import Counter from './lib/Counter.svelte'
  import FeedbackList from "./components/FeedbackList.svelte";

  let firstName = 'Hardey'
  let lastName = 'Santoso'
  let shouldShow = false
  let list = [
    { id: 1, name: 'Hardey', age: 20 },
    { id: 2, name: 'Santoso', age: 20 },
  ]
  $: fullName = `${firstName} ${lastName}`

  let feedback = [
    { "id": 1, "rating": 8, "text": "Great product, highly recommended!" },
    { "id": 2, "rating": 7, "text": "Good quality, but could be a bit cheaper." },
    { "id": 3, "rating": 9, "text": "Excellent service, fast shipping!" },
    { "id": 4, "rating": 4, "text": "Product arrived damaged, disappointed." },
    { "id": 5, "rating": 6, "text": "Decent product, could be better." },
    { "id": 6, "rating": 10, "text": "Absolutely love this product, exceeded my expectations!" },
    { "id": 7, "rating": 3, "text": "Poor quality, wouldn't recommend." },
    { "id": 8, "rating": 5, "text": "Average product, nothing special." },
  ]


  const onClick = () => {
    firstName = 'something different'
    shouldShow = !shouldShow
    const maxId = Math.max(...list.map((item) => item.id))
    list = [...list, {id: maxId+1, name: 'Hardey', age: 20}]
  }
</script>

<main class="container">
  <!--{#if shouldShow}-->
  <!--    <h1>Hi {firstName} {lastName}</h1>-->
  <!--  else-->
  <!--{/if}-->
  <!--{#each list as item (item.id)}-->
  <!--  <p>{item.id}. {item.name} is {item.age} years old</p>-->
  <!--{/each}-->

  <FeedbackList {feedback}></FeedbackList>

</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
