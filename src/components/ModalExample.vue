<template>
  <section class="section">
    <div class="container">
      <button class="button is-primary" @click="isActive=true">Kitty</button>
      <button class="button is-warning" @click="isActive2=true">bacon!</button>
      <button class="button is-link" @click="isActive3=true">Text card</button>

      <img-modal 
      v-if="isActive"
      @close="isActive=false"
      src="https://placekitten.com/400/960">
      </img-modal>

      <img-modal 
      v-if="isActive2"
      @close="isActive2=false"
      src="https://baconmockup.com/600/600">
      </img-modal>
      
      <modal 
      v-if="isActive3"
      @close="isActive3=false">
        <div class="card">
          <div class="card-content">
            <div class="content">
              Lolly texty Saires
            </div>
          </div>
        </div>
      </modal>
    </div>
  </section>
</template>

<script>
import ImgModal from './ImgModal.vue'
import Modal from './Modal.vue'
export default {
  components: { Modal, ImgModal },
  data(){
    return {
      isActive: false,
      isActive2: false,
      isActive3: false
    }
  }
}
</script>

<style>
</style>