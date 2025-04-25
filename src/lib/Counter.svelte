<script lang="ts">
  let count: number = $state(0);
  const increment = () => {
    count += 1;
  };
</script>

<button
  onclick={increment}
  class="px-6 py-3 bg-blue-600 hover:bg-blue-700 text-white font-medium rounded-lg transition-all duration-200 hover:scale-105"
>
  Contagem: {count}
</button>
