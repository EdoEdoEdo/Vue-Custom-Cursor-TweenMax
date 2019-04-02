<template>
    <div class="cursor">
        <div ref="cursor__big" class="cursor__ball cursor__ball--big ">
            <svg height="30" width="30">
                <circle cx="15" cy="15" r="12" stroke-width="0"></circle>
            </svg>
        </div>
          
        <div ref="cursor__small" class="cursor__ball cursor__ball--small">
            <svg height="10" width="10">
                <circle cx="5" cy="5" r="4" stroke-width="0"></circle>
            </svg>
        </div>
    </div>
</template>

<script>

export default {
 
    methods: {

        onMouseMove(e){
            TweenMax.to(this.$refs.cursor__big, .4, { 
            x: e.pageX - 15,
            y: e.pageY - 15
            });
            TweenMax.to(this.$refs.cursor__small, .1, {
            x: e.pageX - 5,  
            y: e.pageY - 7
            });
        }, 
        onMouseHover() {
            TweenMax.to(this.$refs.cursor__big, .3, {
            scale: 4
            });
        },
        onMouseHoverOut() {
            TweenMax.to(this.$refs.cursor__big, .3, {
            scale: 1
            });
        }
    },

    mounted: function() { 

        this.$parent.$el.addEventListener('mousemove', this.onMouseMove);
        
        for(var i=0; i < document.querySelectorAll("[trigger]").length; i++){
            var trigger=document.querySelectorAll("[trigger]")[i];
            trigger.addEventListener('mouseenter', this.onMouseHover);
            trigger.addEventListener('mouseleave', this.onMouseHoverOut);
        }
    },
}
</script>