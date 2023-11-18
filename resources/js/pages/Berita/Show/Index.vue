<template>
    <div class="detail-news">
        <router-link to="/berita">
            <i class="fas fa-arrow-left"></i> Back
        </router-link>
        <h1>{{ news.title }}</h1>
        <img :src="news.imageUrl" :alt="news.title" class="news-image"/>
        <div class="row justify-content-between">
            <div class="col-auto">
                <p>{{ news.created_by }}</p>
            </div>
            <div class="col-auto">
                <p class="date">
                    <i class="fas fa-calendar-alt"></i> {{ formatDate(news.date) }}
                </p>
            </div>
        </div>


        <div class="content">
            <p>{{ news.description }}</p>
            <p class="content-detail">{{ news.content }}</p>
        </div>

        <div class="content mt-5">
            <p>Dokumentasi Kegiatan</p>
            <div class="row">
                <div class="col-md-4">
                    <img src="https://via.placeholder.com/400x300" alt="Image 1" class="img-fluid">
                </div>
                <div class="col-md-4">
                    <img src="https://via.placeholder.com/400x300" alt="Image 2" class="img-fluid">
                </div>
                <div class="col-md-4">
                    <img src="https://via.placeholder.com/400x300" alt="Image 3" class="img-fluid">
                </div>
            </div>
        </div>


    </div>
</template>

<script>
export default {
    data() {
        return {
            news: {
                title: 'Sample News Title',
                created_by: 'Muhammad Ali',
                date: new Date(),
                imageUrl: 'https://via.placeholder.com/800x400',
                description: 'This is a sample news content. Replace it with the actual content.',
                content: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.\n' +
                    '\n' +
                    'Why do we use it?\n' +
                    'It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using \'Content here, content here\', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for \'lorem ipsum\' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).\n' +
                    '\n' +
                    '\n' +
                    'Where does it come from?\n' +
                    'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.',
            },
        };
    },
    methods: {
        formatDate(dateString) {
            const date = new Date(dateString);
            return new Intl.DateTimeFormat('en-US', {
                year: 'numeric',
                month: 'long',
                day: 'numeric',
            }).format(date);
        },
    },
};
</script>

<style scoped>
.detail-news {
    max-width: 70%;
    margin: 0 auto;
    padding: 20px;
}

h1 {
    font-size: 24px;
    margin-bottom: 10px;
    text-align: center;
}

.date {
    color: #888;
    font-size: 0.8rem;
    margin-bottom: 15px;
}

.news-image {
    width: 100%;
    height: auto;
    margin-bottom: 15px;
}

.content {
    font-size: 16px;
    line-height: 1.6;
}
.content-detail {
    font-size: 16px;
    line-height: 1.6;
    text-align: justify;
}

</style>
