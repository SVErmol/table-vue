<template>
  <div>
    <vue-good-table :columns="columns" :rows="rows" max-height="200px"  :search-options="{ enabled: true }"
  :fixed-header="true"   :pagination-options="{
    enabled: true,
    perPageDropdown: [3, 7, 9],
    nextLabel: 'Вперед',
    prevLabel: 'Назад',
    rowsPerPageLabel: 'Показывать по',
    ofLabel: 'из',
  }">

                <!-- :search-options="{  placeholder: 'Поиск по таблице', enabled: true }" -->
                <template slot="table-row" scope="props">

                    <span v-if="props.column.field == 'registration'">
                        <span>
                            <select v-model="props.row.registration" name="" id="">
                                <option value="true">Да</option>
                                <option value="false">Нет</option>
                            </select> </span>
                    </span>
                    <span v-else-if="props.column.field == 'participation_earlier'">
                        <span>
                            <select v-model="props.row.participation_earlier" name="" id="">
                                <option value="true">Да</option>
                                <option value="false">Нет</option>
                            </select> </span>
                    </span>
                    <span v-else>
      {{props.formattedRow[props.column.field]}}
    </span>

                </template>
            </vue-good-table>
  </div>
</template>

<script>
import { VueGoodTable } from 'vue-good-table';
import 'vue-good-table/dist/vue-good-table.css'
export default {
  data() {  return {
            items: [

            ], columns: [
                {
                    label: 'Id',
                    field: 'id',
                },
                {
                    label: 'Фамилия',
                    field: 'surname',
                    filterOptions: {
                        enabled: true, placeholder: 'Фамилия'
                    }
                },
                {
                    label: 'Имя',
                    field: 'name',
                    filterOptions: {
                        enabled: true, placeholder: 'Фамилия'
                    }
                },
                {
                    label: 'Отчество',
                    field: 'patronymic',
                },
                {
                    label: 'Возраст',
                    field: 'age',
                },
                {
                    label: 'Дата рождения',
                    field: 'birthday',
                    type: 'date',
                    dateInputFormat: 'yyyy-MM-dd',
                    dateOutputFormat:'yyyy-MM-dd',
                },
                {
                    label: 'Город',
                    field: 'city',
                },
                {
                    label: 'Регистрация в турнире',
                    field: 'registration',
                },
                {
                    label: 'Разряд',
                    field: 'category',
                    filterOptions: {
                        enabled: true, placeholder: 'Разряд'
                    }

                },
                {
                    label: 'Участвовал ранее',
                    field: 'participation_earlier',
                },

            ],
            rows: [
                { id: 1, surname: "Иванов", name: "Иван", patronymic: "Иванович", age: 58, birthday: '1964-10-02', city: "Красноярск", registration: true, category: "1", participation_earlier: true },
                { id: 2, surname: "Толбанов", name: "Евгений", patronymic: "Севастьянович", age: 54, birthday: '1968-09-09', city: "Москва", registration: false, category: "КМС", participation_earlier: false },
                { id: 3, surname: "Завражнова", name: "Ксения", patronymic: "Романовна", age: 60, birthday: '1962-09-06', city: "Тюмень", registration: false, category: "1", participation_earlier: true },
                { id: 4, surname: "Шелепов", name: "Трофим", patronymic: "Денисович", age: 55, birthday: '1967-05-02', city: "Пермь", registration: true, category: "КМС", participation_earlier: false },
                { id: 5, surname: "Зверев", name: "Виктор", patronymic: "Герасимович", age: 56, birthday: '1966-06-25', city: "Иркутск", registration: true, category: "1", participation_earlier: true },
                { id: 6, surname: "Кожухова", name: "Лариса", patronymic: "Семеновна", age: 52, birthday: '1970-03-28', city: "Ульяновск", registration: false, category: "1", participation_earlier: true },
                { id: 7, surname: "Стукалова", name: "Нонна", patronymic: "Степановна", age: 54, birthday: '1968-05-15', city: "Хабаровск", registration: true, category: "КМС", participation_earlier: true },
                { id: 8, surname: "Шикалов", name: "Арсений", patronymic: "Александрович", age: 52, birthday: '1970-01-23', city: "Иркутск", registration: true, category: "1", participation_earlier: true },
                { id: 9, surname: "Тарасов", name: "Василий", patronymic: "Максимович", age: 61, birthday: '1961-06-25', city: "Казань", registration: true, category: "КМС", participation_earlier: false },
                { id: 10, surname: "Большова", name: "Кира", patronymic: "Ростиславовна", age: 52, birthday: '1970-05-17', city: "Казань", registration: true, category: "КМС", participation_earlier: false },
            ],


        }},
  name: 'HelloWorld',
  props: {
    msg: String
  },components: {
      VueGoodTable
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
