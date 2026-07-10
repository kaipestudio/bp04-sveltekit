<script>
  // Svelte 5 - usa $state para reatividade
  let count = $state(0);
</script>

<div class="min-h-screen bg-gradient-to-br from-slate-50 to-blue-50 flex flex-col items-center justify-center p-4">
  <div class="max-w-2xl mx-auto text-center">
    <!-- Logo/Ícone -->
    <div class="text-6xl mb-6">🚀</div>
    
    <h1 class="text-5xl md:text-6xl font-bold text-gray-900 mb-4">
      Bem-vindo ao<br />
      <span class="bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-transparent">
        SvelteKit
      </span>
    </h1>
    <p class="text-xl text-gray-600 mb-12">
      SvelteKit + Tailwind + Sveltia CMS
    </p>
    
    <!-- Contador Bonito -->
    <div class="bg-white p-8 rounded-2xl shadow-xl border border-gray-100 max-w-md mx-auto">
      <div class="flex items-center justify-between mb-6">
        <h3 class="text-lg font-semibold text-gray-700">🧮 Contador</h3>
        <span class="text-xs bg-blue-100 text-blue-800 px-2 py-1 rounded-full">Interativo</span>
      </div>
      
      <div class="flex items-center justify-center gap-6">
        <button 
          onclick={() => count--}
          class="w-14 h-14 rounded-full bg-red-500 text-white text-2xl font-bold hover:bg-red-600 hover:scale-105 transition-all duration-200 shadow-lg hover:shadow-red-200 flex items-center justify-center"
        >
          −
        </button>
        
        <div class="text-center">
          <p class="text-6xl font-bold text-gray-800 tabular-nums">{count}</p>
          <p class="text-xs text-gray-400 mt-1">cliques</p>
        </div>
        
        <button 
          onclick={() => count++}
          class="w-14 h-14 rounded-full bg-green-500 text-white text-2xl font-bold hover:bg-green-600 hover:scale-105 transition-all duration-200 shadow-lg hover:shadow-green-200 flex items-center justify-center"
        >
          +
        </button>
      </div>
      
      <button 
        onclick={() => count = 0}
        class="mt-6 text-sm text-gray-400 hover:text-gray-600 transition-colors"
      >
        ↺ Resetar
      </button>
    </div>
    
    <!-- Links -->
    <div class="flex flex-wrap gap-4 justify-center mt-8">
      <a href="/admin" class="bg-blue-600 text-white px-6 py-3 rounded-lg hover:bg-blue-700 transition shadow-lg hover:shadow-blue-200">
        ⚙️ Acessar CMS
      </a>
    </div>
  </div>
</div>