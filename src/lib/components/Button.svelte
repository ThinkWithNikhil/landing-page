<script>
	import { loadStripe } from "@stripe/stripe-js";
    import { PUBLIC_STRIPE_KEY } from "$env/static/public";
	import { goto } from "$app/navigation";

    let { buttonText, ...props } = $props();

    async function onclick() {
        try {
            const stripe = await loadStripe(PUBLIC_STRIPE_KEY);

            const response = await fetch('/api/checkout', {
                method: 'POST',
                headers: {
                    "Content-Type": "application/json"
                }
            })

            const {sessionId} = await response.json();

            await stripe?.redirectToCheckout({sessionId});
        } catch (error) {
            goto("/checkout/failure")
        }
    }
</script>

<button {...props} {onclick}>{buttonText}</button>

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