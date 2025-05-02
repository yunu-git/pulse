<script lang="ts">
  import {Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle} from '$lib/components/ui/card';
  import {Button} from '$lib/components/ui/button';
  import {Check} from '@lucide/svelte';

  let {notifications}: { notifications: NotificationParams[] } = {
    notifications: [
      {
        title: "Your call has been confirmed.",
        timestamp: "1 hour ago"
      },
      {
        title: "You have a new message!",
        timestamp: "1 hour ago"
      },
      {
        title: "Your subscription is expiring soon!",
        timestamp: "2 hours ago"
      }
    ]
  };
</script>

<Card>
  <CardHeader>
    <CardTitle>Notifications</CardTitle>
    <CardDescription>You have {notifications.length} unread notifications.</CardDescription>
  </CardHeader>
  <CardContent class="grid gap-4">
    <div>
      {#each notifications as notification, idx (idx)}
        <div
          class="mb-4 grid grid-cols-[25px_1fr] items-start pb-4 last:mb-0 last:pb-0"
        >
          <span class="flex size-2 translate-y-1 rounded-full bg-sky-500"></span>
          <div class="space-y-1">
            <p class="text-sm font-medium leading-none">
              {notification.title}
            </p>
            <p class="text-muted-foreground text-sm">
              {notification.timestamp}
            </p>
          </div>
        </div>
      {/each}
    </div>
  </CardContent>
  <CardFooter>
    <Button class="w-full">
      <Check/>
      Mark all as read
    </Button>
  </CardFooter>
</Card>