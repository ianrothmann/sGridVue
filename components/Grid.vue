<script>
    export default {
        props:{
            vTop : Boolean,
            vCenter : Boolean,
            vStretch : Boolean,
            vBottom : Boolean,
            hCenter : Boolean,
            hStart : Boolean,
            hEnd : Boolean,
            rows : Boolean,
            columns : Boolean,
            reverse : Boolean,
        },
        render(h) {
            let vClass='s-grid-top';
            if(this.vCenter)
                vClass='s-grid-center';
            if(this.vStretch)
                vClass='s-grid-stretch';
            if(this.vBottom)
                vClass='s-grid-bottom';

            let hClass=null;
            if(this.hCenter)
                hClass='s-grid-justify-center';

            if(this.hStart)
                hClass='s-grid-justify-start';

            if(this.hEnd)
                hClass='s-grid-justify-end';

            let dClass=null;

            if(this.rows)
                dClass='s-grid-row';

            if(this.columns)
                dClass='s-grid-column';

            if(this.reverse&&!this.rows&&!this.columns)
                dClass='s-grid-row-reverse';
            else if(this.reverse)
                dClass+='-reverse';

            const classes=[vClass,hClass,dClass];

            return h('div',{'class':classes},this.$slots.default);
        }
    }
</script>
