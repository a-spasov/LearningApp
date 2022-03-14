<script>
export default {
  name: "TableCourses",
  props: {
    tableData: Array,
  }
}
</script>

<template>
    <div class="course-list-row" >
        <table >
          <thead>
              <tr>
                  <th>ID</th>
                  <th>Course name</th>
                  <th>Description</th>
                  <th>Number of lessons</th>
                  <th>State</th>
                  <th>Date added</th>
                  <th>Image</th>
              </tr>
          </thead>
          <tbody>
              <tr v-for="(data) in tableData" :key="data" >
                  <td>{{tableData.indexOf(data) + 1}} </td>
                  <td>{{ data.split(' | ')[0]}}</td>
                  <td>{{ data.split(' | ')[1]}}</td>
                  <td>{{ data.split(' | ')[2]}}</td>
                  <td> 
                      <select name="state">
                          <option value="active">Active</option>
                          <option value="archived">Archived</option>
                      </select>
                  </td>
                  <td>{{ data.split(' | ')[3]}}</td>
                  <td>
                    <img v-if="data.split(' | ')[4] == '-'" alt="Logo picture" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSIyJIXtEKyTFsqiS0BEywz9jQ6ZvDD-gVieg&usqp=CAU">
                    <img v-else alt="Course picture" v-bind:src="data.split(' | ')[4]">
                  </td>
              </tr>
          </tbody>       
        </table>
    </div>
</template>

<style>
  table {
    border: 2px solid black;
    font-family: Arial, Helvetica, sans-serif;
    border-collapse: collapse;
    width: 100%;
    margin: auto;
    margin-top: 40px;
  }
  th, td {
    border: 1px solid #ddd;
  }
  tr:nth-child(even) {
    background-color: #f2f2f2;
  }
  tr:hover {
    background-color: #ddd;
  }
  th {
    text-align: center;
    background-color: #2fb62f;
    color: white;
    font-weight: 700;
    font-size: 18px;
    padding: 12px 8px;
  }
  tbody {
    border: 2px solid black;
  }
  td img {
    margin: auto;
    height: 70px;
    object-fit: contain;
    float: none;
    border-radius: 33px;
  }
</style>