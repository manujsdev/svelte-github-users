
<script lang="ts">
  import type { UserType } from "./utils/types";
  export let user: UserType = undefined;
</script>


<div class="flex">
  <img class="rounded-full" src={user.avatar_url} alt="avatar" />
  <p class="font-bold">{user.login}</p>
</div>

<style>
  .flex {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .rounded-full {
    border-radius: 50%;
    width: 7em;
    margin-right: 27px;
  }
 
  .font-bold {
    font-weight: bolder;
  }
</style>
