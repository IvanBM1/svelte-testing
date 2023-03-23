<script>

    import { Router, Route } from 'svelte-routing'
    import QueryString from 'query-string'
    
    import UsersView from './$views/users.view.svelte'
    import UserView from './$views/user.view.svelte'
    import HomeView from './$views/home.view.svelte'
    import IndexView from './$views/index.view.svelte'
    import V404View from './$views/404.view.svelte'

    function isLogin() {
        return true
    }

    function getQuery(location) {
        return QueryString.parse(location.search || '')
    }

</script>

<Router>

    <Route path="*" component={ V404View } />
    
    {#if isLogin()} 

        <Route path="users/:name" let:params let:location>
            <UsersView { params } query={ getQuery(location) } />
        </Route>

        <Route path="users" component={ UsersView } />
        <Route path="user" component={ UserView } />

        <Route path="home" component={ HomeView } />
    {/if}

    <Route path="/" component={ IndexView } />

</Router>