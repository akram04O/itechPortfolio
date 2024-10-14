<template>
    <div class="survey-form">
      <h2>Survey Form</h2>
      <form @submit.prevent="submitForm">
        <div v-for="(question, index) in questions" :key="index" class="question">
          <label>{{ question.label }}</label>
          <input v-if="question.type === 'text'" v-model="question.answer" :type="question.type" />
          <div v-else-if="question.type === 'radio'">
            <div v-for="(option, i) in question.options" :key="i">
              <input type="radio" :name="'q' + index" :value="option" v-model="question.answer" />
              <label>{{ option }}</label>
            </div>
          </div>
          <div v-else-if="question.type === 'checkbox'">
            <div v-for="(option, i) in question.options" :key="i">
              <input type="checkbox" :value="option" v-model="question.answer" />
              <label>{{ option }}</label>
            </div>
          </div>
        </div>
        <button type="submit">Submit</button>
      </form>
    </div>
  </template>
  
  <script>
  import * as XLSX from "xlsx";
  
  export default {
    data() {
      return {
        questions: [
          { label: 'What is your name?', type: 'text', answer: '' },
          { label: 'What is your Email?', type: 'text', answer: '' },
          { label: 'What is your Phone number?', type: 'text', answer: '' },
          { label: 'What is your Academic level?', type: 'text', answer: '' },
          { label: 'What is your Speciality?', type: 'text', answer: '' },
          { label: 'What is your Soft skills?', type: 'text', answer: '' },
          { label: 'Hard skills', type: 'radio', options: ['Programming', 'Vidéo editing', 'Photography', 'Graphic design'], answer: '' },
          { label: 'Have you ever been in any other clubs, associations...ect?', type: 'checkbox', options: ['Club', 'Association', 'Student organizations', 'None'], answer: [] },
          {label:'Tell us about your experience(if you have one)', type: 'text', answer: ''},
          { label: 'Which one of the next department do you think it suitable for you?', type: 'checkbox', options: ['Coding', 'Organizing', 'Design', 'Multimédia', 'Robotic'], answer: [] },
          { label: 'Tell us why you want to join this club?', type: 'text', answer: '' },


        ]
      };
    },
    methods: {
      submitForm() {
        const questionsRow = this.questions.map(q => q.label);
        const answersRow = this.questions.map(q => q.answer);
        const data = [questionsRow, answersRow];
  
        /* Create a new workbook and add a worksheet */
        const ws = XLSX.utils.json_to_sheet(data);
        const wb = XLSX.utils.book_new();
        XLSX.utils.book_append_sheet(wb, ws, "Survey Results");
  
        /* Generate Excel file */
        XLSX.writeFile(wb, "survey_results.xlsx");
      }
    }
  };
  </script>
  
  <style>
  .survey-form {
    max-width: 500px;
    margin: auto;
    padding: 20px;
    border: 1px solid #ccc;
  }
  .question {
    margin-bottom: 15px;
  }
  </style>
  