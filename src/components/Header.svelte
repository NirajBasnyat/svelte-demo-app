<script>
 	import {Link} from 'svelte-routing';

	let src = 'favicon.png';
</script>

<div>
	<header
		class="d-flex flex-wrap align-items-center justify-content-center justify-content-md-between px-5 border-bottom"
	>
		<Link to="/" class="d-flex align-items-center col-md-3 mb-md-0 text-dark text-decoration-none">
			<img {src} alt="logo" height="70px" width="70px" />
		</Link>

		<ul class="nav col-12 col-md-auto mb-2 justify-content-center mb-md-0">
			<li><Link to="/login" class="nav-link px-2 link-secondary">Login</Link></li>
		</ul>
	</header>
</div>


