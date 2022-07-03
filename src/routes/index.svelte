<script lang="ts">
    import IoMdMenu from 'svelte-icons/io/IoMdMenu.svelte';
    import Card from '../components/Card.svelte';
    import Contato from '../components/Contato.svelte';
    import FaLinkedin from 'svelte-icons/fa/FaLinkedin.svelte';
    import FaDiscord from 'svelte-icons/fa/FaDiscord.svelte';
    import FaTelegramPlane from 'svelte-icons/fa/FaTelegramPlane.svelte';

    import {fly} from 'svelte/transition'

    let services: HTMLElement;
    let contatos: HTMLElement;

    let showMenu = false;

    function scrollToServices(){
        services.scrollIntoView({behavior: 'smooth'});
        showMenu = false;
    }
    function scrollToContatos(){
        contatos.scrollIntoView({behavior: 'smooth'});
        showMenu = false;
    }
    
    function toggleMenu(){
        showMenu = !showMenu;
    }
</script>
<header class="fixed top-0 w-full z-20">
    <nav class="navbar bg-base-200 lg:justify-between">
        <button class="btn btn-square btn-ghost lg:hidden" on:click={toggleMenu}>
            <IoMdMenu />
        </button>
        <p class="text-xl m-auto flex justify-center lg:m-0">Aerton.dev</p>
        <div class="w-8 lg:hidden" />
        <div class="menu menu-horizontal rounded-lg p-0 hidden lg:flex">
            <li><button on:click={scrollToServices}>Serviços</button></li>
            <li><button on:click={scrollToContatos}>Contatos</button></li>
        </div>
    </nav>
    {#if showMenu}
        <ul class="menu bg-base-100 -translate-y-1" transition:fly={{x: -500, duration: 200}}>
            <li><button on:click={scrollToServices}>Serviços</button></li>
            <li><button on:click={scrollToContatos}>Contatos</button></li>
        </ul>
    {/if}
</header>

<section 
    class="hero mt-14 pt-10 pb-10 lg:pb-40 lg:pt-40" 
    style="background-image: url(/anthony-garand-5sT07dJl65s-unsplash.jpg);"
>
    <div class="lg:hero-content text-white">
        <h1 class="text-5xl lg:text-9xl">AERTON</h1>
        <div>
            <h3 class="max-w-xs mb-4">Desenvolvimento de sites, aplicativos mobile e desktop, games e aplicações VR.</h3>
            <button class="btn btn-primary" on:click={scrollToServices}>Conheça os serviços </button>
        </div>
    </div>
</section>

<section class="flex flex-col items-center pt-8" bind:this={services}>
    <h1 class="text-4xl mb-6">Serviços</h1>
    <div class="flex flex-col lg:flex-row pl-4 pr-4 lg:pl-10 lg:pr-10 gap-4">
        <Card 
            img="/igor-miske-Px3iBXV-4TU-unsplash.jpg" 
            title="Websites" 
            description="Desenvolvimento fullstack de sites rápidos e responsivos."
        />
        <Card 
            img="/rami-al-zayat-w33-zg-dNL4-unsplash.jpg" 
            title="Aplicativos" 
            description="Desenvolvimento de aplicativos mobile e desktop utilizando tecnologias modernas."
        />
        <Card 
            img="/omid-armin-w0erZAfnkjg-unsplash.jpg" 
            title="Games" 
            description="Desenvolvimento de games para computadores, smartphones e navegadores."
        />
        <Card 
            img="/vinicius-amnx-amano-MvJezf8FT4o-unsplash.jpg" 
            title="Realidade Virtual" 
            description="Desenvolvimento de aplicativos em Realidade Virtual para desktop, Meta Quest e navegadores."
        />
    </div>
</section>

<footer class="mt-4 bg-base-300 p-4" bind:this={contatos}>
    <h1 class="text-xl mb-2">Contatos:</h1>
    <Contato 
        href="https://www.linkedin.com/in/aerton-castro-de-oliveira/" 
        text="in/aerton-castro-de-oliveira"
    >
        <FaLinkedin />
    </Contato>
    <Contato 
        href="https://t.me/aertoncastro" 
        text="@aertoncastro"
    >
        <FaTelegramPlane />
    </Contato>
    <Contato 
        text="Cafezinho#0059"
    >
        <FaDiscord />
    </Contato>
</footer>


<style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');
    h1{
        font-family: 'Montserrat', sans-serif;
    }
</style>