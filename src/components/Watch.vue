<template>
    <div class="watch">
        <div class="strap"></div>
        <div class="watchCase">
            <div class="watchScreen">
                <table class="watchText">
                    <tr><td><span style="color: #c586c0;">export default</span><span style="color: #ffd700;">&nbsp;&#123;</span></td></tr>
                    <tr><td><span style="color: #9cdcf0;">&nbsp;&nbsp;오전오후&#58;&nbsp;</span><span style="color: #ce9178;">&#39;{{timeAMPM}}&#39;</span><span>&#44;</span></td></tr>
                    <tr><td><span style="color: #9cdcf0;">&nbsp;&nbsp;시간&#58;&nbsp;</span><span style="color: #c586c0;">&#123;</span></td></tr>
                    <tr><td><span style="color: #4ec9a2;">&nbsp;&nbsp;&nbsp;&nbsp;시</span><span style="color: #9cdcf0;">&#58;&nbsp;</span><span style="color: #4ec9a2;">{{ hour }}</span><span>&#44;</span></td></tr>
                    <tr><td><span style="color: #4ec9a2;">&nbsp;&nbsp;&nbsp;&nbsp;분</span><span style="color: #9cdcf0;">&#58;&nbsp;</span><span style="color: #4ec9a2;">{{ minute }}</span><span>&#44;</span></td></tr>
                    <tr><td><span style="color: #4ec9a2;">&nbsp;&nbsp;&nbsp;&nbsp;초</span><span style="color: #9cdcf0;">&#58;&nbsp;</span><span style="color: #4ec9a2;">{{ second }}</span></td></tr>
                    <tr><td><span style="color: #c586c0;">&nbsp;&nbsp;&#125;</span><span style="color: #ffd700;">&nbsp;&#125;</span></td></tr>
                </table>
            </div>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'Key',
    props: {
    },
    data() {
        return {
            timeAMPM: '오전',
            hour: 0,
            minute: 0,
            second: 0
        };
    },
    mounted() {
        setInterval(() => {
            const now = new Date();
            this.timeAMPM = now.getHours() >= 12 ? '오후': '오전';
            this.hour = now.getHours();
            this.minute = now.getMinutes();
            this.second = now.getSeconds();
        }, 1000);
    },

}
</script>

<style scoped>
.watch .strap {
    width: 100px;
    height: 250px;
    border-radius: 10px;
    background:repeating-linear-gradient(0deg, #F2EFE5, #E3E1D9 8px, #C7C8CC 11px, #B4B4B8 14px);
}
.watch .watchCase {
    width: 160px;
    height: 160px;
    border-radius: 80px;
    background-color: #B4B4B8;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
.watch .watchCase .watchScreen {
    width: 140px;
    height: 140px;
    border-radius: 70px;
    background-color: black;
    font-size: 4.5vmin;
    font-family: monospace;
    color: #fff;
    border: 4px solid black;
    box-shadow:
    inset 0 0 0.5rem 0.25em hsl(0 0% 100% / .25);
    background-image: linear-gradient(to bottom right, #fff0 50%, hsl(0 0% 100% / .25));
    /* position: relative; */
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
.watch .watchCase .watchScreen .watchText{
    width: 100%;
    margin: 15px;
    text-align: left;
}
.watch .watchCase .watchScreen .watchText span{
    font-size: 11px;
    display:block;
    float: left;
}
</style>
  