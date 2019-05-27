<template>
  <div>
    name: {{fullname}}
    <br>
    <input ref="inputName" type="text">
    <button @click="changeName($refs.inputName.value)">test</button>
    <br>
    <input :class="nameClass" v-model.trim="name" type="text">
    <input :class="surnameClass" v-model="surname" type="text">
  </div>
</template>

<script>
export default {
  props: {
    initialName: {
      type: String,
      required: true
    },

    initialSurname: {
      type: String,
      required: true
    }
  },

  data() {
    return {
      name: "Vasja",
      surname: "Vassiljev"
    };
  },

  computed: {
    // properties
    fullname() {
      return `${this.name} ${this.surname}`;
    },

    nameClass() {
      return this.getInputClass(this.name);
    },

    surnameClass() {
      return this.getInputClass(this.surname);
    }
  },

  methods: {
    changeName(name) {
      this.name = name;
    },

    getInputClass(el) {
      if (el.length > 5) {
        return "first";
      } else {
        return "second";
      }
    }
  },

  mounted() {
    this.name = this.initialName;
    this.surname = this.initialSurname;
  },

  watch: {
    name(newVal, oldVal) {
      console.log(newVal + "<-" + oldVal);
      this.$emit("test", this.fullname); // mozhno this, togda vydast vsjo
    }
  }
};
</script>

<style scoped>
.first {
  background: grey;
}

.second {
  background: yellow;
}
</style>
>
>
>