<script>
  import { onMount } from 'svelte';
  
  onMount(async () => {
    const script = document.createElement('script');
    script.src = 'https://cdn.jsdelivr.net/npm/@sveltia/cms/dist/sveltia-cms.js';
    script.async = true;
    script.onload = () => {
      if (typeof window.SveltiaCMS !== 'undefined') {
        window.SveltiaCMS.init({
          config: {
            backend: {
              name: 'github',
              repo: 'kaipestudio/bp04-sveltekit',
              branch: 'main',
            },
            publish_mode: 'editorial_workflow',
            media_folder: 'static/images/uploads',
            public_folder: '/images/uploads',
            collections: [
              {
                name: 'servicos',
                label: 'Serviços',
                folder: 'src/content/servicos',
                create: true,
                slug: '{{slug}}',
                fields: [
                  { label: 'Título', name: 'title', widget: 'string' },
                  { label: 'Descrição', name: 'description', widget: 'text' },
                  { label: 'Ícone', name: 'icon', widget: 'string', required: false },
                  { label: 'Ordem', name: 'order', widget: 'number', default: 0 },
                ],
              },
            ],
          },
        });
      }
    };
    document.body.appendChild(script);
  });
</script>

<svelte:head>
  <title>CMS - SvelteKit</title>
</svelte:head>

<div class="min-h-screen bg-gradient-to-br from-slate-50 to-purple-50 p-8">
  <div class="max-w-6xl mx-auto">
    <div class="bg-white rounded-2xl shadow-xl p-6 mb-6">
      <h1 class="text-3xl font-bold text-gray-900">⚙️ CMS</h1>
      <p class="text-gray-600">Gerencie o conteúdo do seu site</p>
    </div>
    <div id="sveltia-cms" class="bg-white rounded-2xl shadow-xl overflow-hidden"></div>
  </div>
</div>