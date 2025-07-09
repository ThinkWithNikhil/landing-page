<script>
    import { FaqItem, Button } from "$components";
    import twitterIcon from "$assets/icons/twitter.webp";

    let faqs = [
        {
            q: "What will I learn from this ebook?",
            a: "This ebook provides a comprehensive guide to relocating to Spain, covering everything from securing the right visa and navigating Spain's legal system to finding the perfect place to live and integrating into the local culture. Whether you're moving for work, study, or retirement, this guide equips you with the essential knowledge and practical steps to make your transition as smooth as possible."
        },
        {
            q: "Who is this ebook for?",
            a: "This ebook is perfect for anyone considering a move to Spain, whether you're planning a short-term stay or a permanent relocation. It's designed for expats, retirees, students, and professionals who want to avoid common pitfalls and streamline their move. If you're looking for a detailed, step-by-step guide to help you every step of the way, this ebook is for you.",
        },
        {
            q: "How much does the ebook cost?",
            a: "The ebook is priced at $10. This one-time purchase grants you immediate access to all the content, including detailed chapters, actionable checklists, and valuable resources that will save you time, money, and stress during your move to Spain."
        },
        {
            q: "Is the information in the ebook up-to-date",
            a: "Yes, the ebook is regularly updated to reflect the latest changes in Spanish immigration laws, visa requirements, and other relevant information. The author, John Smith, stays on top of these updates to ensure that you're receiving the most accurate and current guidance available."
        },
        {
            q: "Can I get a refund if I'm not satisfied?",
            a: "Absolutely. We offer a 30-day money-back guarantee. If you feel that the ebook did not meet your expectations or didn't provide the value you were looking for, simply contact us within 30 days of your purchase, and we’ll issue a full refund—no questions asked."
        }
    ];
    
    let openIndex = $state(-1);

    function toggleFaq(index) {
        openIndex = openIndex === index ? -1 : index;
    }

</script>
<section class="section-size">
    <h2 class="mb-l">Frequently asked questions</h2>
    <div class="faq-container">
        {#each faqs as faq, index}
            <FaqItem
                onclick={
                () => {toggleFaq(index)}
                }
                q={faq.q} 
                a={faq.a} 
                isActive = {openIndex === index}
            />
        {/each}
    </div>
    <div class="additional-info">
        <Button class="mt-s" buttonText="BUY NOW"/>
        <p class="mt-m">Any other questions?</p>
        <a href="http://x.com/thinkwithnikhil">
            <p>
                Hit me up on twitter <img src={twitterIcon} class="twitter-icon" alt="twitter icon">
            </p>
        </a>
    </div>
</section>

<style>
    .additional-info {
        display: flex;
        flex-direction: column;
        align-items: center;
        color: grey;
    }

    .twitter-icon {
        width: 16px;
        height: 16px;
    }

    .additional-info a {
        text-decoration: underline;
    }

</style>