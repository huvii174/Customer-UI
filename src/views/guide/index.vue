<template>
<div class="app-container">
    <a-carousel arrows dots-class="slick-dots slick-thumb">
        <a slot="customPaging" slot-scope="props">
            <img :src="getImgUrl(props.i)" />
        </a>
        <div v-for="item in 4">
            <img :src="baseUrl + 'abstract0' + item + '.jpg'" />
        </div>
    </a-carousel>
    <br>
    <br>
    <br>
    <p>
    </p>
    <a-divider>
        <h3>SHOP NAME</h3>
    </a-divider>
    <div class="shop-detail">
        <p class="el-icon-location"> Shop address </p>
        <br>
        <p class="el-icon-mobile-phone"> 0123456789 </p>
        <br>
        <p class="el-icon-time"> 08:00 - 22:00 </p>
        <br>
        <p class="el-icon-money"> 100.00 - 200.00 </p>
        <br>
        <p>
            <a-icon type="global" /> google.com </p>
        <br>
    </div>
    <div class="payment-method">
        <a-table :columns="columns" :data-source="data" bordered>
            <template slot="name" slot-scope="text">
                <a>{{ text }}</a>
            </template>
            <template slot="title" slot-scope="currentPageData">
                <strong> Payment Method </strong>
            </template>
        </a-table>
    </div>
    <div class="shop-info">
        <a-table :columns="column2" :data-source="data2">
        </a-table>
    </div>
</div>
</template>

<script>
const columns = [{
            title: 'Name',
            dataIndex: 'name',
            scopedSlots: {
                customRender: 'name'
            },
        },
        {
            title: 'Code',
            className: 'code',
            dataIndex: 'code',
        },
    ],
    column2 = [{
            title: 'WIFI',
            dataIndex: 'wifi',
        },
        {
            title: 'Booking',
            dataIndex: 'booking',
        },
        {
            title: 'Parking Scale',
            dataIndex: 'parkingScale',
        },
        {
            title: 'Smooking Place',
            dataIndex: 'smookingPlace',
        },
    ],
    baseUrl = 'https://raw.githubusercontent.com/vueComponent/ant-design-vue/master/components/vc-slick/assets/img/react-slick/',
    data = [{
            key: '1',
            name: 'Cash',
            code: 'By Cash',
        },
        {
            key: '2',
            name: 'VISA',
            code: 'By Card',
        },
        {
            key: '3',
            name: 'ATM',
            code: 'By Card',
        },
    ],
    data2 = [{
        key: '1',
        wifi: 'Yes',
        booking: 'Yes',
        parkingScale: 32,
        smookingPlace: 'Yes'
    }, ];
export default {
    data() {
        return {
            baseUrl,
            data,
            columns,
            column2,
            data2,
        };
    },
    methods: {
        getImgUrl(i) {
            return `${baseUrl}abstract0${i + 1}.jpg`;
        },
    },
};
</script>

<style scoped>
/* For demo */
.ant-carousel>>>.slick-dots {
    height: auto;
}

.ant-carousel>>>.slick-slide img {
    border: 5px solid #fff;
    display: block;
    margin: auto;
    max-width: 80%;
}

.ant-carousel>>>.slick-thumb {
    bottom: -45px;
}

.ant-carousel>>>.slick-thumb li {
    width: 60px;
    height: 45px;
}

.ant-carousel>>>.slick-thumb li img {
    width: 100%;
    height: 100%;
    filter: grayscale(100%);
}

.ant-carousel>>>.slick-thumb li.slick-active img {
    filter: grayscale(0%);
}

.shop-detail>>>p {
    font-weight: 400;
    font-size: 18px;
    font-family: Avenir, -apple-system, BlinkMacSystemFont, Segoe UI, PingFang SC, Hiragino Sans GB, Microsoft YaHei, Helvetica Neue, Helvetica, Arial, sans-serif, Apple Color Emoji, Segoe UI Emoji, Segoe UI Symbol;
}

th.column-money,
td.column-money {
    text-align: right !important;
}
</style>
