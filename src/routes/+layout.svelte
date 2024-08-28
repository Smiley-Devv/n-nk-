<script>
	import '../app.css'; // Impor berkas CSS
	import { dev } from '$app/environment';
	import { inject } from '@vercel/analytics';

	inject({ mode: dev ? 'development' : 'production' }); // Inisialisasi Analytics
</script>

<slot />
