<template>
    <div>
        <Divider dashed ><h2 style="color: #c31313">Services</h2></Divider>
        <Row>
            <Col :xs="24" :sm="16" :md="12" :lg="8" v-for="row in rows" :key="row.id">
                <Card style="margin: 10px">

                    <p slot="title">
                        <NuxtLink :to="'/services/'+row.id">{{ row.name }}</NuxtLink>
                    </p>
                    <div style="text-align:center">
                        <NuxtLink :to="'/services/'+row.id">
                            <img :src="$images(row.image)" width="250">
                        </NuxtLink>
                    </div>
                </Card>
            </Col>
        </Row>
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
                let url = process.env.moduleUrl + 'services';
                this.$axios.$get(url).then((res) => {
                    this.rows = res.payload.data;
                    this.loading = false;
                })
            }
        }
    }
</script>