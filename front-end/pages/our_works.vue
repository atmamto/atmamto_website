<template>
    <div class="container" >
        <div>
            <h1 style="color: #c31313">
                Our Work This Year
              
            </h1>
            <p style="color: #315777">
                We Happy To Serve You
            </p>
            <br/>
            <Loading v-if="loading"/>
            <List item-layout="vertical">
                <ListItem v-for="row in rows" :key="row.id">
                    <template slot="extra">
                       
                         <img :src="$images(row.image , 'org')">
                    </template>
                     <ListItemMeta  :title="row.name" />
                     <p style="color: #315777"> {{ row.description }}</p>
                    <template slot="action">
                        <li v-if="row.link">
                          <a :href="row.link" target="_blank"> <Icon type="md-link" /> Visit it</a>
                        </li>
                      
                    </template>
                </ListItem>
            </List>
            <template v-if="currentPage != lastPage">
                <Button type="primary" :loading="loading" @click="fetchData">
                    <span v-if="!loading">Click me!</span>
                    <span v-else>Loading...</span>
                </Button>
            </template>
        </div>
    </div>
</template>

<script>
    import Loading from '../components/loading'
    export default {
        comments: {
            Loading
        },
        data() {
            return {
                rows: [],
                loading: false,
                lastPage: 1,
                nextUrl: '',
                currentPage: 1,
                total: 0
            }
        },
        mounted() {
            this.fetchData();
        },
        methods: {
            fetchData() {
                this.loading = true;
                let url = process.env.moduleUrl + 'our_works';
                if (this.nextUrl !== '' && this.nextUrl != null) {
                    url = this.nextUrl;
                }
                this.$axios.$get(url).then((res) => {
                    if (this.rows.length > 0) {
                        this.rows = [...this.rows, ...res.payload.data];
                    } else {
                        this.rows = res.payload.data;
                    }
                    this.nextUrl = res.payload.next_page_url;
                    this.lastPage = res.payload.last_page;
                    this.currentPage = res.payload.current_page;
                    this.total = res.payload.total;
                    this.loading = false;
                })
            }
        }
    }
</script>

<style>

.ivu-list-vertical .ivu-list-item-meta-title {
 
    color: #315777;
    font-size: 20px;
  
}

.ivu-list-item-extra img{
    margin-left: 0;
    width: 70% !important;
    float: right;
}
.ivu-list-vertical .ivu-list-item-extra {
    margin-left: 0;
    width: 50%;
}
</style>

