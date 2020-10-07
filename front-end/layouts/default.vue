<template>
    <div class="layout">
        <Layout>
            <Sider breakpoint="md" collapsible :collapsed-width="78" v-model="isCollapsed">
                <Menu active-name="1-1" theme="dark" width="auto" :class="menuitemClasses">
               
                    <MenuItem name="1-1">
                            <NuxtLink to="/" class="white">
                                Home
                            </NuxtLink>
                    </MenuItem>
                    <MenuItem name="1-2">
                            <NuxtLink to="/services" class="white">
                                Services
                            </NuxtLink>
                    </MenuItem>
                    <MenuItem name="1-3">
                            <NuxtLink to="/our_works" class="white">
                                Our Works
                            </NuxtLink>
                    </MenuItem>
                    
                    <MenuItem name="1-4">
                            <NuxtLink to="/atmamtos" class="white">
                                About Us
                            </NuxtLink>
                    </MenuItem>

                    <MenuItem name="1-5">
                            <NuxtLink to="/pages/2" class="white">
                            Our Profile
                            </NuxtLink>
                    </MenuItem>

            <Divider dashed style="color: #fff;">Contact Us</Divider>
            <MenuItem name="1-6" id="">
                    <Icon type="ios-mail-open-outline" />
                    info@atmamto.com
             </MenuItem>
            <MenuItem name="1-7">
                    <Icon type="ios-call-outline" />
                    01140331349 
             </MenuItem>
             <MenuItem name="1-8">
                    <Icon type="ios-call-outline" />
                    01147769139
        </MenuItem>
                   <Divider dashed style="color: #fff;">Social Media</Divider>
           <MenuItem name="1-9" id="social-img">
                                             
                <NuxtLink to="#"><img src="fa.png" alt=""> </NuxtLink>
                                
              <NuxtLink to="#"><img src="tu.png" alt=""> </NuxtLink>  
                                          
              <NuxtLink to="#"><img src="tw.png" alt=""> </NuxtLink>
                                
         </MenuItem>
    </Menu>
                <div slot="trigger"></div>
            </Sider>
            <Layout>
                <Header class="layout-header-bar">
                    <div class="layout-logo">
           <NuxtLink to="/"><img src="atmamto-logo.png" alt="" width="130"> </NuxtLink>
                    </div>
                </Header>
            <Content style="padding: 0 50px ;margin-top:20px">
                <Card>
                    <div style="min-height: 200px;">
                        <Nuxt/>
                    </div>
                </Card>
            </Content>
            <Footer class="layout-footer-center">2020-2021 &copy; Atmamto.com</Footer>
            </Layout>
        </Layout>
    </div>
</template>
<script>
    export default {
        data () {
            return {
                isCollapsed: false
            };
        },
        computed: {
            menuitemClasses: function () {
                return [
                    'menu-item',
                    this.isCollapsed ? 'collapsed-menu' : ''
                ]
            }
        },
        head() {
            return {
                title: 'Atmamto Design Studio',
            }
        }
   
    }
</script>
<style scoped>
#social-img img:hover{
    
    -ms-transform: rotate(45deg);
    -webkit-transform: rotate(45deg);
    transform: rotate(45deg);
    z-index: 1;
    transition: all .5s ease-in-out;
 
}
.ivu-menu-dark.ivu-menu-vertical .ivu-menu-item:hover, .ivu-menu-dark.ivu-menu-vertical .ivu-menu-submenu-title:hover {
    color: #fff;
  background: linear-gradient(60deg, #315777 0%, #c31313 100%);
}
    .layout{
        border: 1px solid #d7dde4;
        background: #f5f7f9;
        position: relative;
        border-radius: 4px;
        overflow: hidden;

    }
    .layout-header-bar{
        background: #fff;
        box-shadow: 0 1px 1px rgba(0,0,0,.1);
    }
    .menu-item span{
        display: inline-block;
        overflow: hidden;
        width: 200px;
        text-overflow: ellipsis;
        white-space: nowrap;
        vertical-align: bottom;
        transition: width .2s ease .2s;
      
    }
    .menu-item i{
        transform: translateX(0px);
        transition: font-size .2s ease, transform .2s ease;
        vertical-align: middle;
        font-size: 16px;
    }
    .collapsed-menu span{
        width: 0px;
        transition: width .2s ease;
    }
    .collapsed-menu i{
        transform: translateX(5px);
        transition: font-size .2s ease .2s, transform .2s ease .2s;
        vertical-align: middle;
        font-size: 22px;
    }



    .white{
        color: white;
    }


    .ivu-layout-sider,
    .ivu-menu-dark,
    .ivu-layout-sider-children {
    background-color: #315777;
        }

  .layout-header-bar[data-v-314f53c6] {
    box-shadow: none;
    }

.layout-logo {
        text-align: center;

    }

.ivu-layout-header {
 
    height: 160px;
   
}





.c-b{
    background-color : #315777;
     border-color: #315777;

}

.ivu-menu-dark.ivu-menu-vertical .ivu-menu-item-active[data-v-314f53c6]:not(.ivu-menu-submenu), .ivu-menu-dark.ivu-menu-vertical .ivu-menu-item-active[data-v-314f53c6]:not(.ivu-menu-submenu):hover,
.ivu-menu-dark.ivu-menu-vertical .ivu-menu-item-active:not(.ivu-menu-submenu), 
.ivu-menu-dark.ivu-menu-vertical .ivu-menu-item-active:not(.ivu-menu-submenu):hover{
    
        background: linear-gradient(60deg, #c31313 0%, #315777 100%);
}

ul.ivu-menu.ivu-menu-dark.ivu-menu-vertical.menu-item {
    width: 200px !important;
}

.ivu-layout-footer {
    color: #c31313;
    font-size: 15px;
    text-align: center;
}
::selection {
    color: #fff;
    background: #315777;
}
@media (min-width:769px)
{
    .ivu-menu-dark{
      position: fixed; 
    }


}

</style>