<script>
export default {
  name: 'FlashcardDeck',
  data() {
    return {
      cartoes: [
        { pergunta: 'Qual a capital da França?', resposta: 'Paris' },
        { pergunta: 'Qual o maior país do mundo?', resposta: 'Russia' },
        { pergunta: 'Qual a moeda do japão??', resposta: 'Yen' }
        // Add more flashcards as needed
      ],
      IndexDoCard: 0,
      mostrarPergunta: true
    };
  },
  methods: {
    nextCard() {
      if (this.IndexDoCard < this.cartoes.length - 1) {
        this.IndexDoCard++;
      } else {
        this.IndexDoCard = 0;
      }
      this.mostrarPergunta = true;
    },
    prevCard() {
      if (this.IndexDoCard > 0) {
        this.IndexDoCard--;
      } else {
        this.IndexDoCard = this.cartoes.length - 1;
      }
      this.mostrarPergunta = true;
    },
    toggleCardSide() {
      this.mostrarPergunta = !this.mostrarPergunta;
    }
  }
};
</script>

<template>
  <div class="deckDePerguntas">
    <div class="cards">
      <div v-if="mostrarPergunta" class="perguntaDoCard">{{ cartoes[IndexDoCard].pergunta }}</div>
      <div v-else class="respostaDoCard">{{ cartoes[IndexDoCard].resposta }}</div>
    </div>
    <div class="button-group">
      <button @click="prevCard">Anterior</button>
      <button @click="toggleCardSide">{{ mostrarPergunta ? 'Resposta' : 'Pergunta' }}</button>
      <button @click="nextCard">Proxima</button>
    </div>
  </div>
</template>

<style scoped>

.deckDePerguntas {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 300px;
}

.cards {
  width: 300px;
  height: 200px;
  background-color: rgba(242, 242, 242, 0.41);
  border-radius: 10px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: Helvetica, Arial, sans-serif;
  font-size: 24px;
  font-weight: bold;
  color: #2c3e50;
  padding: 20px;
  margin-bottom: 20px;
}

.perguntaDoCard {
  color: #2c3e50;
}

.respostaDoCard {
  color: #e74c3c;
}

.button-group {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

.button-group button {
  background-color: #3498db;
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  margin: 0 5px;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
}

.button-group button:hover {
  background-color: #2980b9;
}
body {
  font-family: Helvetica, Arial, sans-serif;
}
</style>
