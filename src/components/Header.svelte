<script>
    const menus = [
        {
            title: "Home",
            link: "#/"
        },
        {
            title: "About",
            link: "#/about"
        },
        {
            title: "Form",
            link: "#/form"
        }
    ]
</script>

<div class="menus">
    {#each menus as { title, link }}
        <a href={link}>{title}</a>
    {/each}
</div>

<style>
.menus {
    display: flex;
    gap: 10px;
}
</style>