<script>
    let { buttonText, ...props } = $props();
</script>

<button {...props} >{buttonText}</button>

<style>
    button {
        background-color: #000;
        color: #fff;
        padding: 20px 24px;
        font-weight: 400;
        font-size: 22px;
        text-transform: uppercase;
        transition: all .3s;
        border: 1px solid white;
    }

    button:hover {
        background-color: #fff;
        color: #000;
    }
</style>