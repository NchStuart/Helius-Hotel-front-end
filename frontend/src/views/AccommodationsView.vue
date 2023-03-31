<template>
  <section id="heading1">
    <TitleInitialDescription>
      <h1>Nossas Acomodações</h1>
      <hr />
      <p>
        As acomodações do Helius Hotel foram projetadas para oferecer todo o
        conforto e tranqüilidade que você merece. Todos os nossos quartos ficam
        próximos a sala de jogos, ao restaurante, às piscinas e possuem uma
        vista magnífica para as piscinas!
      </p>
    </TitleInitialDescription>
    <CarouselOne :images="images"/>
    <p>
      Seja qual for o seu objetivo: comemorações em família, apenas um momento
      para descansar, até mesmo uma confraternização com a empresa ou encontro
      de amigos, o Hotel Helius tem a acomodação certa para você. Aproveite a
      oportunidade e faça agora mesmo sua reserva.
    </p>
  </section>
</template>

<script>
import TitleInitialDescription from "../components/TitleInitialDescription.vue";
import CarouselOne from "../components/carousel/CarouselOne.vue";

export default {
  name: "AccommodationsView",
  components: {
    TitleInitialDescription,
    CarouselOne,
  },
  data() {
    return {
      images: [
        { src: require("../assets/images/quarto_simples.jpg") },
        { src: require("../assets/images/quarto_premium.jpg") },
        { src: require("../assets/images/bangalo04.jpg") },
      ],
      accommodations: ["Simples", "Premium", "Bangalô"],
    };
  },
  methods: {
    skipPage() {
      if (this.$store.state.login == false) {
        alert("Você precisa estar logado para fazer uma reserva.");
      } else {
        this.$router.push("/reservas");
      }
    },
    scrollPage(type) {
      if (type == 1) {
        window.scrollTo({
          top: 1000,
          behavior: "smooth",
        });
      }
      if (type == 2) {
        window.scrollTo({
          top: 1800,
          behavior: "smooth",
        });
      }
      if (type == 3) {
        window.scrollTo({
          top: 2400,
          behavior: "smooth",
        });
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.accommodations-bedrooms {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 95%;
}

section {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
}

h1 {
  font-size: 40px;
  margin-bottom: 30px;
  font-weight: normal;
  text-align: center;
}

p {
  font-size: 17px;
  font-weight: bold;
  min-width: 250px;
  margin-bottom: 50px;
  text-align: center;
}

hr {
  width: 100%;
  margin-bottom: 30px;
}
</style>