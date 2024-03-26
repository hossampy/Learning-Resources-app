<template>
  <base-dialog v-if="inputisinvalid" title="input is invalid" @close="closedialog">
    <template v-slot:default>
      <p>input is invalid </p>
      <p>please chavk your info and add a correct input </p>

    </template>
    <template v-slot:action>
      <base-button @click="closedialog">okey</base-button>
    </template>

  </base-dialog>
  <base-card>

    <form>
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" ref="titleInput" />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea id="description" name="description" rows="3" ref="descInput"></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" ref="linkInput" />
      </div>
      <div>
        <base-button type="submit" @click.prevent="SubmitData">Add Resource</base-button>
      </div>
    </form>
  </base-card>
</template>
<script>
import BaseButton from '../UI/BaseButton.vue';
import BaseDialog from '../UI/BaseDialog.vue';
export default {
  components: { BaseDialog, BaseButton },
  data(){
    return{
      inputisinvalid:false,
    }
  },

  inject: [
    'Addresource'
  ],
  methods:{
    SubmitData(){
      const enterdtitle = this.$refs.titleInput.value;
      const enterdDescription = this.$refs.descInput.value;
      const enterdlink = this.$refs.linkInput.value;
      if (enterdtitle.trim() === '' 
      || enterdDescription.trim() === ''
       || enterdlink.trim()==='')
      {
        this.inputisinvalid =true;
        return
      }

     this.Addresource(enterdtitle, enterdDescription, enterdlink)
    },
    closedialog(){
      this.inputisinvalid=false;
    }
  }
}
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>