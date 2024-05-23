<script lang="ts">
	import IconEnkode from '$lib/images/IconEnkode.png';
	import  {windowWidth}  from '../components/Width';
    import { onDestroy } from 'svelte';

	let width: number;
	const unsubscribe = windowWidth.subscribe((value) => (width = value));

	onDestroy(() => {
	unsubscribe();
	});

	export let title = 'Nuvix - Desarrollo de Sistemas SaaS & Software a medida';
	export let description =
		'Nuvix - Somos una empresa de desarrollo de software que se enfoca en dar soluciones SaaS para que empresas puedan tener mejor funcionamiento.';
	export let url = 'https://nuxiv.vercel.app';
	// export let image = './icon.jpg
</script>

<svelte:head>
	<title>{title}</title>
	<meta name="description" content={description} />
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />

	<meta property="og:title" content={title} />
	<meta property="og:description" content={description} />
	<meta property="og:type" content="website" />
	<meta property="og:url" content={url} />
	<!-- <meta property="og:image" content={image} /> -->

	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content={title} />
	<meta name="twitter:description" content={description} />
	<!-- <meta name="twitter:image" content={image} /> -->
</svelte:head>


<div class=" bg-[#1C1C1C] h-full w-full">
	<header id="header" class=" z-10 bg-transparent sticky top-0 backdrop-blur-md">
		<nav class="flex justify-around items-center h-16 bg-transparent text-white pt-5 font-ESRebondGrotesqueTRIAL-Medium"
		>
			<div class="flex">
				<picture>
					<img src={IconEnkode} alt="Icon" class="size-52" >
				</picture>
			</div>
			{#if width > 1024}
				<ul class="flex list-none gap-4">
					<li><a href="/">Inicio</a></li>
					<li><a href="/">Servicios</a></li>
					<li><a href="/">Soluciones</a></li>
					<li><a href="/">Nosotros</a></li>
					<li><a href="/">Contacto</a></li>
				</ul>
				{:else}
					<div class="flex">
						<button  class="text-white">
							<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
							</svg>
						</button>
					</div>
			{/if}
		</nav>
	</header>

<slot></slot>

<footer>
    <div class="flex flex-col  lg:justify-between lg:flex-row lg:px-[5%] p-5">

        <picture class="flex justify-center">
            <div>
            <img src={IconEnkode} alt="" class="size-60">
            </div>
        </picture>

        <section class="flex flex-wrap justify-center gap-10 ">
           
            <div class="flex flex-col gap-3 max-w-[100px]">
                <h3 class="text-white">Casos de uso</h3>
                <ul class="flex flex-col gap-3 list-none text-white/50">
                    <li><a href="/">ChattyBot CLI</a></li>
                    <li><a href="/">ChattyBot Code</a></li>
                </ul>
            </div>
            <div class="flex flex-col gap-3 max-w-[100px]">
                <h3 class="text-white">Integración</h3>
                <ul class="flex flex-col gap-3 list-none text-white/50">
                    <li><a href="/">Web</a></li>
                    <li><a href="/">Vs Code</a></li>
                </ul>
            </div>
            <div class="flex flex-col gap-3 max-w-[100px]">
                <h3 class="text-white">Recursos</h3>
                <ul class="flex flex-col gap-3 list-none text-white/50">
                    <li><a href="/">Documentación</a></li>
                    <li><a href="/">Blog</a></li>
                    <li><a href="/">Registro de cambios</a></li>
                    <li><a href="/">Contáctanos</a></li>
                </ul>
            </div>
            <div class="flex flex-col gap-3 max-w-[100px]">
                <h3 class="text-white">Empresas</h3>
                <ul class="flex flex-col gap-3 list-none text-white/50">
                    <li><a href="/">Precios</a></li>
                    <li><a href="/">FAQ</a></li>
                    <li><a href="/">Acerca de</a></li>
                    <li><a href="/">Comunidad</a></li>
                </ul>
            </div>
            <div class="flex flex-col gap-3 max-w-[100px]">
                <h3 class="text-white">Cuentas</h3>
                <ul class="flex flex-col gap-3 list-none text-white/50">
                    <li><a href="/">Linkedin</a></li>
                    <li><a href="/">Instagram</a></li>
                    <li><a href="/">Twiter</a></li>
                </ul>
            </div>

        </section>
    </div>
</footer>

</div>