<template>
    <div>
        <section class="academic-section">
            <section class="row">
                <div class="col-half">
                    <div class="academic-image">
                        <img
                            :src="syncDiagram[$i18n.locale]"
                            alt="image in academic section"
                        />
                    </div>
                </div>
                <div class="col-half">
                    <h2>{{ $t('totoro.academic.heading1') }}</h2>
                    <p>
                        {{ $t('totoro.academic.text1')
                        }}<b>{{ $t('totoro.academic.text2') }}</b>
                        {{ $t('totoro.academic.text3')
                        }}<b>{{ $t('totoro.academic.text4') }}</b>
                        {{ $t('totoro.academic.text5')
                        }}<b>{{ $t('totoro.academic.text6') }}</b>
                        {{ $t('totoro.academic.text7') }}
                    </p>
                    <p>
                        {{ $t('totoro.academic.text8')
                        }}<b>{{ $t('totoro.academic.text9') }}</b>
                    </p>
                </div>
            </section>
            <div class="row follow-us">
                <section class="col-half">
                    <h2>{{ $t('totoro.cohesion.followUs.title') }}</h2>
                    <p>
                        {{ $t('totoro.cohesion.followUs.p1') }}
                    </p>
                    <p>
                        <b>{{ $t('totoro.cohesion.followUs.p2') }}</b>
                    </p>
                </section>
                <section class="col-half">
                    <img src="@/assets/totoro/qr-with-totoro.png" />
                </section>
            </div>
            <div class="row group-class-row">
                <section class="col-half col-half-center section-scan">
                    <img class="totoro-qr" src="@/assets/totoro/qr-1.png" />
                    <img class="totoro-qr" src="@/assets/totoro/qr-2.png" />
                    <p>{{ $t('totoro.academic.scanqr1') }}</p>
                    <p>{{ $t('totoro.academic.scanqr2') }}</p>
                </section>
                <div class="col-half col-half-half col-flex">
                    <div class="icon-register half-to-half icon-one-to-one">
                        <img
                            src="@/assets/totoro/onetoone.png"
                            alt="one to one image"
                        />
                        <span>{{ $t('totoro.academic.oneToOne') }}</span>
                    </div>
                    <div
                        class="icon-register half-to-half group-top icon-one-to-more"
                    >
                        <img
                            src="@/assets/totoro/onetoonephd.png"
                            alt="one to one image"
                        />
                        <span>{{ $t('totoro.academic.oneToOnePhd') }}</span>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
import syncDiagramZh from '@/assets/totoro/sync-diagram.png';
import syncDiagramEn from '@/assets/totoro/sync-diagram-en.png';

export default {
    name: 'Academic',
    components: {},
    data() {
        return {
            syncDiagram: {
                zh: syncDiagramZh,
                en: syncDiagramEn,
            },
        };
    },
};
</script>

<style lang="scss" scoped>
.totoro-qr {
    float: left;
    margin-right: 20px;
}

.group-class-row > section > p:first-of-type {
    margin-top: 70px;
}

.icon-register {
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    img {
        height: 100px;
    }
}

.half-to-half {
    flex: 0 0 45%;
    max-width: 45%;
}

.col-half-half {
    display: flex;
}

.section-scan {
    font-weight: 600;
}

.icon-register > img {
    margin-bottom: 22px;
}

.icon-register > button {
    margin-top: 40px;
}

#ifu-logo-img {
    width: 128px;
}

.row {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
}

.col-half {
    flex: 0 0 50%;
    max-width: 50%;
    white-space: pre-line;
    box-sizing: border-box;

    p {
        white-space: normal;
    }
}

.academic-image {
    text-align: center;
}

.academic-image > img {
    width: 500px;
    height: 270px;
}

.col-half > p,
.col-half > h2 {
    padding-left: 80px;
}

.col-half > p {
    font-size: $text-size;
    line-height: 31px;
    letter-spacing: 0.02em;
}

.academic-section {
    padding: 0 0 0 0 !important;
    border-bottom: 6px solid $dark-blue;
}

.flex-top-left {
    display: flex;
    align-items: flex-start;
}

.flex-bottom-right {
    display: flex;
    flex-direction: row-reverse;
}

.color-box {
    background-color: #f1f1f1;
    width: 275px;
    text-align: center;
    height: 119px;
    font-size: 30px;
    color: #ffffff;
    display: flex;
    justify-content: center;
    align-items: center;
}

.row-flex-end {
    align-items: flex-start;
}

.orange {
    background: $orange;
}

.pink {
    background: $dark-pink;
}

.blue {
    background: $teal;
}

.green {
    background: $green;
}
#scan-qr {
    line-height: inherit;
}

.section-scan {
    padding-right: 0;
}

.follow-us {
    background: $background-light-blue;

    section {
        height: 100%;
        background: $background-light-blue;
    }
}

@media (max-width: $mobile-max-width) {
    .row {
        flex-direction: column;
        margin: 0;
        width: 100%;
        box-sizing: border-box;
    }

    .col-half {
        flex: auto;
        max-width: 100%;
        width: 100%;
        img {
            display: block;
            padding-left: 0px;
            width: 100%;
            height: 100%;
            margin: 15px auto 22px auto;
        }
        h2 {
            padding-left: 0;
        }
        p {
            display: block;
            margin-left: auto;
            margin-right: auto;
            padding-left: 0px;
            padding-right: 0px;
        }
        #scan-qr {
            text-align: center;
        }
    }

    .color-box {
        font-size: $h2-size;
    }
    .academic-section {
        padding: 0 0 0 0 !important;
    }

    .group-class-row {
        margin-top: 25px;
        padding: 20px 0 50px 0;
        text-align: center;

        .col-half,
        .col-half-half {
            display: block;
        }

        .half-to-half {
            margin: auto;
            max-width: unset;
        }

        .totoro-qr {
            float: none;
        }

        > section > p {
            text-align: center;
            margin: 15px !important;
        }

        .col-flex {
            display: flex;
            max-width: 80%;
        }
    }

    .group-class-row > section > p {
        margin-top: 15px;
    }

    .icon-one-to-one > img {
        height: 99px;
        width: 100px;
    }

    .icon-one-to-more > img {
        height: 99px;
        width: 165px;
    }

    .section-scan {
        p {
            line-height: 10px;
        }

        img {
            height: 180px;
            width: 180px;
        }
    }
}
</style>
