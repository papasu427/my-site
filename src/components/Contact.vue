<template>
  <div class="wrapper position-re">
    <section class="wrapper-left">
      <div class="top-title">
        <div class="top-name">CONTACT</div>
        <div class="top-subscription">
          お問い合わせやご依頼はお気軽に、
          <br />ご連絡ください。
        </div>
      </div>
    </section>

    <section class="wrapper-right">
      <div class="textbox">
        <form action="/my-handling-form-page" method="post">
          <ul>
            <li class="mb-8">
              <label for="name">Company Name</label>
              <input type="text" id="name" name="user_name" />
            </li>
            <li class="mb-8">
              <label for="name">
                You Name
                <span style="font-size: 8px;">※</span>
              </label>
              <input type="text" id="name" name="user_name" required />
            </li>
            <li class="mb-8">
              <label for="mail">
                Address
                <span style="font-size: 8px;">※</span>
              </label>
              <input type="email" id="mail" name="user_email" required />
            </li>
            <li class="mb-8">
              <label for="mail">E-mail</label>
              <input type="email" id="mail" name="user_email" />
            </li>
            <li class="mb-8">
              <label for="msg" class="msg-filed">
                Message
                <span style="font-size: 8px;">※</span>
              </label>
              <textarea id="msg" name="user_message" required></textarea>
            </li>
            <li>
              <button type="submit">send</button>
            </li>
          </ul>
        </form>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "conntact",
  props: {
    msg: String,
    num: Number
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.textbox {
  width: 70%;
  position: absolute;
  top: 50%;
  left: 44%;
  transform: translateY(-50%) translateX(-50%);
  -webkit-transform: translateY(-50%) translateX(-50%);
  text-align: left;
  font-weight: bold;
}

/*  InputCSS  */

ul {
  list-style: none;
  padding: 0 !important;
  margin: 0;
}

form li + li {
  margin-top: 1em;
}

label {
  /* すべてのラベルを同じサイズにして、きちんと揃える */
  display: inline-block;
  width: 40%;
  border-bottom: 1px solid #c4c4c4;
  font-size: 12px;
  padding-bottom: 10px;
}

input {
  /* すべてのテキストフィールドのフォント設定を一致させる
     デフォルトで、textarea は等幅フォントが設定されている */
  font: 0.8em sans-serif;

  /* すべてのテキストフィールドを同じサイズにする */
  box-sizing: border-box;

  /* テキストフィールドのボーダーの外見を同一にする */
  border-bottom: 1px solid #424242;

  width: 60%;

  padding-bottom: 10px;
}

textarea {
  /* すべてのテキストフィールドのフォント設定を一致させる
     デフォルトで、textarea は等幅フォントが設定されている */
  font: 0.8em sans-serif;

  /* すべてのテキストフィールドを同じサイズにする */
  box-sizing: border-box;

  /* テキストフィールドのボーダーの外見を同一にする */
  border: 1px solid #424242;

  padding-bottom: 10px;

  /* 複数行のテキストフィールドをラベルにきちんと揃える */
  vertical-align: top;

  /* テキスト入力に十分な領域を与える */
  height: 10em;
  padding: 10px;
  width: 100%;
}

input:focus {
  outline: none;
}

textarea:focus {
  outline: none;
}

input:focus,
textarea:focus {
  /* アクティブな要素を少し強調する */
  border-color: #000;
}

.msg-filed {
  /* すべてのラベルを同じサイズにして、きちんと揃える */
  display: block !important;
  font-size: 12px;
  padding-bottom: 10px;
  border: none;
}

button {
  display: block;
  font-size: 14px;
  margin: 0 auto;
  border: 1px solid;
  padding: 4px 50px;
  transition: 0.4s;
}
button:hover {
  background: #424242;
  color: white;
}
@media (max-height: 560px) {
  .top-name {
    font-size: 5vh;
  }
  .top-subscription {
    font-size: 3vh;
  }
  .textbox {
    font-size: 5vh;
  }
}
@media (max-height: 330px) {
  .top-name {
    font-size: 7vh;
  }
  .top-subscription {
    font-size: 4vh;
  }
}
</style>
