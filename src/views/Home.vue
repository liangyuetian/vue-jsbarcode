<template>
    <div class="home">
        <svg class="code" id="code">

        </svg>
    </div>
</template>

<script lang="ts">
    import {Component, Vue} from 'vue-property-decorator';
    import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
    import JsBarcode from 'jsbarcode';

    @Component({
        data() {
            return {
                codeId: 'jsBarcode' + Math.random()
            }
        },
        components: {
            HelloWorld,
        },
    })
    export default class Home extends Vue {
        mounted() {
            JsBarcode(`#code`, 'BJS', {
                // format: "pharmacode",
                // lineColor: "#0aa", // 线条颜色
                width: 2,
                height: 40,
                // displayValue: false,
                text: 'BJS',
                fontOptions: '',
                textAlign: 'center',
                textPosition: 'bottom',
                textMargin: 2, // 文字距离条形码的距离
                fontSize: 12,
                background: '#fff',
                lineColor: '#000',
                margin: 0,
                marginTop: 0,
                marginBottom: 0,
                marginLeft: 0,
                marginRight: 0
            })
        }
    }
</script>
