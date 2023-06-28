<script lang="ts">
    import logo from '$lib/assets/Logo.svg'
    import logoName from '$lib/assets/Logo-Name.svg'

    let expanded = false;

    const closeOnClick = ()=>{expanded = false}

</script>

<nav>
    <div class="logo">
        <a href="/">
            <img src="{logoName}" alt="company logo">
        </a>
    </div>
    <button 
        class="nav-toggle {expanded?'open':''}"
        on:click={()=>{expanded=!expanded}}
    >
        <span class="sr-only">Menu</span>
        <span class="line line-1"></span>
        <span class="line line-2"></span>
        <span class="line line-3"></span>
    </button>
    <ul class="sections {expanded?'expanded':''}">
        <li>
            <a href="#products" on:click={closeOnClick}>Our Offerings</a>
        </li>
        <li>
            <a href="#sevices" on:click={closeOnClick}>Our Services</a>
        </li>
        <li>
            <a href="#locations" on:click={closeOnClick}>Our Locations</a>
        </li>
        <li>
            <a href="#contact" on:click={closeOnClick}>Contact Us</a>
        </li>
    </ul>
</nav>

<style>
    nav {
        position: sticky;
        top: 0;
        max-height: 10vh;
        padding: 0 1rem;
        display: flex;
        align-items: center;
        justify-content: space-between;
        background: linear-gradient(135deg, #000000, #0e0d0f, #030303);
    }
    .logo {
        margin: 2rem 0;
        max-width: 200px;
    }
    .logo img {
        max-width: 100%;
    }
    nav .sections {
        display: flex;
        gap: 3.5rem;
        list-style: none;
        z-index: 1000;
    }
    nav .sections a {
        font-weight: 500;
        text-transform: uppercase;
        text-decoration: none;
    }
    .nav-toggle {
        display: none;
    }
    @media (max-width : 920px) {
        nav {
            max-height: 10vh;
        }
        nav .logo {
            margin: 1.5rem .5rem;
        }
        nav .logo img{
            max-width: 200px;
        }
        nav .sections {
            position: fixed;
            inset: .7% 0 .7% 30%;
            flex-direction: column;
            padding: min(30vh, 25rem) 2rem;
            background: rgba(44, 44, 44, 0.6);
            backdrop-filter: blur(1rem);
            box-shadow: 0 0 5px 5px rgba(0, 0, 0, 0.5);
            border-radius: var(--radius-md) 0 0 var(--radius-lg);
            transform: translateX(110%);
            transition: transform 300ms cubic-bezier(0.39, 0.575, 0.565, 1);
        }
        nav .sections.expanded {
            transform: translateX(0%);
        }
        .nav-toggle {
            position: absolute;
            display: flex;
            flex-direction: column;
            gap: 2px;
            align-items: center;
            justify-content: center;
            width: 2rem;
            aspect-ratio: 1;
            top: 1.35rem;
            right: 1rem;
            cursor: pointer;
            z-index: 9999;
        }
        .line {
            width: 60%;
            height: 3px;
            background: white;
            transition: .3s ease;
        }
        .nav-toggle.open .line {
            background: crimson;
        }
        .nav-toggle.open .line-1 {
            transform: translate(20%, 50%);
            rotate: 45deg;
        }
        .nav-toggle.open .line-3 {
            transform: translate(30%, -110%);
            rotate: -45deg;
        }
        .nav-toggle.open .line-2 {
            opacity: 0;
        }
    }
</style>