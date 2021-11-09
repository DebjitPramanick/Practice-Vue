<template>
  <div>
    <p>Getter setter: {{ fullName }}</p>
    <button @click="changeName">Change Name</button>
  </div>
</template>

<script>
export default {
  name: "GetterSetter",
  data() {
    return {
      name: {
        firstName: "Debjit",
        secondName: "Pramanick",
      },
    };
  },
  methods: {
    changeName() {
      this.fullName = "Richard Johanson";
    },
  },
  computed: {
    fullName: {
      get() {
        return `${this.name.firstName} ${this.name.secondName}`;
      },
      set(value) {
        const names = value.split(" ");
        console.log(names);
        this.name.firstName = names[0];
        this.name.secondName = names[1];
      },
    },
    total() {
      return 12;
    },
  },
};
</script>


data() {
    return {
      name: {
        firstName: "Debjit",
        secondName: "Pramanick",
      },
    };
  },
  methods: {
      changeName(){
          this.fullName = 'Richard Johanson'
      }
  },
  computed: {
      fullName: {
          get(){
              return `${this.firstName} ${this.secondName}`
          },
          set(value){
              const names = value.spli(' ')
              this.firstName = names[0]
              this.secondName = names[1]
          }
      }
  }
