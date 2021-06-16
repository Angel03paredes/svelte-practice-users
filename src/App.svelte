<script>
  import Home from "./pages/Home.svelte";
  import About from "./pages/About.svelte";
  import "../node_modules/bootswatch/dist/materia/bootstrap.css";

  import { Router, Route, Link } from "svelte-navigator";
</script>

<Router primary={false}>
  <header>
    <nav class="navbar navbar-expand-sm navbar-dark bg-dark ">
      <div class="container">
        <Link class="navbar-brand" to="/">Svelte</Link>

        <ul class="navbar-nav mr-auto">
          <li class="nav-item ">
            <Link class="nav-link" to="/">Home</Link>
          </li>
          <li class="nav-item ">
            <Link class="nav-link" to="/about">About</Link>
          </li>
        </ul>
      </div>
    </nav>
  </header>

  <main class="p-5">
    <Route path="/">
      <Home />
    </Route>

    <Route path="/about">
      <About />
    </Route>
  </main>
</Router>

<style>
</style>
