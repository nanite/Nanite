<template>
    <div class="">
        <div class="top">
            <div class="about">
                <div class="title">
                    <h1>Our projects</h1>
                </div>
                <div class="subtitle">
                    <h2>
                        We make mods, lots of really, really, weird and
                        wonderful mods. We’re not really sure why but if you
                        wanna play with any of them, you can grab them from
                        below.
                    </h2>
                </div>
            </div>
        </div>
        <div v-if="repos && repos.length > 0" class="mods">
            <div v-for="(project, index) in repos" :key="index" class="mod">
                <ModCard :project="project" />
            </div>
        </div>
    </div>
</template>
<script lang="ts">
import Vue from 'vue'

export interface Meta {
    curseID: string
    maven: string
    github: string
    name: string
}

export default Vue.extend({
    data() {
        return {
            repos: [{ curseID: '', maven: '', github: '', name: '' }],
        }
    },
    async fetch() {
        const res = await fetch('https://api.github.com/orgs/nanite/repos', {
            headers: {
                Authorization: `token ${process.env.GITHUB_TOKEN}`,
            },
        })
        if (!res.ok) {
            console.error(res)
            return
        }
        const projects = await res.json()
        const github: Meta[] = []

        await Promise.all(
            projects.map(async (project: any) => {
                const metaRes = await fetch(
                    'https://raw.githubusercontent.com/nanite/' +
                        project.name +
                        '/' +
                        project.default_branch +
                        '/.github/meta.json'
                )
                if (metaRes.statusText === 'OK') {
                    const meta = await metaRes.json()
                    github.push({
                        curseID: meta.curseID,
                        maven: meta.maven ?? null,
                        github: project.html_url,
                        name: project.name,
                    })
                }
            })
        )
        github.sort((a: Meta, b: Meta) => a.name.localeCompare(b.name))
        this.repos = github
    },
    fetchOnServer: true,
})
</script>

<style lang="scss" scoped>
.top {
    display: flex;
    justify-content: center;
    .about {
        text-align: center;
        .title {
            font-weight: bold;
            font-size: 1.75rem;
            margin-bottom: 1rem;
        }
        .subtitle {
            max-width: 650px;
            word-wrap: break-word;
            color: rgba(255, 255, 255, 0.8);
            line-height: 1.4rem;
            word-spacing: 0.1rem;
        }
    }
}

.mods {
    padding-top: 3rem;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 1.5rem;
    @media (max-width: 1200px) {
        .mod {
            grid-column: span 3;
        }
    }
}
</style>
