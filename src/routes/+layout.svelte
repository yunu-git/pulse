<script lang="ts">
  import '../app.css';
  import {SidebarInset, SidebarProvider, SidebarTrigger} from '$lib/components/ui/sidebar';
  import AppSidebar from '$lib/components/app-sidebar.svelte';
  import AppHeader from '$lib/components/app-header.svelte';

  let {children} = $props();
</script>

<SidebarProvider>
  <AppSidebar/>
  <SidebarInset>
    <AppHeader/>
    <div class="flex flex-1 flex-col gap-4 p-4">
      {@render children?.()}
    </div>
  </SidebarInset>
</SidebarProvider>
