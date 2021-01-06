<template>
    <div class="w-4/5 m-auto text-white py-28" id="intro">
        <h3 class="text-dropboxyellow text-3xl mb-6 font-bold">Dropbox</h3>
        <h1 class="text-dropboxyellow text-7xl mb-8 w-2/5 font-bold">Focus on the work that  matters</h1>
        <p class="w-2/5 text-xl">Dropbox is the world’s first smart workspace. We bring all your team’s content together while letting you use the tools you love. And we help cut through the clutter, surfacing what matters most.</p>
        <span id="icon" class="animate relative top-0">Icon</span>
    </div>
</template>
<style scoped>
    @keyframes animate {
    from {
        top: 0;
    }

    to {
        top: 20;
    }
    }

    #icon {
    animation-duration: 0.1s;
    animation-name: animate;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    }
</style>
