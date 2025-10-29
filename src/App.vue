<template>
    <div class="main-view">
        <div class="main-split">
            <SideNavigation />
            <div class="main-content-wrapper">
                <main class="main-content">
                    <div class="title-block">
                        <h1>Главная</h1>
                        <h2>Статистика по кафедре ИиИТ</h2>
                    </div>
                    <div class="filters-section">
                        <label class="filter-block">
                            Семестр:
                            <select class="filter-select">
                                <option value="">Не выбрано</option>
                            </select>
                        </label>
                        <label class="filter-block">
                            Учебный год:
                            <select class="filter-select">
                                <option value="">Не выбрано</option>
                            </select>
                        </label>
                    </div>
                    <table class="main-table">
                        <thead>
                            <tr>
                                <th scope="col">Направление</th>
                                <th scope="col">Группа</th>
                                <th scope="col">Дисциплины</th>
                                <th scope="col">Электронный отчёт</th>
                                <th scope="col">Замечания по электронному отчёту</th>
                                <th scope="col">Бумажный отчёт</th>
                                <th scope="col">Замечания по бумажному отчёту</th>
                                <th scope="col">Всё сдано</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="item in list">
                                <th scope="row">{{item.direction}}</th>
                                <td>{{item.groupName}}</td>
                                <td>{{item.discipline}}</td>
                                <td>{{item.report}}</td>
                                <td>{{item.reportCount}}</td>
                                <td>{{item.paperReportCount}}</td>
                                <td>{{item.paperReportCommentsCount}}</td>
                                <td>
                                    <div class="checkbox-wrapper">
                                        <check-box v-model="item.isOver" />
                                    </div>
                                </td>
                            </tr>
                        </tbody>
                        <!--<tfoot>
                            <tr>
                                <th scope="row" colspan="2">Групп: 9/20</th>
                                <th scope="row">Групп: 9/20</th>
                                <th scope="row">Групп: 9/20</th>
                                <th scope="row">Дисциплин: 18/30</th>
                                <th scope="row">Эл. отчётов: 9/9</th>
                                <th scope="row">Замечаний: 6</th>
                                <th scope="row">Бум. отчётов: 9/9</th>
                                <th scope="row">Замечаний: 5</th>
                                <th scope="row">Сдано: 5/9</th>
                            </tr>
                        </tfoot>-->
                    </table>
                </main>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
.main-view {
    background: linear-gradient(180deg, rgba(95, 109, 236, 50%) 0%, rgba(255, 255, 255, 50%) 100%);
    .main-split {
        display: flex;
        flex-direction: row;
        .main-content-wrapper {
            width: 100%;
            height: 100%;
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 60px;
            justify-content: center;
            .main-content {
                background-color: white;
                border-radius: 30px;
                padding: 40px 60px;
                .title-block {
                    display: flex;
                    flex-direction: row;
                    gap: 150px;
                    h1, h2 {
                        font-size: 40px;
                        font-weight: bold;
                    }
                }
                .filters-section {
                    display: flex; 
                    flex-direction: row;
                    justify-content: center;
                    font-size: 20px;
                    font-weight: bold;
                    margin: 40px 0;
                    .filter-block {
                        display: flex;
                        align-items: center;
                        width: 100%;
                        max-width: 550px;
                        gap: 10px;
                        .filter-select {
                            width: 100%;
                            border-radius: 7px;
                            height: 40px;
                            border: none;
                            max-width: 400px;
                            padding: 0 10px;
                            color: #515151;
                            font-weight: 600;
                        }
                    }
                }
                .main-table {
                    max-width: 1200px;
                    width: 100%;
                    color: #515151;
                    font-size: 14px;
                    border-collapse: collapse;
                    border-radius: 7px;
                    border: 1px solid #DBDBDB;
                    .checkbox-wrapper {
                        width: 100%;
                        height: 100%;
                        display: flex;
                        align-items: center;
                        justify-content: center;
                    }
                    th, td {
                        border: 1px solid #DBDBDB;
                        padding: 16px 7.5px;
                    }
                    thead {
                    
                    }
                    tbody {
                        background-color: #EDEDF9; 
                        tr:nth-child(2n) {
                            background-color: white; 
                        }
                    }
                }
            }
        }
    }
}
</style>

<script>
import SideNavigation from '@/components/SideNavigation.vue'
import CheckBox from '@/components/CheckBox.vue'

export default {
	components: {
        SideNavigation,
        CheckBox,
    },
    data() {
        return {
            list: [
                {
                    direction: 'ИСИТ',
                    groupName: '231-332',
                    discipline: 'Дисциплина1, Дисциплина2',
                    report: 'отчёт.docx',
                    reportCount: 0,
                    paperReportCount: 1,
                    paperReportCommentsCount: 1,
                    isOver: true,
                },
                {
                    direction: 'ИСИТ',
                    groupName: '231-332',
                    discipline: 'Дисциплина1, Дисциплина2',
                    report: 'отчёт.docx',
                    reportCount: 0,
                    paperReportCount: 1,
                    paperReportCommentsCount: 1,
                    isOver: false,
                },
            ]
        }
    },
}
</script>

<!--
TODO:
Создание фронта для подсистемы Формирование справочника с перечнем групп, рекомендуемых для проверки остаточных знаний в текущем квартале
FIGMA:
https://www.figma.com/design/eoxrLNCFiCZi8D0VVF7q8e/%D0%9E%D1%81%D1%82%D0%B0%D1%82%D0%BE%D1%87%D0%BD%D1%8B%D0%B5-%D0%B7%D0%BD%D0%B0%D0%BD%D0%B8%D1%8F-2025?node-id=0-1&t=3zVYpPaKrmbSmydm-1
-->
