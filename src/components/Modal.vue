<template>
    <div class="modal is-active">
        <div class="modal-background"></div>
        <div class="modal-card">
            <header class="modal-card-head">
                <p class="modal-card-title">
                    <slot name="header"></slot>
                </p>
                <button class="delete" aria-label="close" @click="$emit('close')"></button>
            </header>
            <section class="modal-card-body">
                <slot name="body"></slot>
            </section>
            <footer class="modal-card-foot">
                <slot name="footer">
                    <a class="button is-primary">Decline</a>
                    <a class="button">Accept</a>
                </slot>
            </footer>
        </div>
    </div>
</template>
<script>
export default {
    name: 'modal-template'
}
</script>
