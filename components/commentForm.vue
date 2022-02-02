<template>
  <div>
    <h3 class="form_title">Введите ваш комментарий:</h3>
    <div class="comment_form">
      <div class="form-group">
        <div>
          <img src="../assets/user.png" alt="user" class="user_photo_form">
        </div>
      </div>
      <div class="form-group">
        <input type="text" v-model="name" placeholder="Введите ваше имя" class="form" >
        <textarea class="form" v-model="comment" name="message" placeholder="Введите ваш комментарий" style="width:600px; height:100px;"></textarea>
      </div>
    </div>
    <button type="submit" class="btn_commentForm btn" v-on:click="addComment" >Добавить комментарий</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name:'',
      comment:'',
    };
  },
  methods: {
    addComment(e) {
      e.preventDefault();
      if (this.name !== '' && this.comment !== '') {
        this.$emit('addComment', { name: this.name, comment: this.comment });
        this.name = '';
        this.comment = '';
      } else {
        this.error = true;
        setTimeout(() => {
          this.error = false;
        }, 3000);
      }
    },
  }
}
</script>

<style>

.comment_form {
  margin-top: 40px;
  display: flex;
  justify-content: start;
  align-items: start;
  flex-direction: row;
}
.form{
  border: 1px solid #f6b6ff;
  border-radius: 10px;
  width: 600px;
  margin-bottom: 5px;
  padding: 15px 20px 15px 20px;
}

.user_photo_form {
  height: 60px;
}

.form_title {
  margin:40px 0 15px;
  font-size: 26px;
}
.form-group {
  display: flex;
  flex-direction: column;
  margin-right: 30px;
}

label {
  margin-bottom: 20px;
}

.btn_commentForm {
  position: absolute;
  margin: 15px;
  left: 410px;
  border: none;
  color: white;
  padding: 15px 45px;
  margin-bottom: 100px;
}
</style>
