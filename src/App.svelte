<script>

    import { Router, Route } from 'svelte-routing'
    
    import UsersView from './$views/users.view.svelte'
    import HomeView from './$views/home.view.svelte'
    import IndexView from './$views/index.view.svelte'
    import V404View from './$views/404.view.svelte'

    function isLogin() {
        return false
    }

</script>

<Router>

    <Route path="*" component={ V404View } />
    
    <Route path="users/:userName" let:params>
        <UsersView userName={ params.userName } />
    </Route>

    <Route path="users" component={ UsersView } />
    <Route path="home" component={ HomeView } />

    <Route path="/" component={ IndexView } />

</Router>