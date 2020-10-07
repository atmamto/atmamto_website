<template>
    <div class="container">
        <div>
            <Slider />
            <Service />
         
            <Test />
   			<Contact />
        </div>
    </div>
</template>

<script>
    import Slider from '../components/home/slider'
    import Service from '../components/home/service'
    import Test from '../components/home/test'
    import Contact from '../components/home/contact'

   

    export default {
        comments: {
            Slider,
            Service,
           Test,
           Contact
        }
    }
</script>

<style>

a{
	color: #c31313;
}
a:hover {
    color: #315777;
}
.ivu-card-body img{
	
	width: 100%;
}
@media (min-width:300px) and (max-width: 768px)
{
.ivu-card-body img{
	
	width: 100%;
}
.ivu-layout-sider {
     

    position: absolute;

}

}

@media (min-width:300px) and (max-width: 767px)
{
.sliderTitle {
    left: 20%;
    font-size: 15px;

}
}

@media (min-width:300px) and (max-width: 425px)
{
.layout-logo img{
	
	width: 100%;
}
.ivu-layout-content {
   padding: 0px 0px !important;
}
.sliderTitle {
    left: 16%;
    font-size: 15px;

}
.ivu-input{
	font-size: 8px !important;
}
}

@media (min-width:426px) and (max-width: 768px)
{
.layout-logo img{
	
	width: 50%;
}

}
@media (min-width:769px) and (max-width: 1024px)
{
.layout-logo img{
	
	width: 43%;
}
.sliderTitle {
  top: 40%;
    left: 15%;
    font-size: 30px;

}

}
@media (min-width:1025px)
{
.layout-logo img{
	
	width: 30%;
}
.sliderTitle {
  top: 40%;
    left: 20%;
    font-size: 40px;

}

}
</style>