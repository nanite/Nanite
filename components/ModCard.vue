<template>
    <div class="card">
        <div class="icon">
            <a :href="websiteUrl" target="_blank">
                <img :src="icon" alt="" />
            </a>
        </div>
        <div class="meta">
            <div class="modinfo">
                <div class="title">
                    <a :href="websiteUrl" target="_blank">
                        {{ name }}
                    </a>
                </div>
                <div class="summary">
                    {{ summary }}
                </div>
            </div>
            <div class="links">
                <div class="item">
                    <a :href="project.github" target="_blank">
                        <svg
                            viewBox="0 0 14 15"
                            fill="none"
                            xmlns="http://www.w3.org/2000/svg"
                        >
                            <path
                                d="M9.61538 13.9396V11.558C9.63847 11.2646 9.59882 10.9696 9.49909 10.6927C9.39935 10.4157 9.2418 10.1632 9.03692 9.95187C10.9692 9.73649 13 9.00418 13 5.64418C12.9998 4.785 12.6693 3.95876 12.0769 3.33649C12.3575 2.5848 12.3376 1.75393 12.0215 1.01649C12.0215 1.01649 11.2954 0.801103 9.61538 1.92726C8.20493 1.54499 6.71815 1.54499 5.30769 1.92726C3.62769 0.801103 2.90154 1.01649 2.90154 1.01649C2.58546 1.75393 2.56563 2.5848 2.84615 3.33649C2.24931 3.96338 1.91848 4.79708 1.92308 5.66264C1.92308 8.99803 3.95385 9.73033 5.88615 9.97033C5.68369 10.1795 5.52755 10.429 5.42788 10.7026C5.32822 10.9761 5.28727 11.2676 5.30769 11.558V13.9396M5.30769 12.0934C2.23077 13.0165 2.23077 10.555 1 10.2473L5.30769 12.0934Z"
                                stroke="white"
                                stroke-width="1.23077"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                            />
                        </svg>
                    </a>
                </div>
                <div class="item">
                    <a :href="project.maven" target="_blank"
                        ><svg
                            viewBox="0 0 13 14"
                            fill="none"
                            xmlns="http://www.w3.org/2000/svg"
                        >
                            <path
                                d="M12.0769 9.61412V4.69105C12.0767 4.47521 12.0197 4.26324 11.9117 4.07638C11.8037 3.88952 11.6485 3.73435 11.4615 3.62643L7.15385 1.16489C6.96675 1.05687 6.75451 1 6.53846 1C6.32242 1 6.11018 1.05687 5.92308 1.16489L1.61538 3.62643C1.42847 3.73435 1.27322 3.88952 1.16521 4.07638C1.0572 4.26324 1.00022 4.47521 1 4.69105V9.61412C1.00022 9.82995 1.0572 10.0419 1.16521 10.2288C1.27322 10.4157 1.42847 10.5708 1.61538 10.6787L5.92308 13.1403C6.11018 13.2483 6.32242 13.3052 6.53846 13.3052C6.75451 13.3052 6.96675 13.2483 7.15385 13.1403L11.4615 10.6787C11.6485 10.5708 11.8037 10.4157 11.9117 10.2288C12.0197 10.0419 12.0767 9.82995 12.0769 9.61412Z"
                                stroke="white"
                                stroke-width="1.23077"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                            />
                            <path
                                d="M1.1665 4.05103L6.53881 7.15872L11.9111 4.05103"
                                stroke="white"
                                stroke-width="1.23077"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                            />
                            <path
                                d="M6.53857 13.3557V7.15259"
                                stroke="white"
                                stroke-width="1.23077"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                            />
                        </svg>
                    </a>
                </div>
                <div class="item">
                    <a :href="websiteUrl" target="_blank"
                        ><svg
                            viewBox="0 0 19 11"
                            fill="none"
                            xmlns="http://www.w3.org/2000/svg"
                        >
                            <path
                                d="M4.99304 0L5.30233 1.31658C3.75581 1.31658 0 1.31658 0 1.31658C0 1.31658 0.0883937 1.71155 0.13258 1.75543C0.265138 1.97486 0.397696 2.23818 0.57444 2.41372C1.41398 3.37921 2.87207 3.77417 4.06509 3.9936C4.90463 4.16915 5.7442 4.21305 6.58373 4.25693L7.5558 6.84618H8.08607L8.39535 7.68003H7.95349L7.20235 10.0937H14.5814L13.8303 7.68003H13.3884L13.6977 6.84618H14.2279C14.2279 6.84618 14.6698 4.16916 16.0396 2.94036C17.3651 1.71155 19 1.53601 19 1.53601V0H4.99304ZM12.4163 6.62676C12.0628 6.84618 11.6651 6.8462 11.4 7.02174C11.2233 7.10951 11.1349 7.37282 11.1349 7.37282C10.9581 6.97785 10.7372 6.84621 10.4721 6.75843C10.207 6.67066 9.72093 6.71454 9.05814 6.14402C8.61628 5.74905 8.57209 5.22241 8.61628 4.9591V4.91522C8.61628 4.87134 8.61628 4.87133 8.61628 4.82745C8.61628 4.78356 8.61627 4.73968 8.66045 4.69579C8.74883 4.43248 8.96979 4.16915 9.41165 3.9936C9.41165 3.9936 9.10235 4.43246 9.41165 4.87132C9.58839 5.13464 9.94184 5.26629 10.2511 5.09075C10.3837 5.00298 10.4721 4.82745 10.5163 4.69579C10.6047 4.38859 10.6047 4.08138 10.3395 3.86195C9.94187 3.51086 9.8535 3.02813 10.1186 2.72093C10.1186 2.72093 10.207 3.1159 10.6047 3.07201C10.8698 3.07201 10.8698 2.98423 10.7814 2.89646C10.7372 2.7648 10.1628 1.93098 11.0023 1.31658C11.0023 1.31658 11.5326 0.965484 12.1512 1.00937C11.7977 1.05326 11.4 1.2727 11.2674 1.62378C11.2674 1.62378 11.2674 1.62377 11.2674 1.66766C11.1349 2.01874 11.2233 2.41372 11.4884 2.7648C11.6651 3.02812 11.886 3.24756 11.9744 3.59865C11.8418 3.55476 11.7535 3.59865 11.6651 3.68642C11.5768 3.7742 11.5325 3.94972 11.5767 4.08138C11.6209 4.16915 11.7093 4.25693 11.7977 4.25693C11.8418 4.25693 11.8419 4.25693 11.8861 4.25693H11.9302C12.0628 4.21305 12.1512 4.03751 12.107 3.90585C12.1954 3.99362 12.2395 4.21305 12.1953 4.34471C12.1953 4.47637 12.107 4.60802 12.0628 4.69579C12.0186 4.78357 11.9302 4.87133 11.8861 4.9591C11.8419 5.04687 11.7977 5.13466 11.7977 5.22243C11.7977 5.3102 11.7977 5.44184 11.8419 5.52961C12.0186 5.79292 12.3721 5.52961 12.4604 5.31018C12.593 5.04686 12.5488 4.73968 12.3721 4.47636C12.3721 4.47636 12.6814 4.6519 12.9023 5.2663C13.079 5.79293 12.7698 6.40733 12.4163 6.62676Z"
                                fill="white"
                            /></svg
                    ></a>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
    props: {
        project: {
            type: Object,
            required: true,
        },
    },
    data() {
        return {
            icon: '',
            name: '',
            websiteUrl: '',
            summary: '',
        }
    },
    async fetch() {
        await fetch(
            'https://addons-ecs.forgesvc.net/api/v2/addon/' +
                this.project.curseID
        ).then(async (res) => {
            const data = await res.json()
            this.websiteUrl = data.websiteUrl
            this.icon = data.attachments.find((a: any) => a.isDefault === true)
                ? data.attachments.find((a: any) => a.isDefault === true).url
                : require('@/assets/img/placeholder_art.png')
            this.summary = data.summary
            this.name = data.name
        })
    },
    fetchOnServer: true,
})
</script>

<style lang="scss" scoped>
.card {
    position: relative;
    padding: 1.5rem;
    border-radius: 10px;
    z-index: 1;
    overflow: hidden;
    display: flex;
    align-items: center;
    background-color: #132429;
    .icon {
        img {
            border-radius: 10px;
            max-width: 128px;
            box-shadow: 0 4px 20px rgba(black, 0.2);
            margin-right: 2.5rem;
        }
    }
    .meta {
        flex: 1;
        .modinfo {
            .title {
                font-size: 1.125rem;
                font-weight: bold;
                margin-bottom: 0.7rem;
            }
            .summary {
                font-size: 0.875rem;
                margin-bottom: 0.7rem;
            }
        }
        .links {
            width: 100%;
            display: flex;
            align-items: center;
            .item {
                margin-right: 1rem;
            }
        }
        a {
            text-decoration: none;
            color: white;
            svg {
                min-height: 1rem;
                height: 1rem;
            }
        }
        a:hover {
            color: rgba(255, 255, 255, 0.6);
        }
    }
}
</style>
