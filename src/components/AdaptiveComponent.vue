<template>
    <div class="wrapper">
        <!-- Блок с изображением стола и кнопками -->
        <div class="table-container">
            <img
                class="table-container__image-top"
                src="../assets/table-top.png"
                :style="{ transform: `translateY(${tablePosition}px)` }"
                alt="Столешница"
            />
            <img
                class="table-container__image-legs"
                src="../assets/table-legs.png"
                alt="Ножки стола"
            />
            <!-- Кнопки  -->
            <div class="table-container__buttons">
                <button @click="moveUp" class="table-container__button-up">
                    <span class="table-container__button-text">вверх</span>
                </button>

                <button @click="moveDown" class="table-container__button-down">
                    <span class="table-container__button-text">вниз</span>
                </button>
            </div>
        </div>

        <!-- Текстовый блок с заголовком и описанием -->
        <div class="text-container">
            <div class="text-container__title">
                Эргономика — <br />
                ключ к успеху <br />
                современного <br />
                человека
            </div>

            <!-- Первое текстовое описание -->
            <div class="text-container__first-description">
                Стильная столешница, выполненной <br />
                из экологически безопасного материала (ДСП), <br />
                и усиленной стальной рамы не составит труда <br />
                разместить на поверхности инновационного <br />
                стола большое количество крупногабаритной <br />
                техники: стол выдерживает нагрузку до 80 кг.
            </div>

            <!-- Второе текстовое описание -->
            <div class="text-container__second-description">
                Также столешница, обладающая меламиновым <br />
                покрытием, хорошо переносит механические <br />
                воздействия (царапины или удары), <br />
                при контакте с водой не разрушается, устойчиво <br />
                переносит бытовые химические вещества <br />
                и не выгорает под воздействием <br />
                ультрафиолета.
            </div>
        </div>
    </div>
</template>

<style scoped>
.wrapper {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    height: 100vh;
    padding: 0;
    margin: 0;
    overflow: hidden;
}

.table-container {
    position: absolute;
    max-width: 1476.76px;
    max-height: 984.7px;
}

.table-container,
.text-container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
}

.table-container__image-top,
.table-container__image-legs {
    max-width: 100%;
    height: auto;
}

.table-container__image-top {
    position: absolute;
    display: flex;
    justify-content: center;
    width: 70%;
    height: auto;
    z-index: 1;
}

.table-container__image-legs {
    position: relative;
    display: flex;
    justify-content: center;
    width: 70%;
    height: auto;
    z-index: 0;
}

.table-container__buttons {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 70%;
    bottom: 290px;
    z-index: 2;
    gap: 30px;
}

.table-container__button-up,
.table-container__button-down {
    background: rgb(166, 255, 255);
    border-radius: 50%;
    border: none;
    width: 110.22px;
    height: 110.22px;
}

.table-container__button-text {
    color: rgb(0, 0, 0);
    text-transform: uppercase;
    font-family: var(--second-family);
    font-size: 1.1rem;
    font-weight: 300;
    line-height: 170%;
    letter-spacing: 0%;
    text-align: center;
}

.text-container {
    position: absolute;
    left: 60%;
    width: 70%;
}

.text-container__title {
    position: relative;
    color: rgb(11, 100, 254);
    font-family: var(--second-family);
    font-size: 2.3rem;
    font-weight: 300;
    letter-spacing: 0%;
    text-align: left;
    top: 25.59px;
}

.text-container__first-description {
    position: relative;
    top: 2.5rem;
}

.text-container__second-description {
    position: relative;
    top: 3.5rem;
}

.text-container__first-description,
.text-container__second-description {
    position: relative;
    color: rgb(24, 24, 24);
    font-family: var(--second-family);
    font-size: 0.8rem;
    font-weight: 300;
    line-height: 170%;
    letter-spacing: 0%;
    text-align: left;
}

@media (max-width: 400px) {
    .wrapper {
        flex-direction: column;
        height: auto;
        min-height: 100vh;
        margin: 0;
        padding: 0;
    }

    .table-container {
        position: relative;
        width: 165%;
        max-width: none;
        order: 2;
    }

    .table-container__image-top,
    .table-container__image-legs {
        width: 100%;
        height: auto;
        bottom: 160px;
    }

    .table-container__image-top {
        top: -580px;
        width: 150%;
        left: -20%;
    }

    .table-container__image-legs {
        top: -580px;
        width: 150%;
        left: -20%;
    }

    .table-container__buttons {
        width: 100%;
        bottom: 750px;
        gap: 15px;
        left: -20%;
    }

    .table-container__button-up,
    .table-container__button-down {
        width: 90px;
        height: 90px;
    }

    .table-container__button-text {
        font-size: 0.7rem;
    }

    .text-container {
        position: relative;
        left: 0;
        width: 100%;
        order: 1;
    }

    .text-container__title {
        font-family: var(--fourth-family);
        font-size: 2.6rem;
        font-weight: 600;
        line-height: 100%;
        letter-spacing: 0%;
        text-align: left;
        top: 13.57px;
        padding-left: 12.12px;
        padding-right: 12.12px;
    }

    .text-container__first-description,
    .text-container__second-description {
        font-size: 1.4rem;
        top: 1rem;
        margin-bottom: 30rem;
        padding-left: 12.12px;
        padding-right: 12.12px;
    }

    .text-container__first-description {
        padding-top: 3rem;
    }

    .text-container__second-description {
        position: relative;
        margin-top: 1rem; 
        margin-bottom: -13rem;
    }

    br {
        display: none;
    }
}
</style>

<script setup>
import { ref } from 'vue';

// Создаем реактивную переменную для позиции столешницы
const tablePosition = ref(0); // Исходное положение

// Максимальная и минимальная позиция
const maxPosition = 20; // Максимальный подъем
const minPosition = -20; // Максимальное опускание

// Функция для подъема столешницы
const moveUp = () => {
    // Проверяем, меньше ли текущее значение максимального опускания
    if (tablePosition.value > minPosition) {
        tablePosition.value -= 10; // Двигаем вверх на 10px
    }
};

// Функция для опускания столешницы
const moveDown = () => {
    // Проверяем, больше ли текущее значение максимального подъема
    if (tablePosition.value < maxPosition) {
        tablePosition.value += 10; // Двигаем вниз на 10px
    }
};
</script>
