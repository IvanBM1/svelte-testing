<script>

    import { navigate } from 'svelte-routing'

</script>

<h1>Home View</h1>
<button on:click={() => navigate('users')} >Usuarios</button>