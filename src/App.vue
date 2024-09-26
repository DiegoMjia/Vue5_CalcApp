<template>
  <div>
    <div class="home">
      <div class="ContainerCalc">
        <div class="ContainerAll">
          <ScreenCalc class="ScreenCalc" :NumberValue="ValueShow"></ScreenCalc>
          <hr>
          <div class="ContainerOptions">
            <ButtonsCalc class="Buttons" @button-click="ShowNumber"></ButtonsCalc>
            <ButtonsOperations @sign-operation="ShowNumber"></ButtonsOperations>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ScreenCalc from './components/ScreenCalc.vue';
import ButtonsCalc from './components/ButtonsCalc.vue';
import ButtonsOperations from './components/ButtonsOperations.vue';

export default {
  name: 'App',


  data() {
    return {
      Numbers: [],
      ValueShow: '',
      Ce: false,
      Operation: '',
    }
  },


  methods: {
    ShowNumber(value) {
      if (value == 'CE' || value == 'C') {
        this.Numbers = [];
        this.Ce = true;
      }

      if (this.Ce) {
        this.ValueShow = '';
        this.Ce = false;
      } else {
        this.ValueShow += value.toString();
        if (value != '=' && value != 'CE' && value != 'C') {
          this.Numbers.push(value);
        }
      }

      switch (value) {
        case '=':
          {
            try {
              const expression = this.Numbers.join('');
              this.ValueShow = new Function('return ' + expression)().toString();
              this.Numbers = [];
              this.Numbers[0] = this.ValueShow;
            } catch (error) {
              alert("FATAL ERROR SINTAXIS");
              this.Numbers = [];
              this.ValueShow = 0;
            }
          }
          break;

        default:
          break;
      }

    },
  },

  components: {
    ScreenCalc,
    ButtonsCalc,
    ButtonsOperations,
  }
}
</script>

<style scoped>
.home {
  width: 100%;
  margin-top: 100px;
  display: flex;
  justify-content: center;
  align-content: center;
}

.ContainerCalc {
  border: 2px solid #000;
  margin: 20px;
  padding: 20px;
  border-radius: 15px;
}


.ContainerOptions {
  display: flex;
  gap: 10px;
}
</style>
