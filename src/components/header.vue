<template>
	<header class="header">
		<div class="title" v-if = "message.length > 0">{{message}}</div>
		<div class="title" v-else >{{title}}</div>
		<router-link to="/about"><i class="iconfont icon-shezhi"></i></router-link>
	</header>
</template>

<script>
	import $ from 'webpack-zepto';
	export default {
		name:'header',
		props:["message"],
	    data() {
	    	return {
	    		title:'全部',
	    		isFistLoad:true,
	    	}
	    },
	    mounted:function(){
	    	if(this.message.length > 0){
	    		this.isFistLoad = false;
	    	}
	    }
	}
</script>
<style rel="stylesheet/scss" type="text/css" lang="scss" scoped="">
	.header{
		width:100%;
		height:40px;
		line-height:40px;
        border-bottom: 1px solid #dddddd;
        position:fixed;
        background-color:#ffffff;
        top:0px;
        z-index:9;
		.title{
			height:100%;
			width:100%;
			text-align:center;
			font-size:14px;
			line-height:40px;
		}
		a{
			display: inline-block;
		    float: right;
		    position: absolute;
		    top: 0px;
		    right: 10px;
		    .icon-shezhi{
		    	color:#80bd01;
		    	opacity:.7;
		    }
		}
	}
</style>
