<template>
    <section class="side-navigation">
        <img class="polytech-logo" src="../assets/icons/PolytechLogo.svg" alt="Московский политех" />
        <hr/>
        <h2 class="page-group-title">Проверка<br>остаточных знаний</h2>
        <div class="user-widget">
            <div class="user-profile-image-block">
                <img 
                    v-if="userProfileImageUrl"
                    class="user-profile-image"
                    :src="userProfileImageUrl"
                    alt="Фотография профиля"
                >
            </div>
            <div class="user-name-block">
                <b class="user-last-name">Иванов</b>
                <b class="user-name">Иван Иванович</b>
            </div>
        </div>
        <nav class="side-navigation-nav">
            <ul class="side-navigation-links-list">
                <li class="side-navigation-link selected">Главная</li>
                <li class="side-navigation-link">Выбор групп</li>
                <li class="side-navigation-link">Выбор дисциплин</li>
                <li class="side-navigation-link">Выбор преподавателей</li>
            </ul>
        </nav>
    </section>
</template>

<style lang="scss">
.side-navigation {
    background-color: white;
    border-radius: 0 30px 30px 0;
    color: #515151;
    font-size: 20px;
    height: 100vh;
    width: 100%;
    max-width: 368px;
    padding: 30px 60px;

    .polytech-logo {
        width: 100%;
    }
    .page-group-title {
        color: #5F6DEC;
        font-size: 20px;
        font-weight: 600;
        margin: 7px 0;
    }
    .user-widget {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 40px 0;
        .user-profile-image-block {
            background-color: #D9D9D9;
            border-radius: 100%;
            width: 100px;
            height: 100px;
            overflow: hidden;
        }
        .user-name-block {
	        font-variation-settings: 'wght' 600;
            display: flex;
            flex-direction: column;
            align-items: center;
            font-weight: bold;
        }
    }
    .side-navigation-nav {
        padding: 20px 0;
        font-weight: bold;
        .side-navigation-links-list {
            list-style-type: none;
            display: flex;
            flex-direction: column;
            gap: 20px;
            .side-navigation-link {
            
            }
            .selected {
                color: #5F6DEC;

            }
        }
    }
}
</style>

<script>
export default {
    data() {
        return {
            userProfileImageUrl: null,
            userLastName: 'Иванов',
            userName: 'Иван Иванович',
        }
    }
}
</script>
