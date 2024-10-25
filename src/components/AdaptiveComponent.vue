<template>
  <div class="adaptive-component">

    <!-- Блок с изображением стола и кнопками -->
    <div class="table-container">
      <!-- Изображение ножек стола -->
      <img
          class="table-container__image table-container__image--legs"
          src="../assets/table-legs.png"
          alt="Ножки стола"
      />

      <!-- Изображение столешницы с динамическим изменением позиции -->
      <img
          class="table-container__image table-container__image--top"
          src="../assets/table-top.png"
          :style="{ transform: `translateY(${tablePosition}px)` }"
          alt="Столешница"
      />
      <div class="table-container__buttons">
        <!-- Кнопка для подъема столешницы -->
        <button @click="moveUp" class="table-container__button table-container__button--up">
          <span class="table-container__button-text">вверх</span>
        </button>

        <!-- Кнопка для опускания столешницы -->
        <button @click="moveDown" class="table-container__button table-container__button--down">
          <span class="table-container__button-text">вниз</span>
        </button>
      </div>
    </div>

    <!-- Текстовый блок с заголовком и описанием -->
    <div class="adaptive-component__text adaptive-component__text--first">

      <div class="adaptive-component__title">
        Эргономика — <br />
        ключ к успеху <br />
        современного <br />
        человека
      </div>

      <!-- Первое текстовое описание -->
      <div class="adaptive-component__description">
        Стильная столешница, выполненной <br /> из экологически безопасного материала (ДСП), <br /> и усиленной
        стальной рамы не составит труда <br /> разместить на поверхности инновационного <br /> стола большое
        количество крупногабаритной <br /> техники: стол выдерживает нагрузку до 80 кг.
      </div>

      <!-- Второе текстовое описание -->
      <div class="adaptive-component__text adaptive-component__text--second">
        <div class="adaptive-component__description">
          Также столешница, обладающая меламиновым <br /> покрытием, хорошо переносит механические <br />
          воздействия (царапины или удары), <br /> при контакте с водой не разрушается, устойчиво <br /> переносит
          бытовые химические вещества <br /> и не выгорает под воздействием <br /> ультрафиолета.
        </div>
      </div>

    </div>


  </div>
</template>

<style scoped>
/* Общие стили */
.adaptive-component {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  width: 100%;
  padding: 2rem;
  max-width: 1920px;
  max-height: 900px;

}

.adaptive-component__title {
  color: #0b64fe;
  font-size: 2rem;
  font-family: var(--second-family);
  font-weight: 300;
  line-height: 1.2;
  margin-bottom: 1rem;
  text-align: left;
  max-width: 647px;
  max-height: 219px;
}

.adaptive-component__text {
  display: flex;
  flex-direction: column;
  width: 100%;
  margin: 0;
  max-width: 500px;
  max-height: 416px;
}

.adaptive-component__description {
  color: #181818;
  font-size: 1rem;
  font-family: var(--second-family);
  font-weight: 300;
  text-align: left;
  margin-bottom: 1rem;
  line-height: 170%;
  max-width: 500px;
  max-height: 416px;
}

.table-container {
  position: relative;
  width: 100%;
  height: auto;
  margin-top: -30px;
  max-width: 1477px;
  max-height: 985px;
  margin-right: 70px;
}

.table-container__image {
  width: 100%;
  height: auto;
  object-fit: contain;
}

.table-container__image--top {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
  width: 130%;
}

.table-container__image--legs {
  position: relative;
  z-index: 0;
  width: 130%;
}

.table-container__buttons {
  position: absolute;
  bottom: 150px;
  left: 48%;
  transform: translateX(0);
  display: flex;
  gap: 1rem;
  z-index: 2;
  font-family: var(--second-family);
  text-transform: uppercase;
}

.table-container__button {
  background: #a6ffff;
  border: none;
  border-radius: 50%;
  color: black;
  font-size: 1.5rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 6rem;
  height: 6rem;
  transition: background 0.3s ease;
}

.table-container__button-text {
  font-family: var(--second-family);
  font-weight: 300;
  font-size: 0.8rem;
  line-height: 170%;
  color: #000;
}

.table-container__button:hover {
  background: #7de0ff;
}

/* Медиазапрос для экрана 320x998 */
@media (max-width: 320px) and (max-height: 998.41px) {
  .adaptive-component {
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 1rem;
    width: 100vw;
  }

  .table-container {
    order: 2;
    margin-top: -150px;
    margin-bottom: 1.5rem;
    width: 90vw;
  }

  .adaptive-component__title {
    text-align: left;
    font-size: 1.5rem;
    font-weight: 900;
  }

  .adaptive-component__text--first {
    order: 1;
    margin-bottom: 10px;
  }

  .adaptive-component__text--second {
    order: 3;
    margin-top: 190px;
  }

  .adaptive-component__text {
    width: 100%;
    text-align: center;
  }

  .adaptive-component__description {
    font-size: 0.9rem;
    line-height: 170%;
  }

  .table-container__image {
    width: 100%;
  }

  .table-container__button {
    width: 3rem;
    height: 3rem;
    font-size: 0.7rem;
  }

  .table-container__buttons {
    bottom: 20%;
    transform: translateX(-46%);
    width: 50vw;
    justify-content: center;
    align-items: center;
  }

  .table-container__button-text {
    font-size: 0.7rem;
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
