<script>
    export default {
        functional : true,
        props:{
            top : Boolean,
            center : Boolean,
            stretch : Boolean,
            bottom : Boolean,
            hCenter : Boolean,
            hStart : Boolean,
            hEnd : Boolean,
            rows : Boolean,
            columns : Boolean,
            reverse : Boolean,
        },
        render(h,c) {
            function isset(val){
                return c.props[val]!==undefined&&c.props[val];
            }

            let vClass='s-grid-top';
            if(isset('center'))
                vClass='s-grid-center';
            if(isset('stretch'))
                vClass='s-grid-stretch';
            if(isset('bottom'))
                vClass='s-grid-bottom';

            
            let hClass=null;
            if(isset('hCenter'))
                hClass='s-grid-justify-center';

            if(isset('hStart'))
                hClass='s-grid-justify-start';

            if(isset('hEnd'))
                hClass='s-grid-justify-end';

            let dClass=null;

            if(isset('rows'))
                dClass='s-grid-row';

            if(isset('columns'))
                dClass='s-grid-column';

            if(isset('reverse')&&!isset('rows')&&!isset('this.columns'))
                dClass='s-grid-row-reverse';
            else if(isset('reverse'))
                dClass+='-reverse';

            const classes=[vClass,hClass,dClass];

            return h('div',Object.assign({'class':classes},c.data),c.children);
        }
    }
</script>
