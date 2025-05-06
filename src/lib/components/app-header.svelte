<script lang="ts">
  import {SidebarTrigger} from '$lib/components/ui/sidebar';
  import {Separator} from '$lib/components/ui/separator';
  import {Breadcrumb, BreadcrumbItem, BreadcrumbList} from '$lib/components/ui/breadcrumb';
  import {BreadcrumbLink} from '$lib/components/ui/breadcrumb/index.js';
  //FIXME push onto state!
  // let {breadcrumbs}: {breadcrumbs: BreadcrumbParams[]} = $props();
  let {breadcrumbs}: {breadcrumbs: BreadcrumbParams[]} = {breadcrumbs: [{label: 'Home', href: '/'}]};

</script>

<header class="flex h-16 shrink-0 items-center gap-2 border-b px-4">
  <SidebarTrigger class="-ml-1 mr-1"/>
  <Separator orientation="vertical" class="mr-2 h-4"/>
  <Breadcrumb>
    <BreadcrumbList>
      <BreadcrumbList>
        {#each breadcrumbs as breadcrumb}
          <BreadcrumbItem class="hidden md:block">
            <BreadcrumbLink href={breadcrumb.href}>{breadcrumb.label}</BreadcrumbLink>
          </BreadcrumbItem>
        {/each}
      </BreadcrumbList>
    </BreadcrumbList>
  </Breadcrumb>
</header>