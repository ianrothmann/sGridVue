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
        },
        methods : {
            createClass(breakpoint,cols){
                return 's-grid-cell-'+breakpoint+'-'+cols;
            },
            createOffsetClass(breakpoint,cols){
                return 's-grid-cell-offset-'+breakpoint+'-'+cols;
            }
        },
        render(h) {
            const classes=[
                's-grid-cell',
                this.createClass('xs',this.xs),
            ];
            if(this.sm){
                classes.push(this.createClass('sm',this.sm));
            }
            if(this.md){
                classes.push(this.createClass('md',this.md));
            }
            if(this.lg){
                classes.push(this.createClass('lg',this.lg));
            }
            if(this.xl){
                classes.push(this.createClass('xl',this.xl));
            }

            if(this.offsetXs){
                classes.push(this.createOffsetClass('sm',this.offsetXs));
            }
            if(this.offsetSm){
                classes.push(this.createOffsetClass('sm',this.offsetSm));
            }
            if(this.offsetMd){
                classes.push(this.createOffsetClass('md',this.offsetMd));
            }
            if(this.offsetLg){
                classes.push(this.createOffsetClass('lg',this.offsetLg));
            }
            if(this.offsetXl){
                classes.push(this.createOffsetClass('xl',this.offsetXl));
            }

            return h('div',{
                'class':classes
            },this.$slots.default);
        }
    }
</script>
