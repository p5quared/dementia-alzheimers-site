<script>
    export let address;
</script>

<a href={"/"+address.toLowerCase()}>{address}</a>

<style>
    a {
        text-decoration: none;
        font-size: 54px;
        box-shadow: 0 -1px 0 #000;
    }
</style>