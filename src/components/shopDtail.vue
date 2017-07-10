<template>
  <div class="product-box">
	  <div class="product-tit1"><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAu4AAABiCAIAAACAksEXAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAA3ppVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuNS1jMDIxIDc5LjE1NTc3MiwgMjAxNC8wMS8xMy0xOTo0NDowMCAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wTU09Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9tbS8iIHhtbG5zOnN0UmVmPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvc1R5cGUvUmVzb3VyY2VSZWYjIiB4bWxuczp4bXA9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC8iIHhtcE1NOk9yaWdpbmFsRG9jdW1lbnRJRD0ieG1wLmRpZDpjM2I1MGM5OC1mOWFiLTQ0NDYtOWY3Mi03NDliNTY4NmU4ZGYiIHhtcE1NOkRvY3VtZW50SUQ9InhtcC5kaWQ6MzQ2QjA2NjU4NDgyMTFFNkI2M0RDQkI5RDlBMkVGREYiIHhtcE1NOkluc3RhbmNlSUQ9InhtcC5paWQ6MzQ2QjA2NjQ4NDgyMTFFNkI2M0RDQkI5RDlBMkVGREYiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENDIDIwMTUuNSAoTWFjaW50b3NoKSI+IDx4bXBNTTpEZXJpdmVkRnJvbSBzdFJlZjppbnN0YW5jZUlEPSJ4bXAuaWlkOmVjOTlkZjhiLWI3MTAtNDViNS1hYmE4LWM5YzlhYjY0NzhiMCIgc3RSZWY6ZG9jdW1lbnRJRD0ieG1wLmRpZDpjM2I1MGM5OC1mOWFiLTQ0NDYtOWY3Mi03NDliNTY4NmU4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" /></div>
	  <div class="product-list1">
	  	<div class="li" v-for="val in datas.Recommend">	
      	  <router-link :to="{path:'/shopCart',query:{id:val.ProductID}}">
      	  	<img :src="val.PicturesWebp">
      		  <div></div>	
      	  </router-link>
      	  <p>{{val.Subject}}</p>	
      		<p>{{val.FinalPrice}}</p>
	  	</div>	  	
    </div> 
  </div>
</template>

<script>
export default {
  props: ['datas']
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
.product-tit1{
   height: .42rem;
   img{
      width:100%;
   }
}
.product-list1{
	display: -webkit-flex;
	justify-content:space-between;
	flex-wrap: wrap;
}
.product-list1 .li{
  background:#fff;
	width: 49%;	
	margin-bottom: .1rem;
  p{
    width: 90%;
    margin:0 auto;
    white-space: nowrap;
    overflow:hidden;
    padding-top: .1rem;
    text-overflow: ellipsis;
 }
  p:last-child{
    padding-top: .08rem;
 	text-align: center;
  }
}
.product-list1 .li a{
	display: block;
  position: relative;
  div{
    padding-top: 100%;
  }
}
.product-list1 .li a img{
	  width:100%;
    position: absolute;
}
</style>
