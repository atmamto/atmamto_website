<template>

    <div>
        <Divider dashed ><h2 style="color: #c31313">our works</h2></Divider>
     <Carousel  v-model="value1" loop >
        <CarouselItem v-for="row in rows" :key="'slider_'+row.id">
          
       
            <List item-layout="vertical" >
                <ListItem :xs="24" :sm="24" :md="24" :lg="24"  >
                    <template slot="extra">
                        <img :src="$images(row.image)" width="250">
                    </template>
                    <ListItemMeta  :title="row.name" />
                    {{ row.description }}
                    <template slot="action">
                        <li v-if="row.link">
                          <a :href="row.link" target="_blank"> <Icon type="md-link" /> Visit it</a>
                        </li>
                    </template>
                </ListItem>
            </List>
          
          
        </CarouselItem>
    </Carousel>
         
    </div>


</template>
<script>
    export default {
        data () {
            return {
                rows:[],
                loading:true,
                value1:0 
            }
        },
        mounted() {
            this.fetchData();
        },
        methods: {
            fetchData() {
                this.loading = true;
                let url = process.env.moduleUrl + 'our_works';
                this.$axios.$get(url).then((res) => {
                    this.rows = res.payload.data;
                    this.loading = false;
                })
            }
        }
    }
</script>