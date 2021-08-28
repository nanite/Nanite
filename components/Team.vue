<template>
    <div class="container">
        <div class="team">
            <div class="title"><h1>The team</h1></div>
            <div class="subtitle">
                <h2>Mad people, doing mad things for equally mad reasons.</h2>
            </div>
            <div v-if="members && members.length > 0" class="members">
                <div
                    v-for="(member, index) in members"
                    :key="index"
                    class="member"
                >
                    <div class="icon">
                        <a :href="member.url"
                            ><img :src="member.avatar" :alt="member.username"
                        /></a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts">
import Vue from 'vue'

export interface Member {
    username: string
    avatar: string
    url: string
}

export default Vue.extend({
    data() {
        return {
            members: [{ username: '', avatar: '', url: '' }],
        }
    },
    async fetch() {
        const res = await fetch('https://api.github.com/orgs/nanite/members', {
            headers: {
                Authorization: `token ${process.env.GITHUB_TOKEN}`,
            },
        })
        if (!res.ok) {
            console.error(res)
            return
        }
        const members = await res.json()
        const githubMembers: Member[] = []

        await Promise.all(
            members.map((member: any) => {
                githubMembers.push({
                    username: member.login,
                    avatar: member.avatar_url,
                    url: member.html_url,
                })
            })
        )
        githubMembers.sort((a: Member, b: Member) =>
            a.username.localeCompare(b.username)
        )
        this.members = githubMembers
    },
    fetchOnServer: true,
})
</script>
<style lang="scss" scoped>
.container {
    display: flex;
    justify-content: center;
    text-align: center;
    .title {
        font-weight: bold;
        font-size: 1.75rem;
        margin-bottom: 0.5rem;
    }
    .members {
        margin-top: 3.5rem;
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
        gap: 2rem;
        @media (max-width: 1100px) {
            grid-template-columns: 1fr 1fr 1fr;
        }
        .member {
            .icon {
                img {
                    width: 96px;
                    border: 6px solid rgba($color: #fff, $alpha: 0.1);
                    border-radius: 360px;
                }
            }
        }
        // .member:not(:last-child) {
        //     margin-bottom: 2rem;
        // }
        // @media (min-width: 1200px) {
        //     .member:not(:last-child) {
        //         margin-right: 2rem;
        //     }
        // }
    }
}
</style>
