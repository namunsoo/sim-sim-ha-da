<template>
    <div class="keyMain">
        <div class="key" ref="key" :id="id" @mousedown="mouseDownEvent" @mouseup="mouseUpEvent" @mouseleave="mouseLeaveEvent">
            <div class="keyContent">
                <div class="text" v-html="renderText">
                </div>
            </div>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'Key',
    props: {
        id: String,
        keyText: String,
        mainWith: String,
        mainHeight: String,
        contentWith: String,
        contentHeight: String,
    },
    computed: {
        renderText() {
            return this.keyText;
        }
    },
    methods: {
        mouseDownEvent() {
            const key = this.$refs.key;
            key.style.marginTop = "5px";
            key.style.boxShadow  = "0 0 0 1px #e9e8e6 inset, "
                +"0 0 0 2px rgba(255,255,255,0.15) inset, "
                +"0 0 0 1px rgba(0,0,0,0.4)";
        },
        mouseUpEvent() {
            const key = this.$refs.key;
            key.style.boxShadow  = "0 0 0 1px #e9e8e6 inset, "
                +"0 0 0 2px rgba(255,255,255,0.15) inset, "
                +"0 4px 0 0 rgba(0,0,0,0.2), "
                +"0 4px 0 1px rgba(0,0,0,0.4), "
                +"0 4px 4px 1px rgba(0,0,0,0.5)";
            key.style.marginTop = "0px";
        },
        mouseLeaveEvent() {
            const key = this.$refs.key;
            key.style.boxShadow  = "0 0 0 1px #e9e8e6 inset, "
                +"0 0 0 2px rgba(255,255,255,0.15) inset, "
                +"0 4px 0 0 rgba(0,0,0,0.2), "
                +"0 4px 0 1px rgba(0,0,0,0.4), "
                +"0 4px 4px 1px rgba(0,0,0,0.5)";
            key.style.marginTop = "0px";
        }
    }
}
</script>

<style scoped>
.keyMain {
    padding: 2px;
    width: v-bind(mainWith);
    height: v-bind(mainHeight);
}
.key {
    box-shadow: 0 0 0 1px #e9e8e6 inset, 
        0 0 0 2px rgba(255,255,255,0.15) inset, 
        0 4px 0 0 rgba(0,0,0,0.2), 
        0 4px 0 1px rgba(0,0,0,0.4), 
        0 4px 4px 1px rgba(0,0,0,0.5);
	display: inline-block;
	font-size: 22px;
	color: white;
	text-align: center;
	text-shadow: 0 1px 0 rgba(0,0,0,0.15);
    
    border: 3px solid transparent;
    border-top: 2px solid transparent;
    border-bottom: 6px solid transparent;
	border-radius: 4px;
    background-color: #e9e8e6;
    border-color: #c3c0bb;
    border-top-color: #eeedeb;
    border-bottom-color: #a6a29a;
    transition: all 100ms ease-in-out;

}
.keyContent {
    border: 1px solid transparent;
    border-radius: 4px;
    border-left-color: #b2afa8;
    border-right-color: #b2afa8;
    border-bottom-color: #959187;
    box-shadow: 0 4px 4px -3px rgba(0, 0, 0, 0.15);
    background-image: linear-gradient(to right, #e9e8e6, #c9c9c9 5%, transparent 40%, transparent 60%, #c9c9c9 95%, #e9e8e6);
}
.text {
    align-items: center;
    text-align: center;
    font-size: 14px;
    width: v-bind(contentWith);
    height: v-bind(contentHeight);
    color: black;
}
</style>
  