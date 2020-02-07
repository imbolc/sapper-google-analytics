# Google Analytics tracking for Sapper-based apps

It's not enough to just add Analytics code for SPA sites,
as it doesn't track client-side navigation. So we
have to pass navigation events manually and this component
does exactly this.

# Setup

Install the component:

```sh
npm i sapper-google-analytics
```

And add it to your `src/routes/_layout.svelte`:

```html
<GoogleAnalytics {stores} id={ga_measurment_id}/>

<script>
    import GoogleAnalytics from "sapper-google-analytics/GoogleAnalytics.svelte"
    import { stores } from "@sapper/app"

    let ga_measurment_id = "UA-SOMETHING"  // your analytics id
</script>
```
