<template>
  <section>
      <h2 class="contact__title">Contact Me</h2>
      <div class="contact__wrapper">
          <form action="" class="contact__form">
              <input type="text"  name="name" required aria-required="required"
                placeholder="Name" aria-placeholder="Name" v-model="name" 
                id="formName" class="contact__input" aria-label="Name">
              <input type="text" name="email" required aria-required="required"
                placeholder="Email" aria-placeholder="Email" v-model="email" 
                id="formEmail" class="contact__input" aria-label="Email">
              <input type="text" name="phone" required aria-required="required"
                placeholder="Phone" aria-placeholder="Phone" v-model="phone" 
                id="formPhone" class="contact__input" aria-label="Phone">
              <textarea type="text" name="message" required aria-required="required"
                placeholder="Message" aria-placeholder="Message" v-model="message" 
                id="formMsg" class="contact__input" maxlength="260" rows="1" aria-label="Message"></textarea>
              <input type="submit" class="contact__submit" name="submit" aria-label="Submit Button" value="Send">
          </form>
          <div class="contact__questions">
              <h2 class="contact__title">Ask About These</h2>
              <ul class="contact__questionsList">
                  <li class="contact__question" v-for="question in questions" :key="question.id">{{ question.content }}</li>
              </ul>
          </div>
          <p class="contact__extra">Do not hesitate to ask about anything else that isn’t on the list. These are just common questions, or answers I can get to you quickly.</p>
      </div>
  </section>
</template>

<script>
export default {
    data() {
        return {

          name: '',
          email: '',
          phone: '',
          message: '',

            questions: [
                {id: 0, content: 'Lorem ipsum dolor sit amet, consectetur'},
                {id: 1, content: 'sed do eiusmod tempor incididunt'},
                {id: 2, content: 'Ut enim ad minim veniam, quis nostrud'},
                {id: 3, content: 'exercitation ullamco laboris'},
                {id: 4, content: 'Excepteur sint occaecat cupidatat non proident, sunt'},
            ]
        }
    }
}
</script>

<style>

</style>