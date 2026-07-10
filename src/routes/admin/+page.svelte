<script>
  import { onMount } from 'svelte';
  
  onMount(async () => {
    const { default: SveltiaCMS } = await import('@sveltia/cms');
    
    SveltiaCMS.init({
      config: {
        backend: {
          name: 'github',
          repo: 'kaipestudio/bp04-sveltekit',
          branch: 'main',
        },
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
  });
</script>

<svelte:head>
  <title>CMS - SvelteKit</title>
</svelte:head>

<div class="min-h-screen bg-gray-50">
  <div id="sveltia-cms"></div>
</div>