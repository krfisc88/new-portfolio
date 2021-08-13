<script>
  import Navigation from "./ui/Navigation";
  let windowWidth;
  const links = [
    { url: "/", title: "Home" },
    { url: "/", title: "Pricing" },
    { url: "/", title: "Contact" },
    { url: "/", title: "About" }
  ];

  const brand = {
    title: "FWD",
    url: "/"
  };
</script>
<svelte:window bind:innerWidth={windowWidth} />

<Navigation 
  {links}
  {brand}
  bind:windowWidth
/>

<!-- Color Scheme -->
<!-- https://coolors.co/f7ff0a-20a39e-ef5b5b-23001e-a4a9ad-ffffff -->