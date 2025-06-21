<script>
    import chevronDown from '$assets/icons/chevron-down.svg'
    let { q, a, isActive = false, ...props } = $props();

</script>
<button class="container" class:hide-answer={!isActive} {...props}>
    <div class="qna">
        <p class="question">{q}</p>
        <p class="answer">{a}</p>
    </div>
    <img src={chevronDown} alt="Chevron" style={isActive ? "transform: rotate(180deg);" : ""} />
</button>
<style>
    .container {
        display: flex;
        justify-content: space-between;
        align-items: flex-start;
        padding: 12px 0;
        border-bottom: 1px solid grey;
        text-align: left;
    }

    .qna {
        padding-right: 150px;
        flex-grow: 1;
    }

    button img {
        width: 24px;
        height: 24px;
        transition: 
            transform 0.3s linear ;
    }

    .question {
        font-weight: 600;
    }

    .hide-answer .answer {
        max-height: 0;
        overflow: hidden;
        opacity: 0;
        transition: 
            max-height 0.3s ease-out,
            opacity 0.3s ease-out
            ;
    }
</style>