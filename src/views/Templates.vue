<template>
  <div class="templates">
    <div class="templates__wrapper">
      <div class="templates__template">
        <div class="template__header">
          <div class="template__title">
            {{ `${user.name} ${user.surname}` }}
          </div>
          <div class="template__position">{{ user.position }}</div>
          <div class="template__phone">{{ user.phoneNumber }}</div>
        </div>
        <div class="template__content">
          <div class="template__content-col template__content-left">
            <div class="template__content-info">
              <div class="template__content-title">Обо мне</div>
              <div class="template__content-desc">{{ user.about }}</div>
            </div>
            <div class="template__content-info">
              <div class="template__content-title">Награды</div>
              <div
                class="template__content-desc"
                v-for="award in user.awards"
                :key="award"
              >
                {{ award }}
              </div>
            </div>
            <div class="template__content-info">
              <div class="template__content-title">Контакты</div>
              <div class="template__content-desc">{{ user.phoneNumber }}</div>
              <div class="template__content-desc">{{ user.email }}</div>
            </div>
          </div>

          <div class="template__content-col template__content-right">
            <div class="template__content-info">
              <div class="template__content-title">Проекты</div>

              <div
                class="template__content-desc"
                v-for="project in user.projects"
                :key="project.key"
              >
                <a :href="project.url">
                  {{ project.name }}
                </a>
              </div>
            </div>
            <div class="template__content-info">
              <div class="template__content-title">Навыки</div>
              <div
                class="template__content-desc"
                v-for="skill in user.skills"
                :key="skill"
              >
                {{ skill }}
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="templates__btn-download">
        <a href="#" class="templates__download">Скачать</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: JSON.parse(localStorage.user),
    };
  },
  mounted() {},
};
</script>

<style lang="scss">
$blue: #1771f1;

.templates {
  padding-bottom: 30px;
}

.templates__template {
  width: 21cm;
  height: 29.7cm;
  margin: 80px auto;
  background-color: #fff;
  color: #000;

  .template__header {
    width: 100%;
    height: 6.5cm;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: #000;
    color: #fff;
    text-align: center;

    .template__title {
      font-size: 40px;
      font-weight: 600;
    }

    .template__position {
      margin-top: 0.2cm;
      font-size: 16px;
      letter-spacing: 6px;
      text-transform: uppercase;
    }

    .template__phone {
      margin-top: 0.5cm;
      font-size: 15px;
      font-weight: 600;
    }
  }

  .template__content {
    padding-top: 70px;
    display: flex;
    justify-content: space-between;

    .template__content-info {
      &:not(:first-child) {
        margin-top: 43px;
      }
      a {
        color: #000;
      }
    }

    .template__content-col {
      min-width: 9.5cm;
      max-width: 9.5cm;
      min-height: 22cm;
      max-height: 22cm;

      .template__content-title {
        display: inline-block;
        padding: 7px 20px;
        background-color: #000000;
        color: #fff;
        font-size: 25px;
        font-weight: 600;
      }

      .template__content-desc {
        margin-top: 15px;
        color: #111111;
        font-size: 16px;
        font-weight: 500;
      }
    }

    .template__content-left {
      padding-left: 25px;
    }
    .template__content-right {
      padding-right: 25px;
    }
  }
}

.templates__btn-download {
  width: 100%;
  margin-top: -50px;
  display: flex;
  justify-content: center;
}

.templates__download {
  padding: 13px 30px;
  background-color: $blue;
  color: #fff;
  font-size: 18px;
  text-decoration: none;
}
</style>

</style>