<script>
  import { Router, Route } from "svelte-routing";
  import NavLink from "./components/NavLink.svelte";
  import Home from "./routes/Home.svelte";
  // Used for SSR. A falsy value is ignored by the Router.
  export let url = "";
</script>
<Router {url}>
  <div class="container">
    <nav>
      <div class="navContainer">
        <div class="navTitle">
          <NavLink to="/">untitled <span style="padding-top:5px;">politics</span></NavLink>
        </div>
        <div class="navLinks">
          <NavLink to="/">Home</NavLink>
          <NavLink to="/essays">Essays</NavLink>
          <NavLink to="/authors">Authors</NavLink>
          <NavLink to="/about">About</NavLink>
        </div>
        <div class="navLinks login">
          <NavLink to="/login">Login</NavLink> or <NavLink to="/signup">Sign Up</NavLink>
        </div>
      </div>
    </nav>
    <div class="pageContainer">
      <Route path="/" component={Home} />
    </div>
  </div>
  <div class="footer">copyright © {new Date().getFullYear()} untitled politics</div>
</Router>
