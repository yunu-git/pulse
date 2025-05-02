<script lang="ts">
  import { invoke } from "@tauri-apps/api/core";
  import {Button} from '$lib/components/ui/button/index';
  import {Alert, AlertDescription, AlertTitle} from '$lib/components/ui/alert/index.js';

  let name = $state("");
  let greetMsg = $state("");

  async function greet(event: Event) {
    event.preventDefault();
    // Learn more about Tauri commands at https://tauri.app/develop/calling-rust/
    greetMsg = await invoke("greet", { name });
  }
</script>

<div class="container">
  <Alert>
    <AlertTitle>Hello Bro</AlertTitle>
    <AlertDescription>Some sort of description</AlertDescription>
  </Alert>
  <Button>Yes</Button>
</div>
