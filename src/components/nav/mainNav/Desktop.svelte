<script>
  import { Link } from 'yrv';
  import Icon from 'svelte-awesome';
  import { plus } from 'svelte-awesome/icons';

  import { Cart } from '../../../elements/svgs';
  import UserProfile from '../_UserProfile.svelte';
  import links from './links';
</script>

<div class="hidden md:flex md:items-center md:justify-between text-gray-500">
  <div class="md:flex md:ml-10 md:pr-4">
    {#each links as l}
      <Link
        href="{l.href}"
        class="ml-4 px-3 py-2 font-medium text-sm text-gray-500  rounded-md
        hover:text-white hover:bg-that-blue focus:outline-none
          focus:text-white focus:bg-that-blue
        
        transition duration-150 ease-in-out"
      >
        <div class="flex items-center">
          <svg class="h-5" fill="currentColor" viewBox="0 0 20 20">
            <path d="M11 0h3L9 20H6l5-20z"></path>
          </svg>
          <span>{l.text}</span>
        </div>
      </Link>
    {/each}
  </div>

  <div class="flex items-center">
    <div
      class="ml-4 p-1 rounded-full  hover:text-white hover:bg-thatBlue-500 focus:text-white"
    >
      <Link href="/orders/summary">
        <Cart />
      </Link>
    </div>

    <div
      class="ml-4 p-1 rounded-full  hover:text-white  hover:bg-thatBlue-500 focus:text-white"
    >
      <Link href="/activities/create">
        <Icon data="{plus}" class="h-8 w-8" />
      </Link>
    </div>

    <div
      class="ml-4 p-1 rounded-full md:flex text-that-orange hover:text-thatOrange-500"
    >
      <UserProfile />
    </div>
  </div>
</div>
