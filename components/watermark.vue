<template>
    <aside class="watermark">
        <img class="watermark-logo" src="/logo-red.jpg" alt="Logo Shodo" />
        <span class="watermark-title">Crafting sustainable code we do</span>
    </aside>
</template>

<style scoped>
.watermark {
    align-items: center;
    display: flex;

    &-logo {
        margin-right: 10px;
        max-height: 50px;
    }

    &-title {
        font-family: var(--font-secondary);
        font-size: 0.7rem;
        line-height: 0.9rem;
        max-width: 90px;
        text-transform: uppercase;
    }
}
</style>