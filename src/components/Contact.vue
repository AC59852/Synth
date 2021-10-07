<template>
  <section>
      <h2>Contact Me</h2>
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
                id="formMsg" class="contact__input" maxlength="260" aria-label="Message">
              </textarea>
              <input type="submit" class="contact__submit" name="submit" aria-label="Submit Button" value="Send">
          </form>
          <div class="contact__questions">
              <h2>Ask About These</h2>
              <ul class="contact__questionsList">
                  <li class="contact__question" v-for="question in questions" :key="question.id">{{ question.content }}</li>
              </ul>
              <span>Do not hesitate to ask about anything else that isn’t on the list. These are just common questions, or answers I can get to you quickly.</span>
          </div>
      </div>
  </section>
</template>

<script>
export default {
    data() {
        return {
            questions: [
                {id: 0, content: 'Question One'},
                {id: 1, content: 'Question Two'},
                {id: 2, content: 'Question Three'},
                {id: 3, content: 'Question Four'},
                {id: 4, content: 'Question Five'},
            ]
        }
    }
}
</script>

<style>

</style>