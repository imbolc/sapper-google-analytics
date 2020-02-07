<svelte:head>
    <script async src="https://www.googletagmanager.com/gtag/js?id={id}"></script>
</svelte:head>
<script>
    import { stores } from "@sapper/app"

    export let id

    if (typeof window !== "undefined") {
        window.dataLayer = window.dataLayer || []
        window.gtag = function gtag() {
            window.dataLayer.push(arguments)
        }
        window.gtag("js", new Date())
        window.gtag("config", id)
    }

    const { page } = stores();
    $: {
        if (typeof gtag !== "undefined"){
            window.gtag("config", id, {
                page_path: $page.path,
            });
        }
    }
</script>
