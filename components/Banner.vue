<template>
    <div class="banner" :style="{ backgroundImage: `url(${background})` }">
        <div class="banner-left">
            <h1 v-if="subTitle" class="subtitle-text">{{ subTitle }}</h1>
            <h1 v-if="title" class="title-text" :style="{ color: titleColor }">
                {{ title }}
            </h1>
            <p v-if="description">{{ description }}</p>
            <div v-for="(item, index) in bannerList" :key="index" class="title">
                <strong>{{ item.name }}</strong
                ><span>{{ item.text }}</span>
            </div>
            <slot />
            <Button v-if="to" :external="external" :to="to">
                {{ buttonText }}
            </Button>
        </div>
        <div class="banner-right">
            <img :src="image" />
        </div>
    </div>
</template>

<script>
import Button from '@/components/Button.vue';

export default {
    name: 'Banner',
    components: {
        Button,
    },
    props: {
        title: {
            type: String,
            default: null,
        },
        subTitle: {
            type: String,
            default: null,
        },
        description: {
            type: String,
            default: '',
        },
        buttonText: {
            type: String,
            default: '',
        },
        external: {
            type: Boolean,
            default: false,
        },
        to: {
            type: String,
            default: null,
        },
        background: {
            type: String,
            default: null,
        },
        bannerList: {
            type: Array,
            default: null,
        },
        titleColor: {
            type: String,
            default: '#202020',
        },
        image: {
            type: String,
            default: null,
        },
    },
};
</script>

<style lang="scss" scoped>
.banner {
    width: 100%;
    height: 100%;
    padding: 96px $padding-horizontal;
    box-sizing: border-box;
    background-size: cover;
    display: flex;
    box-shadow: 0 0px 10px #eee;
    background-position: center;
}

h1 {
    font-size: $h1-size;
    color: #2c3e51;
    font-weight: normal;
    margin: 0;
}

.title-text {
    font-weight: normal;
}

p {
    max-width: 490px;
    margin: 30px 0;
    line-height: 31px;
}

button {
    margin-top: 45px;
}
.title {
    font-size: $text-size;
    line-height: 31px;
}

.banner-left {
    width: 50%;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.banner-right img {
    width: 100%;
}
strong {
    margin-right: 5px;
}

@media (max-width: $mobile-max-width) {
    .banner {
        padding: 70px 30px 35px 30px;
        flex-wrap: wrap;
    }

    h1 {
        font-size: $h2-size;
        margin: 0 0 20px 0;
    }

    button {
        margin-top: 35px;
    }

    .banner-left {
        width: 100%;
    }

    p {
        margin: 0;
        max-width: 100%;
    }
}
</style>
