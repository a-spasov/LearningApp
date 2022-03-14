<script>
import TableCourses from "@/components/TableCourses.vue";

export default {
  name: "TableActions",
  components: {
    TableCourses
  },
  data() {
    return {
      courses: ['Java Intro | Lorem ipsum Lorem ipsum dolor sit amet | 10 | 03-03-2021 | -', 
                'Python | Lorempsum dsectetur adipiscing | 12 | 28-02-2022 | https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ89NlVK9G8MUgOHgAGwXayi6Ev-vWq9ZHtRQ&usqp=CAU', 
                'C++ | - | 8 | - | -'],
      selected: '',
      show: false,
      showBoth: false,
      prefix: '',
      name: '',
      description: '',
      lessons: '',
      date: '',
      image: ''
    }
  },
  computed: {
    filteredNames() {
      console.log(this.prefix);
      return this.courses.filter((n) =>
        n.toLowerCase().startsWith(this.prefix.toLowerCase())
      )
    }
  },
  watch: {
    selected(course) {
      [this.name, this.description, this.lessons, this.date, this.image] = course.split(' | ');
    }
  },
  methods: {
    hasValidInput() {
      if (this.name && this.lessons) {
        return true;      
      } else if ((typeof Number(this.lessons) !== 'number') || (this.lessons == '')) {
          alert(`Lessons should be a number.`)
      } else {
        console.log(this.lessons);

          alert('Course name and number of lessons are required!');
      }
    },
    create() {
      if (this.hasValidInput() == true) {
        let result = [];
        let formData = [this.name, this.description, this.lessons, this.date, this.image];
        for (let data of formData) {
          if (data == undefined || data == '') {
            result.push('-');
          } else {
            result.push(data);
          }
        }
        const fullName = result.join(' | ');
        if (!this.courses.includes(fullName)) {
          this.courses.push(fullName);
          this.name = '';
          this.description = '';
          this.lessons = '';
          this.date = '';
          this.image = '';
        } else {
            alert('Course already added!');
        }
      }
    },
    update() {
      if (this.hasValidInput() && this.selected) {
        const i = this.courses.indexOf(this.selected);
        let formData = `${this.name} | ${this.description} | ${this.lessons} | ${this.date} | ${this.image}`;
        if (formData !== this.selected) {
          this.courses[i] = formData;
          this.selected = ``;
        } else {
          alert(`No changes made.`)
        }
      } else {
          alert('Please, select course!');
      }
    },
    del() {
      if (this.selected) {
        const i = this.courses.indexOf(this.selected);
        this.courses.splice(i, 1);
        this.selected = '';
        this.name = '';
        this.description = '';
        this.lessons = '';
        this.date = '';
        this.image = '';
      } else {
          alert('Please, select course!');
      }
    },
    clear() {
      this.selected = '';
    }  
  }
}
</script>

<template>
    
    <div class="form">
        <h2> Course info: </h2>
            <input v-model="name" class="input-big" placeholder="Course name...">
            <input v-model="lessons" type="number" class="input-small" placeholder="Number of lessons...">
            <input v-model="date" type="date" class="input-small" >
            <input v-model="image" type="url" class="input-big" placeholder="Enter image URL...">
            <div class="buttons">
                <button @click="create" class="btn-green" >Add course</button>
            </div>
            <h2>To update or delete course you can:</h2>
            <div><input v-model="prefix" placeholder="Filter prefix" class="input-big"></div>
            <select size="5" v-model="selected">
                <option v-for="(course) in courses" :key="course">{{ course }}</option>
            </select>
            <div class="buttons">
                <button @click="update" class="btn-yellow">UPDATE</button>
                <button @click="del" class="btn-red">DELETE</button>
                <button @click="clear" id="btn-clear">Clear selected</button>
            </div>
    </div>  
    <TableCourses v-bind:tableData=courses />
</template>

<style>
  .form {
    width: 100%;
    border-radius: 5px;
    background-color: #f2f2f2;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-around;
  }
  
  .form input {
    padding: 12px 20px;
    margin: 12px 0;
    box-sizing: border-box;
    border: 3px solid #ccc;
    border-radius: 6px;
    -webkit-transition: 0.5s;
    transition: 0.5s;
    outline: none;
  }
  .form input:focus {
    border: 3px solid #555;
  }
  .input-big {
    margin: auto;
    width: 95%;
  }
  .input-small {
    width: 45%;
    display: flex;
  }
  label {
    margin-top: 12px;
    display: block;
    text-align: left;
  }
  h2 {
    display: block;
  }
  .buttons {
    display: block;
  }
  #btn-clear {
    display: block;
    width: 150px;
    color: #ff1a1a;
    background-color: white;
    padding: 14px 20px;
    margin: 8px 10px;
    border-color: #ff1a1a;
    border-radius: 4px;
    cursor: pointer;
    font-weight: 700;
  }
  #btn-clear :hover {
    display: inline-block;
    width: 120px;
    background-color: #ff1a1a;
    color: white;
    padding: 14px 20px;
    margin: 8px 10px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-weight: 700;
  }
  .btn-green {
    display: block;
    width: 120px;
    background-color: #4CAF50;
    color: white;
    padding: 14px 20px;
    margin: 8px 10px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-weight: 700;
  }
  .btn-green:hover {
    background-color: #45a049;
  }
  .btn-yellow {
    display: inline-block;
    width: 120px;
    background-color: #ffd633;
    color: white;
    padding: 14px 20px;
    margin: 8px 10px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-weight: 700;
  }
  .btn-yellow:hover {
    background-color: #ffcc00;
  }
  .btn-red {
    display: inline-block;
    width: 120px;
    background-color: #ff1a1a;
    color: white;
    padding: 14px 20px;
    margin: 8px 10px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-weight: 700;
  }
  .btn-red:hover {
    background-color: #e60000;
  }
</style>