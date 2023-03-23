<script>

    import { navigate } from 'svelte-routing'
    import { UserStore } from '../stores'

    export let params = {name: 'Usuario'}
    export let query = {}

    function showUser() {
        UserStore.set({
            name: 'default',
            ...params, 
            ...query
        })
        navigate('/user')
    }   

</script>

<h1>Users { params.name }</h1>

<button on:click={() => showUser()}>Ver Usuario</button>