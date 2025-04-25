<script lang="ts">
  import Counter from "./lib/Counter.svelte";
</script>

<main
  class="min-h-screen bg-gradient-to-br from-gray-900 to-gray-800 flex items-center justify-center p-4"
>
  <div
    class="max-w-md w-full bg-white/10 backdrop-blur-lg rounded-xl shadow-2xl p-8 space-y-6"
  >
    <h1 class="text-4xl font-bold text-center text-white">Svelte FiveM NUI</h1>
    <div class="flex justify-center">
      <Counter />
    </div>
  </div>
</main>
