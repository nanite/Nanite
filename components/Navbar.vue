<template>
    <div class="bar">
        <div class="left">
            <div class="art">
                <img src="/nanite_chunk.png" alt="" />
            </div>
            <div class="nanite">
                <h1 class="title">Nanite</h1>
                <h2 class="substitle">
                    A group of mods, modders, people, beings
                </h2>
            </div>
        </div>
        <div class="right">
            <div class="item">
                <a href="https://github.com/nanite" target="_blank">Github</a>
            </div>
            <div class="item">
                <a
                    href="https://www.curseforge.com/members/nanitedev/projects"
                    target="_blank"
                    >Curse Mods</a
                >
            </div>
            <div class="item">
                <a href="https://maven.nanite.dev/" target="_blank">Maven</a>
            </div>
            <div class="item">
                <a href="https://vers.nanite.dev/" target="_blank"
                    >Lastest project files</a
                >
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.bar {
    padding: 4.4rem;
    @media (min-width: 1150px) {
        justify-content: space-between;
        display: flex;
    }
    .left {
        display: flex;
        @media (max-width: 1150px) {
            justify-content: center;
        }
        .nanite {
            margin: 0 0 0 2rem;
            align-self: center;
            .title {
                font-weight: bold;
                font-size: 1.5rem;
                margin-bottom: 0.3rem;
            }
        }
    }
    .right {
        display: flex;
        align-self: center;
        @media (max-width: 1150px) {
            justify-content: center;
        }
        .item {
            margin: 0 0 0 3rem;
            @media (max-width: 1150px) {
                margin: 1rem 0 0 1.2rem;
                a {
                    text-decoration: underline !important;
                }
            }

            a {
                text-decoration: none;
                color: white;
            }
            a:hover {
                color: rgba(255, 255, 255, 0.6);
            }
        }
    }
}
</style>
