<script>
    export default {
        props : {
            xs : {
                type:[Number,String],
                'default':12,
                required:false,
            },
            sm : [Number,String],
            md : [Number,String],
            lg : [Number,String],
            xl : [Number,String],
            offsetXs : [Number,String],
            offsetSm : [Number,String],
            offsetMd : [Number,String],
            offsetLg : [Number,String],
            offsetXl : [Number,String],
            noMargins : Boolean
        },
        functional : true,
        render(h,c){
            function isset(val){
                return c.props[val]!==undefined&&c.props[val];
            }

            function createClass(breakpoint,cols){
                return 's-grid-cell-'+breakpoint+'-'+cols;
            }
            function createOffsetClass(breakpoint,cols){
                return 's-grid-cell-offset-'+breakpoint+'-'+cols;
            }
            const classes=[
                's-grid-cell',
                createClass('xs',c.props.xs),
            ];
            if(isset('sm')){
                classes.push(createClass('sm',c.props.sm));
            }
            if(isset('md')){
                classes.push(createClass('md',c.props.md));
            }
            if(isset('lg')){
                classes.push(createClass('lg',c.props.lg));
            }
            if(isset('xl')){
                classes.push(createClass('xl',c.props.xl));
            }

            if(isset('offsetXs')){
                classes.push(createOffsetClass('sm',c.props.offsetXs));
            }
            if(isset('offsetSm')){
                classes.push(createOffsetClass('sm',c.props.offsetSm));
            }
            if(isset('offsetMd')){
                classes.push(createOffsetClass('md',c.props.offsetMd));
            }
            if(isset('offsetLg')){
                classes.push(createOffsetClass('lg',c.props.offsetLg));
            }
            if(isset('offsetXl')){
                classes.push(createOffsetClass('xl',c.props.offsetXl));
            }
            const style={};
            if(isset('noMargins')){
                style['margin']=0;
            }

            return h('div',Object.assign({'class':classes,style},c.data),c.children);
        }
    }
</script>
