<script>

    import { onMount } from 'svelte'
    import { navigate } from 'svelte-routing'
    import { UserStore } from '../stores'

    onMount(() => {
        if(!$UserStore)
            return navigate('/users')
    })    

</script>

{#if $UserStore}
    <table>
        <tbody>
            <tr>
                <th>Nombre</th>
                <th>{ $UserStore.name }</th>
            </tr>
            <tr>
                <th>Apellido</th>
                <th>{ $UserStore.last }</th>
            </tr>
            <tr>
                <th>Edad</th>
                <th>{ $UserStore.age }</th>
            </tr>
        </tbody>
    </table>
{/if}