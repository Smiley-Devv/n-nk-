<script>
	import 'aos/dist/aos.css';
	// @ts-ignore
	import AOS from 'aos';

	import { onMount } from 'svelte';
	/*
                            ੭﹕ARX ♥  ̊ ̟ ꒷꒦  💬  
  | 🍡 a discord moderation & music 24 / 7~
	*/

	console.log(
		'Made by Tragic In Bogor | https://hi-lrmn.is-a.dev/ | https://discord.gg/6EXgrmtkPX',
		'color: #e06c75'
	);
	$: screenWidth = 0;
	$: size0 = screenWidth <= 800 && screenWidth > 0;
	$: size1 = screenWidth <= 1250 && screenWidth > 800;
	$: size3 = screenWidth <= 3000 && screenWidth > 2000;
	let pagescrollY = 0;
	let elementOneMarginX = 0;
	let MouseX = 0;
	let MouseY = 0;
	let finalStyleOfMouseFollower = [
		'w-44',
		'h-44',
		'opacity-5',
		'from-neutral-400',
		'to-neutral-500',
		'rounded-full',
		'animate-pulse'
	].join(' ');
	let initStyleOfMouseFollower = [
		'w-40',
		'h-40',
		'opacity-10',
		'from-neutral-100',
		'to-neutral-300'
	].join(' ');
	onMount(() => {
		AOS.init();
		window.addEventListener('scroll', () => {
			pagescrollY = window.scrollY;
			if (pagescrollY < 1833) {
				elementOneMarginX = 10;
			} else {
				elementOneMarginX = size0
					? 200 - (pagescrollY - 1833) / 10
					: 100 - (pagescrollY - 1833) / 15;
				//140 - (pagescrollY - 1833) / 10;
			}
		});
		window.addEventListener('mousemove', (e) => {
			MouseX = e.clientX;
			MouseY = e.clientY;
		});
		screenWidth = window.innerWidth;
		size0 = screenWidth <= 800 && screenWidth > 0;
		size1 = screenWidth <= 1250 && screenWidth > 800;
		size3 = screenWidth <= 3000 && screenWidth > 2000;
		window.addEventListener('resize', () => {
			screenWidth = window.innerWidth;
			size0 = screenWidth <= 800 && screenWidth > 0;
			size1 = screenWidth <= 1250 && screenWidth > 800;
			size3 = screenWidth <= 3000 && screenWidth > 2000;
		});
		// when hover .card and buttons, change style of .mouseFollower
		const elements = [
			...document.querySelectorAll('.card'),
			...document.querySelectorAll('a'),
			...document.querySelectorAll('.commanditem'),
			...document.querySelectorAll('button')
		];
		const mouseFollower = document.querySelector('.mouseFollower');
		elements.forEach((element) => {
			element.addEventListener('mouseenter', () => {
				mouseFollower.classList.remove(...initStyleOfMouseFollower.split(' '));
				mouseFollower.classList.add(...finalStyleOfMouseFollower.split(' '));
			});
			element.addEventListener('mouseleave', () => {
				mouseFollower.classList.remove(...finalStyleOfMouseFollower.split(' '));
				mouseFollower.classList.add(...initStyleOfMouseFollower.split(' '));
			});
		});
	});
	let arrayOfFeatures = [
		{
			name: 'Scrobble ♥',
			style: 'from-pink-500 to-violet-500',
			description:
				"You can now connect your Last.fm account for automatic scrobbling whenever you play music."
		},
		{
			name: '24/7 ♪',
			style: 'from-orange-500 to-yellow-500',
			description: 'Be ♥ is a Discord bot that is always online and ready to serve you.'
		},
		{
			name: 'Stations ☾',
			style: 'from-red-800 to-orange-300',
			description:
				'lofi stations with different vibes like Study, Anime Live, Hardstyle.'
		},
		{
			name: 'Playlist ⚙',
			style: 'from-red-800 to-orange-300',
			description:
				'੭﹕ARX ♥ has a playlist system that allows you to add and remove songs from your playlist.'
		}
	];
	let liveText = '';
	let num = 0;
	let index = 0;
	setInterval(() => {
		if (index < arrayOfFeatures[num].name.length) {
			liveText = liveText + arrayOfFeatures[num].name[index];
			index++;
		} else {
			liveText = arrayOfFeatures[num].name;
		}
	}, 100);
	setInterval(
		() => {
			liveText = '';
			index = 0;
			num++;
			if (num >= arrayOfFeatures.length) num = 0;
		},
		7000,
		num
	);
</script>

<div
	class="mouseFollower {size0 &&
		'hidden'} fixed blur-3xl bg-gradient-to-r z-50 pointer-events-none {initStyleOfMouseFollower}"
	style="top: {MouseY}px; left: {MouseX}px; transform: translate(-50%, -50%); border-radius: 50%; transition: 0.1s linear"
/>
<header
	class="w-full h-16 p-5 {size0
		? 'pr-0 justify-center'
		: size1
		? 'pr-0 justify-center'
		: 'pr-56'} text-sm fixed z-10 text-neutral-400 flex justify-end items-center backdrop-blur-3xl"
	style="background-color: rgba(0,0,0,0.1)"
>
	<a
		class="mx-4 hover:text-neutral-200 {size0 && 'hidden'} hover-underline-animation"
		href="/invite"
	>
		Invite
	</a>
	<a
		class="mx-4 hover:text-neutral-200 {size0 && 'hidden'} hover-underline-animation"
		href="/discord"
	>
		Support
	</a>
	<a
		class="mx-4 hover:text-neutral-100 hover-underline-animation bg-clip-text text-transparent bg-gradient-to-r from-amber-700 to-blue-200 font-extrabold after:scale-x-100 after:origin-bottom-left after:bg-gradient-to-r after:from-amber-700 after:to-blue-500"
		href="/vote"
	>
		Vote for Be ♥
	</a>
	<a class="mx-4 hover:text-neutral-200" href="/">
		<img alt="logo" class="h-8 w-8" src="/beavatar1.png" />
	</a>
</header>

<section
	class="{size0
		? 'pt-16'
		: size1
		? 'pt-20'
		: size3
		? 'pt-64'
		: 'pt-24'} flex justify-start items-center flex-col text-center px-10"
>
	<h2
		class="{size0
			? 'text-lg'
			: 'text-2xl'} text-neutral-500 font-bold tracking-normal mt-32 bg-clip-text text-transparent bg-gradient-to-b from-neutral-100 to-neutral-400"
	>
		Upgrade your server with the
	</h2>
	<h1
		class="{size0
			? 'text-5xl leading-28'
			: size1
			? 'text-7xl'
			: 'text-8xl'} w-11/12 tracking-tighter font-extrabold mt-8 bg-clip-text text-transparent bg-gradient-to-b from-neutral-100 to-neutral-400"
		style="font-family: 'Inter', monospace"
	>
		Music
		<span class="divider">
			{#if size0 || size1}
				<br />
			{/if}
		</span>
		<span
			class="bg-clip-text pr-0.5 tracking-tighter text-transparent bg-gradient-to-r {arrayOfFeatures[
				num
			].style}"
			id="writer"
		>
			{liveText}
			<span
				style="animation: blink 2s linear infinite"
				class="bg-clip-text text-transparent bg-gradient-to-b from-neutral-200 to-neutral-400"
			>
				|
			</span>
		</span>
	</h1>
	<h2
		class="{size0
			? 'w-10/12 text-sm leading-5'
			: size1
			? 'w-6/12 text-xl leading-8'
			: 'w-4/12 text-xl leading-8'} text-neutral-500 tracking-wide mt-10"
		style="animation: blink1 7s linear infinite"
	>
		{arrayOfFeatures[num].description}
	</h2>
	<div class="mt-14 flex">
		<a
			class="text-white relative mx-3
		 rounded-lg z-1 bg-gradient-to-r from-neutral-100 to-neutral-300"
			href="/discord"
			style="padding: 1px"
		>
			<div
				class="flex tracking-wide text-sm justify-center z-1 rounded-lg items-center bg-neutral-700 w-full h-full px-8 py-2.5 relative hover:bg-transparent hover:text-neutral-950"
			>
				Join Discord
			</div>
		</a>
		<a
			class="text-white relative mx-3
		 rounded-lg z-1 bg-gradient-to-r {arrayOfFeatures[num].style}"
			href="/invite"
			style="padding: 1px"
		>
			<div
				class="absolute left-1/4 rounded-lg blur-xl opacity-30 w-16 h-16 bg-gradient-to-r {arrayOfFeatures[
					num
				].style}"
				style="z-index: 0; animation: spin 20s linear infinite; top: -14px;"
			/>
			<div
				class="flex tracking-wide text-sm justify-center z-1 rounded-lg items-center bg-neutral-950 w-full h-full px-8 py-2.5 relative hover:bg-transparent hover:text-neutral-950"
			>
				Invite Be ♥
			</div>
		</a>
	</div>
</section>
<section
	class="{size0 ? 'mt-20' : size1 ? 'mt-16' : 'mt-24'} flex justify-center flex-col items-center"
>
	<div class="{size0 ? 'mt-2 text-sm' : size1 ? 'mt-20' : 'mt-24'} mb-80 text-neutral-500">
		👇 Start exploring ARX ♥
	</div>
	<div
		class="grid {size0 ? 'grid-cols-1' : size1 ? 'grid-cols-2' : 'grid-cols-3'} w-max text-center"
	>
		<div
			data-aos={size0 ? 'none' : 'fade-up'}
			data-aos-anchor-placement={size0 ? 'none' : size1 ? 'center-bottom' : 'bottom-bottom'}
			data-aos-duration="500"
			class="card"
			style={size0 ? 'margin-top: -15rem' : 'margin-top: -10rem'}
		>
			<p
				class="text-4xl tracking-tighter my-5 font-extrabold bg-clip-text text-transparent bg-gradient-to-r from-green-500 to-teal-500"
			>
				Trust and Support.
			</p>
			<p class="desc-text">
				Trusted by servers and has a dedicated support team that is always ready to help asap.
			</p>
		</div>
		<div
			data-aos={size0 ? 'none' : 'fade-up'}
			data-aos-anchor-placement={size0 ? 'none' : size1 ? 'center-bottom' : 'bottom-bottom'}
			data-aos-duration="500"
			class="card mt-28"
			style="background: linear-gradient(180deg, rgba(255,255,255,4%), rgba(255,255,255,3%));"
		>
			<p
				class="text-4xl tracking-tighter my-5 font-extrabold bg-clip-text text-transparent bg-gradient-to-r from-orange-500 to-blue-500"
			>
				99% Uptime.
			</p>
			<p class="desc-text">
				ARX ♥ would never go down, it's always there for your server, 24/7, 365 days a year!
			</p>
		</div>
		<div
			data-aos={size0 ? 'none' : 'fade-up'}
			data-aos-anchor-placement={size0 ? 'none' : size1 ? 'center-bottom' : 'bottom-bottom'}
			data-aos-duration="500"
			class="card"
			style="margin-top: -10rem; opacity:0;{size0 || size1 ? 'display: none' : 'display: auto'}"
		/>
		<div
			data-aos={size0 ? 'none' : 'fade-up'}
			data-aos-anchor-placement={size0 ? 'none' : size1 ? 'center-bottom' : 'bottom-bottom'}
			data-aos-duration="500"
			class="card"
			style={size0 ? '' : 'margin-top: -10rem'}
		>
			<p
				class="text-4xl tracking-tighter my-5 font-extrabold bg-clip-text text-transparent bg-gradient-to-r from-violet-500 to-cyan-500"
			>
				Music.
			</p>
			<p class="desc-text">
				ARX♥ simple music system allows for smooth playback from multiple sources, filter and
				feature stay in the voice channel.
			</p>
		</div>
		<div
			data-aos={size0 ? 'none' : 'fade-up'}
			data-aos-anchor-placement={size0 ? 'none' : size1 ? 'center-bottom' : 'bottom-bottom'}
			data-aos-duration="500"
			class="card mt-28"
			style="background: linear-gradient(180deg, rgba(255,255,255,4%), rgba(255,255,255,3%));"
		>
			<p
				class="text-4xl tracking-tighter my-5 font-extrabold bg-clip-text text-transparent bg-gradient-to-r from-pink-500 to-red-500"
			>
				moderation.
			</p>
			<p class="desc-text">
				ARX uses new and improved moderation system to keep your guild from ghostpings Spams and Mention spamming!
			</p>
		</div>
		<div
			data-aos={size0 ? 'none' : 'fade-up'}
			data-aos-anchor-placement={size0 ? 'none' : size1 ? 'center-bottom' : 'bottom-bottom'}
			data-aos-duration="500"
			class="card"
			style={size0 ? '' : 'margin-top: -10rem'}
		>
			<p
				class="text-4xl tracking-tighter my-5 font-extrabold bg-clip-text text-transparent bg-gradient-to-r from-slate-500 to-pink-500"
			>
				Supports slash commands.
			</p>
			<p class="desc-text">
				In addition to using a prefix, ARX ♥ supports slash commands, allowing users to access and
				use commands by using a forward slash as a prefix.
			</p>
		</div>
	</div>
</section>

<section
	class="flex justify-start flex-col items-center px-5 text-center"
	data-aos={size0 ? 'none' : 'fade-up'}
	data-aos-anchor-placement="none"
	data-aos-duration="500"
>
	<div
		class="text-5xl text-neutral-500 font-bold tracking-normal mt-0 bg-clip-text text-transparent bg-gradient-to-b from-white to-neutral-400"
	>
		Be ♥ Support ?
	</div>
	<h2
		class="text-3xl text-neutral-500 font-bold tracking-normal mt-0 bg-clip-text text-transparent bg-gradient-to-b from-white to-neutral-400"
	>
		You're just one click away!
	</h2>

	<div
		class="mt-14 flex"
		data-aos={size0 ? 'none' : 'fade-up'}
		data-aos-anchor-placement="bottom-bottom"
		data-aos-duration="500"
	>
		<a
			class="text-white relative mx-3
		 rounded-lg z-1 bg-gradient-to-r from-neutral-100 to-neutral-300"
			href="https://www.patreon.com/mewwme"
			style="padding: 1px"
			target="_blank"
		>
			<div
				class="absolute left-1/4 rounded-lg blur-xl opacity-30 w-16 h-16 bg-gradient-to-r from-neutral-100 to-neutral-300"
				style="z-index: 0; animation: spin 20s linear infinite; top: -14px;"
			/>
			<div
				class="flex tracking-wide text-sm justify-center z-1 rounded-lg items-center bg-neutral-950 w-full h-full px-8 py-2.5 relative hover:bg-transparent hover:text-neutral-950"
			>
				Patreon
			</div>
		</a>
	</div>
</section>
<section
	class="footer-container flex justify-between items-center border-t-neutral-700 border-t mt-36 p-5 bg-neutral-800"
>
	<p class="text-neutral-400 text-xs tracking-wide leading-8">
		<a class="hover-underline-animation" href="https://discord.gg/6EXgrmtkPX" target="_blank"
			>Made with ♥ in Bogor</a
		>, by
		<a class="hover-underline-animation" href="https://hi-lrmn.is-a.dev/" target="_blank">L RMN</a>
	</p>
	<p class="text-neutral-400 text-xs tracking-wide leading-8">
		2023 - {new Date().getFullYear()} © <a href="/" class="hover-underline-animation"> Be ♥</a>. All rights reserved.
	</p>
	<div class="flex text-neutral-400 text-xs tracking-wide leading-8">
		<a class="mx-4 hover-underline-animation" href="/privacy">Privacy Policy</a>
		<a class="mx-4 hover-underline-animation" href="/termsofservice">Terms Of Service</a>
		<a
			class="mx-4 hover-underline-animation"
			href="https://top.gg/team/469616667718533120"
			target="_blank"
			rel="noopener noreferrer">Topgg</a
		>
	</div>
</section>
