<script lang="ts">
    import {Sidebar, SidebarMenuItem} from '$lib/components/ui/sidebar';
    import {
        SidebarContent,
        SidebarFooter,
        SidebarGroup, SidebarGroupContent,
        SidebarGroupLabel,
        SidebarHeader, SidebarMenuButton, SidebarRail
    } from '$lib/components/ui/sidebar/index.js';
  import {House} from '@lucide/svelte';
  const pages = [
    {
      title: "Home",
      url: "#",
      icon: House,
    }
  ];
  const year = new Date().getFullYear();
</script>

<Sidebar>
  <SidebarHeader>
    pulse
  </SidebarHeader>
  <SidebarContent>
    <SidebarGroup>
      <SidebarGroupLabel>Pages</SidebarGroupLabel>
      <SidebarGroupContent>
        {#each pages as page (page.title)}
          <SidebarMenuItem>
            <SidebarMenuButton>
              {#snippet child({props})}
                <a href={page.url} {...props}>
                  <page.icon/>
                  <span>{page.title}</span>
                </a>
              {/snippet}
            </SidebarMenuButton>
          </SidebarMenuItem>
        {/each}
      </SidebarGroupContent>
    </SidebarGroup>
  </SidebarContent>
  <SidebarFooter>
    pulse © {year}
  </SidebarFooter>
</Sidebar>