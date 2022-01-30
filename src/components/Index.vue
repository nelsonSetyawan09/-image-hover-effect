<template>
    <div id="image-container">
        <div class="card" v-for="num,index in 4" :key="index">
            <img class="image-blur" :src="require(`@/assets/images/image-${num}.png`)" alt="">
            <div class="text-blur" :class="side[index]">
                Lorem ipsum dolor sit, amet consectetur adipisicing elit. Consectetur fugiat architecto alias labore similique et blanditiis hic quam quis tenetur eos mollitia, eaque harum accusantium dolorem voluptate? Porro, et rem.
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            side:["side-left", "side-right", "side-top", "side-bottom"]
        }
    },
    created(){
        this.side = this.side.sort(() => Math.random() - 0.5);
    }
}
</script>

<style  scoped>
    #image-container{
        margin: 0 auto;
        width: 700px;
        margin-bottom: 20px;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 5px;
    }
    .card{
        position: relative;
        overflow: hidden;
    }
    
    .image-blur{
        display: block;
        width: 100%;
        aspect-ratio: 1/1;
        object-fit: cover;
        object-position: left;
    }
    .text-blur{
        position: absolute;
        inset: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 20px;
        font-weight: 500;
        line-height: 1.4;
        background: rgba(255, 255, 255, .3);
        color: rgb(7, 13, 31);
    }
    .card > .image-blur,
    .card > .text-blur{
        transition: 200ms ease-in-out;
    }
    .card >.image-blur{
        filter: blur(0);
    }
    .card:hover > .image-blur{
        filter: blur(1px);
    }
    .card > .text-blur{
        opacity: 0;
        transform: translateX(-100%);
    }
    .card:hover > .text-blur{
        opacity: 1;
        transform: translateX(0);
    }
    .card > .text-blur.side-left{
        transform: translateX(-100%);
    }
    .card:hover > .text-blur.side-left{
        opacity: 1;
        transform: translateX(0);
    }
    .card > .text-blur.side-right{
        transform: translateX(100%);
    }
    .card:hover > .text-blur.side-right{
        opacity: 1;
        transform: translateX(0);
    }
    .card > .text-blur.side-top{
        transform: translateY(-100%);
    }
    .card:hover > .text-blur.side-top{
        opacity: 1;
        transform: translateX(0);
    }
    .card > .text-blur.side-bottom{
        transform: translateY(100%);
    }
    .card:hover > .text-blur.side-bottom{
        opacity: 1;
        transform: translateY(0);
    }
</style>