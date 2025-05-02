<script lang="ts">
  import '../app.css';
  import {SidebarProvider, SidebarTrigger} from '$lib/components/ui/sidebar';
  import AppSidebar from '$lib/components/app-sidebar.svelte';
  let {children} = $props();
</script>

<SidebarProvider>
  <AppSidebar/>
  <main>
    <SidebarTrigger/>
    {@render children?.()}
  </main>
</SidebarProvider>
