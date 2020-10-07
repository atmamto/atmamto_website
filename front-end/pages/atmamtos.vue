<template>
    <div>
        <Divider dashed ><h2 style="color: #c31313">About Us</h2></Divider>
        <Row>
            <Col :xs="24" :sm="24" :md="24" :lg="24" v-for="row in rows" :key="row.id">
                <Card style="margin: 10px">
                     
                    <p v-html="row.description"></p>
                    
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
                let url = process.env.moduleUrl + 'atmamtos';
                this.$axios.$get(url).then((res) => {
                    this.rows = res.payload.data;
                    this.loading = false;
                })
            }
        }
    }
</script>