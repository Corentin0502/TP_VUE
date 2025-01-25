<script>
import axios from "axios";

export default {
  data() {
    return {
      superheros: [], // Liste des superhéros
    };
  },
  mounted() {
    axios
      .get("https://cdn.jsdelivr.net/gh/akabab/superhero-api@0.3.0/api/all.json")
      .then((response) => {
        this.superheros = response.data; // Mise à jour des superhéros
      })
      .catch((error) => {
        console.error("Erreur lors de la récupération des données :", error);
      });
  },
};
</script>
