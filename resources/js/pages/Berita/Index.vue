<template>
    <div class="container mt-5">
        <div class="row justify-content-center">
            <div class="col-md-10 text-center">
                <div class="font-size-24 font-weight-500">Berita Terbaru</div>
                <div class="card-container mt-4">
                    <div v-for="(card, index) in cards.slice(0, 3)" :key="index" class="card">
                        <img :src="card.imageUrl" :alt="card.title" class="card-image" />
                        <div class="card-content">
                            <h3>{{ card.title }}</h3>
                            <p class="description">{{ card.description }}</p>
                        </div>
                        <div class="card-footer" style="background-color: white">
                            <p class="date" style="margin-left: -5%; margin-bottom: -3%">
                                <i class="fas fa-calendar-alt" style="margin-right: 4px;"></i>
                                {{ formatDate(card.date) }}
                            </p>
                            <button class="more-info-btn" @click="showMoreInfo(card)" style="margin-right: -6%; margin-top: 3%">Lihat Selengkapnya</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <hr>
        <div class="row justify-content-center">
            <div v-for="(card, index) in cards" :key="index" class="card-all">
                <img :src="card.imageUrl" :alt="card.title" class="card-all-image" />
                <div class="card-all-content">
                    <h3>{{ card.title }}</h3>
                    <p class="description">{{ card.description }}</p>
                </div>
                <div class="card-all-footer" style="background-color: white">
                    <p class="date" style="margin-left: -3%; margin-bottom: -3%">
                        <i class="fas fa-calendar-alt" style="margin-right: 4px;"></i>
                        {{ formatDate(card.date) }}
                    </p>
                    <button class="more-info-btn" @click="showMoreInfo(card)" style="margin-right: -5%; margin-top: 3%">Lihat Selengkapnya</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            cards: [
                {
                    title: 'Card 1',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
                {
                    title: 'Card 2',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
                {
                    title: 'Card 3',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: '01-23-2023 00:00:00',
                },
                {
                    title: 'Card 4',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
                {
                    title: 'Card 5',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
                {
                    title: 'Card 6',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
                {
                    title: 'Card 7',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
                {
                    title: 'Card 8',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
                {
                    title: 'Card 9',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
                {
                    title: 'Card 10',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
                {
                    title: 'Card 11',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
                {
                    title: 'Card 12',
                    description: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
                    imageUrl: 'https://via.placeholder.com/150',
                    date: new Date(),
                },
            ],
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
        showMoreInfo(card) {
            console.log('More info for:', card.title);
            this.$router.push('/berita/show');
        },
    },
};
</script>

<style scoped>
.card-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

.card {
    width: 30%;
    padding: 10px;
    margin: 10px;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    align-items: center;
}

/* Additional styling for smaller screens */
@media (max-width: 768px) {
    .card {
        width: 45%;
    }
}

/* Additional styling for even smaller screens */
@media (max-width: 576px) {
    .card {
        width: 100%;
    }
}

.card-image {
    width: 100%;
    height: auto;
    border-radius: 8px;
    margin-bottom: 10px;
}

.card-content {
    text-align: center;
}

.card-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 10px;
}

.date {
    font-size: 0.8rem;
    color: #888;
    display: flex;
    align-items: center;
}

.date i {
    font-size: 1rem;
}

.more-info-btn {
    background-color: #3498db;
    color: white;
    padding: 6px 12px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 0.8rem;
    transition: background-color 0.3s;
}

.more-info-btn:hover {
    background-color: #2980b9;
}

hr {
    border: none;
    height: 8px;
    width: 60%;
    background-color: #0000ff;
    margin: 40px auto;
}

.card-all {
    width: 20%;
    padding: 20px;
    margin: 30px;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: justify;
}

/* Additional styling for smaller screens */
@media (max-width: 768px) {
    .card-all {
        width: 45%;
    }
}

/* Additional styling for even smaller screens */
@media (max-width: 576px) {
    .card-all {
        width: 90%;
    }
}

.card-all-image {
    width: 100%;
    height: auto;
    border-radius: 8px;
    margin-bottom: 10px;
}

.card-all-content {
    text-align: center;
}

.card-all-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 10px;
}
.card-all-content .description {
    text-align: justify;
    font-size: 0.7rem;
}
.card-content .description {
    font-size: 0.7rem;
    text-align: justify;
}

</style>
