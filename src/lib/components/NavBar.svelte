<script lang="ts">
    import { page, url } from '$app/stores'
    import { signOut } from '$lib/user'
    import { user } from '$lib/user'
</script>
<nav class="h-14 bg-blue-900 w-screen mx-auto max-w-7xl sm:px-2 lg:px-2 shadow-sm" >
    <ul class="list-none h-full flex items-center justify-end gap-3">
        {#if $user}
            <li class="nav__item">
                <a rel="prefetch" href="/settings" class:active={new URL($page.url).pathname === '/settings'}>
						<i class="ion-gear-a" />
				</a>
            </li>
            <li class="nav__item">
                <a rel="prefetch" href="/home">
                    Home
                </a>
            </li>

            <li class="nav__item">
                <a rel="prefetch" href="/band_list">
                    Band lists
                </a>
            </li>

            <li class="nav__item">
                <a rel="prefetch" href="/band_registration">
                    Band registration
                </a>
            </li>

            <button class="" on:click={() => signOut()}>Sign Out</button>
        {:else}
            <li class="nav__item">
                <a rel="prefetch" href="/auth" title="Sign In">
                    Sign In
                </a>
            </li>
            <li class="nav__item">
                <a rel="prefetch" href="/auth?reg=true" title="Sign Up">
                    Sign Up
                </a>
            </li>
        {/if}
    </ul>
</nav>

<style lang="postcss">
</style>
