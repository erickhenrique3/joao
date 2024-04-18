<script>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'

export default {
  data() {
    return {
      text: '',
      count: 0,
      count2: 0,
      firstArray: ['joao', 'lucas', 'pedro', 'guilherme']
    }
  },
  methods: {
    addStudent() {
      if (this.firstArray.lenght >= 10) {
        return
      }
      this.firstArray.push(this.text),
        this.text = ''
        console.log(this.sumCount);
    },
    removeLastStudent() {
      this.firstArray.pop()
    },
    removeStudent(index) {
      this.firstArray.splice(index, 1)
    }
  },
  created() {
    this.firstArray.push('joao');
  },
  computed: {
    sumCount() {
      return this.count + this.count2
    }
  },
}


</script>


<template>
  <header>
    <div>
      <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />
      a
    </div>
    <div class="wrapper">
      <button @click="count--">-</button>/>
      <h1 :class="count > 10 ? 'green' : ''">{{ count }}</h1>
      <button @click="count++">+</button>
    </div>
    <div class="wrapper">
      <button @click="count2--">-</button>/>
      <h1 :class="count > 10 ? 'green' : ''">{{ count }}</h1>
      <button @click="count2++">+</button>
    </div>
    <p>A soma desses dois valores é {{ sumCount }}</p>
    <section>
      <input type="text" v-model="text" @keyup.enter="assStudent()">
      <button :disabled="firstArray.lenght >= 10" @click="addStudent()">Adicionar nome!</button>
      <p style="color: red;" v-show="firstArray.lenght >= 10">Limite de itens atingido!</p>
      <button @click="removeLastStudent()">Remover nome!</button>
      <div v-for="(student, index) in firstArray" :key="student">
        <span>{{ student }}</span>
        <button @click="removeStudent(index)">Remover {{ student }}</button>
      </div>
    </section>
  </header>
  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
