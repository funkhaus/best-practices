<template>
    <smart-link
        v-in-view
        class="block-news has-border in-view-effects"
        :to="url"
    >
        <responsive-image
            v-if="image"
            class="image"
            :image="image"
            :aspect-ratio="56.25"
        >
            <ul
                v-if="categories"
                class="cats"
            >
                <li
                    v-for="(cat, i) in categories"
                    v-if="cat.name !== 'News'"
                    v-html="cat.name"
                />
            </ul>

            <div
                v-if="showNext"
                class="next-up"
            >
                Next Up
            </div>

            <div class="border" />
        </responsive-image>

        <div class="meta">
            <div class="date">
                {{ formattedDate }}
            </div>
            <h2
                class="title"
                v-html="title"
            />
            <div
                class="excerpt"
                v-html="excerpt"
            />
            <button
                class="read-more"
                v-text="'Read more'"
            />
        </div>
    </smart-link>
</template>

<script>
import { formatDate } from "~/utils/tools"

export default {
    props: {
        image: {
            type: Object,
            default: () => {}
        },
        title: {
            type: String,
            default: ""
        },
        date: {
            type: String,
            default: ""
        },
        url: {
            type: String,
            default: ""
        },
        categories: {
            type: Array,
            default: () => []
        },
        showNext: {
            type: Boolean,
            default: false
        },
        excerpt: {
            type: String,
            default: ""
        }
    },
    computed: {
        formattedDate() {
            return formatDate(this.date)
        }
    }
}
</script>

<style lang="scss">
@import "~/styles/_vars.scss";

.block-news {
    width: 100%;
    margin-bottom: 60px;
    position: relative;
    text-align: left;

    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: center;
    align-content: center;
    align-items: center;

    .image {
        width: calc(50% - 60px);
        position: relative;
    }
    .cats {
        position: absolute;
        bottom: 30px;
        left: 30px;
        list-style: none;
        margin: 0;
        padding: 0;
        color: $white;
        font-size: 14px;
        text-transform: uppercase;
        font-weight: 700;
        opacity: 0;
        transition: all 0.4s ease-in-out;

        li {
            margin: 0;
            padding: 0;
        }
    }
    .next-up {
        position: absolute;
        z-index: 20;
        top: 30px;
        right: 30px;
        color: $white;
        font-weight: 700;
        font-size: 14px;
        text-transform: uppercase;
    }
    .meta {
        margin-left: 60px;
        width: 50%;
    }
    .date {
        font-size: 16px;
    }
    .title {
        font-size: 32px;
        margin-top: 15px;
        letter-spacing: 0;
        line-height: 38px;
    }
    .excerpt {
        margin: 20px auto;
        font-size: 16px;
        line-height: 1.45;
    }
    .read-more {
        font-size: 16px;
        text-transform: uppercase;
        font-weight: 700;
    }

    // Hover state
    @media (hover: hover) {
        &:hover .cats {
            opacity: 1;
        }
    }

    // Breakpoints
    @media #{$lt-tablet} {
        display: block;

        .image {
            width: 100%;
        }
        .cats {
            opacity: 1;
            left: 20px;
            bottom: 20px;
        }
        .date {
            font-size: 14px;
        }
        .meta {
            margin: 20px 0;
            width: 100%;
        }
        .title {
            font-size: 18px;
            line-height: 28px;
            margin: 10px 0;
        }
        .excerpt {
            font-size: 14px;
        }
    }
}
</style>
