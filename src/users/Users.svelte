<script lang="ts">
import Card from "../shared/card/Card.svelte";
import UserCard from "./UserCard.svelte";
import type { UserType } from "./utils/types";

  const getUsers = async (): Promise<UserType[]> => {
    const response = await fetch('https://api.github.com/users');
    const users = await response.json();

    if (response.ok) {
      return users;
    } else {
      throw new Error(users);
    }
  }

   $: allUsersPromise = getUsers();
</script>

<section >
    {#await allUsersPromise then users}
    {#each users as user}
      <div class="cursor-pointer">
        <Card>
          <UserCard {...{user}}/>
        </Card>
      </div>
    {/each}
  {/await}
</section>

<style>
  section {
    border: 1px solid #c7baba;
    margin: 5px;
    padding: 10px;
  }

  .cursor-pointer {
    cursor: pointer;
  }
 </style>
