<template>
  <div class="home">
    <div class="container">
      <h1 class="home__title">Создать резюме онлайн</h1>
      <form class="home__form" @submit.prevent="next">
        <div class="home__form-row">
          <input
            v-model="user.name"
            type="text"
            required
            placeholder="Имя"
            class="home__form-inp"
          />
          <input
            v-model="user.surname"
            type="text"
            required
            placeholder="Фамилия"
            class="home__form-inp"
          />
        </div>
        <div class="home__form-row">
          <input
            v-model="user.age"
            type="text"
            placeholder="Возраст"
            required
            class="home__form-inp"
          />
          <input
            v-model="user.position"
            type="text"
            placeholder="Должность"
            required
            class="home__form-inp"
          />
        </div>
        <div class="home__form-row">
          <input
            v-model="user.phoneNumber"
            type="text"
            placeholder="Номер телефона"
            required
            class="home__form-inp"
          />
          <input
            v-model="user.email"
            type="text"
            placeholder="Email"
            required
            class="home__form-inp"
          />
        </div>
        <textarea
          required
          v-model="user.about"
          placeholder="Обо мне"
          class="home__form-textarea"
          cols="30"
          rows="10"
        ></textarea>
        <div class="home__form-row">
          <div class="home__form-add">
            <div class="home__form-group">
              <input
                required
                v-for="(skill, index) in user.skills"
                :key="index"
                v-model="user.skills[index]"
                placeholder="Навыки"
                type="text"
              />
            </div>
            <div class="home__form-add-btn btn" @click="user.skills.push('')">
              Добавить ещё
            </div>
          </div>
          <div class="home__form-add">
            <div class="home__form-group">
              <input
                v-for="(award, index) in user.awards"
                :key="index"
                v-model="user.awards[index]"
                placeholder="Награды"
                type="text"
              />
            </div>
            <div class="home__form-add-btn btn" @click="user.awards.push('')">
              Добавить ещё
            </div>
          </div>
        </div>
        <div class="home__form-projects">
          <div class="home__form-group">
            <div class="home__form-proj-info">
              <input
                required
                v-for="(project, index) in user.projects"
                :key="index"
                v-model="user.projects[index].name"
                placeholder="Проект"
                type="text"
              />
            </div>
            <div class="home__form-proj-info">
              <input
                required
                v-for="(project, index) in user.projects"
                :key="index"
                v-model="user.projects[index].url"
                placeholder="Ссылка на проект"
                type="text"
              />
            </div>
          </div>
          <div
            class="home__form-add-btn btn"
            @click="user.projects.push({ name: '', url: '' })"
          >
            Добавить ещё
          </div>
        </div>
        <div class="home__form-next-wrapper">
          <button class="home__form-next">Создать личное резюме</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      user: {
        name: "",
        surname: "",
        age: "",
        position: "",
        phoneNumber: "",
        email: "",
        about: "",
        skills: [""],
        awards: [""],
        projects: [{ name: "", url: "" }],
      },
    };
  },
  methods: {
    next() {
      localStorage.user = JSON.stringify(this.user);
      this.$router.push("/templates");
    },
  },
};
</script>

<style lang="scss">
.home__title {
  margin-top: 70px;
}

.home__form {
  width: 100%;
  margin-top: 40px;
  padding-bottom: 15px;

  .home__form-row {
    display: flex;
    justify-content: space-between;

    &:not(:first-child) {
      margin-top: 20px;
    }

    input {
      width: 49%;
    }

    .home__form-add {
      width: 49%;
      input {
        width: 100%;
        &:not(:first-child) {
          margin-top: 10px;
        }
      }

      .home__form-add-btn {
        margin-top: 8px;
      }
    }
  }

  .home__form-projects {
    width: 100%;
    margin-top: 20px;
    .home__form-group {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      .home__form-proj-info {
        width: 49%;
      }
      input {
        width: 100%;

        &:not(:first-child) {
          margin-top: 10px;
        }
      }
    }
    .home__form-add-btn {
      margin-top: 8px;
    }
  }

  @media (max-width: 720px) {
    .home__form-row {
      flex-direction: column;

      &:not(:first-child) {
        margin-top: 20px;
      }

      input {
        width: 100%;
        margin-top: 8px;
      }

      .home__form-add {
        width: 100%;
        &:not(:first-child) {
          margin-top: 20px;
        }
      }
    }
  }

  .home__form-textarea {
    min-width: 100%;
    max-width: 100%;
    margin-top: 20px;
  }

  .home__form-next-wrapper {
    width: 100%;
    display: flex;
    justify-content: center;
  }

  .home__form-next {
    width: 300px;
    margin-top: 50px;
    background-color: #00dc7d;
  }
}
</style>
