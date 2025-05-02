<script lang="ts">
  import { invoke } from "@tauri-apps/api/core";
  import NotificationCard from "$lib/components/notification-card.svelte"
  let name = $state("");
  let greetMsg = $state("");

  async function greet(event: Event) {
    event.preventDefault();
    // Learn more about Tauri commands at https://tauri.app/develop/calling-rust/
    greetMsg = await invoke("greet", { name });
  }
</script>

<div class="grid auto-rows-min gap-4 md:grid-cols-3">
  <NotificationCard/>
</div>
