<template>
    <div>
        <Divider dashed ><h2 style="color: #c31313">Some Of Testimonials</h2></Divider>
        <Row>
            <Col :xs="24" :sm="16" :md="12" :lg="6" v-for="row in rows" :key="row.id">
                <Card style="margin: 10px">
                    <div style="text-align:center">
                        <Avatar :src="$images(row.image)" size="large"/>
                        <h3>{{ row.name }}</h3>
                        <p>{{ row.job_title }}</p>
                        <p>{{ row.comment}}</p>
                        <small style="color: #c31313;font-weight: 600;">{{ row.project_type }}</small>
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
                let url = process.env.moduleUrl + 'testimonials';
                this.$axios.$get(url).then((res) => {
                    this.rows = res.payload.data;
                    this.loading = false;
                })
            }
        }
    }
</script>