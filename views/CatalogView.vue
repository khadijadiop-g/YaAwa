<script setup>
const products = [
        {"id": "1","name": "Riz brisé parfumé","categoryId": "1","price": 17500,"salePrice": null,"stock": 18,"unit": "sac de 25 kg","origin": "Vallée du fleuve","description": "Riz brisé parfumé, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/riz.svg","active": true,"featured": true},
        {"id": "2","name": "Oignons de Potou","categoryId": "2","price": 750,"salePrice": 700,"stock": 4,"unit": "kg","origin": "Potou","description": "Oignons de Potou, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/oignons.svg","active": true,"featured": true},
        {"id": "3","name": "Mil local","categoryId": "1","price": 800,"salePrice": null,"stock": 24,"unit": "kg","origin": "Kaolack","description": "Mil local, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/mil.svg","active": true,"featured": false},
        {"id": "4","name": "Fonio précuit","categoryId": "1","price": 2200,"salePrice": 2000,"stock": 12,"unit": "sachet de 500 g","origin": "Kédougou","description": "Fonio précuit, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/fonio.svg","active": true,"featured": true},
        {"id": "5","name": "Maïs en grains","categoryId": "1","price": 650,"salePrice": null,"stock": 30,"unit": "kg","origin": "Tambacounda","description": "Maïs en grains, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/mais.svg","active": true,"featured": false},
        {"id": "6","name": "Tomates fraîches","categoryId": "2","price": 1000,"salePrice": null,"stock": 16,"unit": "kg","origin": "Niayes","description": "Tomates fraîches, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/tomates.svg","active": true,"featured": false},
        {"id": "7","name": "Carottes","categoryId": "2","price": 900,"salePrice": null,"stock": 7,"unit": "kg","origin": "Niayes","description": "Carottes, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/carottes.svg","active": true,"featured": false},
        {"id": "8","name": "Gombo frais","categoryId": "2","price": 1200,"salePrice": null,"stock": 0,"unit": "kg","origin": "Thiès","description": "Gombo frais, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/gombo.svg","active": true,"featured": true},
        {"id": "9","name": "Huile d’arachide","categoryId": "3","price": 4500,"salePrice": 4200,"stock": 20,"unit": "bouteille de 2 L","origin": "Kaolack","description": "Huile d’arachide, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/huile.svg","active": true,"featured": true},
        {"id": "10","name": "Sucre en poudre","categoryId": "3","price": 650,"salePrice": null,"stock": 32,"unit": "kg","origin": "Démonstration","description": "Sucre en poudre, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/sucre.svg","active": true,"featured": false},
        {"id": "11","name": "Sel iodé","categoryId": "3","price": 300,"salePrice": null,"stock": 45,"unit": "sachet de 500 g","origin": "Démonstration","description": "Sel iodé, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/sel.svg","active": true,"featured": false},
        {"id": "12","name": "Pâte d’arachide","categoryId": "3","price": 1500,"salePrice": null,"stock": 5,"unit": "pot de 500 g","origin": "Kaolack","description": "Pâte d’arachide, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/pate.svg","active": true,"featured": false},
        {"id": "13","name": "Thiof","categoryId": "4","price": 4500,"salePrice": null,"stock": 8,"unit": "kg","origin": "Joal","description": "Thiof, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/thiof.svg","active": true,"featured": true},
        {"id": "14","name": "Sardinelles","categoryId": "4","price": 1200,"salePrice": 1000,"stock": 25,"unit": "kg","origin": "Kayar","description": "Sardinelles, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/sardinelles.svg","active": true,"featured": false},
        {"id": "15","name": "Crevettes","categoryId": "4","price": 6500,"salePrice": null,"stock": 0,"unit": "kg","origin": "Casamance","description": "Crevettes, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/crevettes.svg","active": true,"featured": false},
        {"id": "16","name": "Poisson fumé","categoryId": "4","price": 3000,"salePrice": null,"stock": 6,"unit": "sachet de 500 g","origin": "Saint-Louis","description": "Poisson fumé, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/fume.svg","active": true,"featured": false},
        {"id": "17","name": "Bissap séché","categoryId": "5","price": 1200,"salePrice": null,"stock": 22,"unit": "sachet de 250 g","origin": "Kaolack","description": "Bissap séché, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/bissap.svg","active": true,"featured": true},
        {"id": "18","name": "Bouye en poudre","categoryId": "5","price": 1800,"salePrice": 1600,"stock": 13,"unit": "sachet de 500 g","origin": "Tambacounda","description": "Bouye en poudre, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/bouye.svg","active": true,"featured": true},
        {"id": "19","name": "Café Touba","categoryId": "5","price": 2500,"salePrice": null,"stock": 18,"unit": "sachet de 500 g","origin": "Démonstration","description": "Café Touba, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/cafe.svg","active": true,"featured": false},
        {"id": "20","name": "Madd en conserve","categoryId": "5","price": 2000,"salePrice": null,"stock": 9,"unit": "pot de 400 g","origin": "Casamance","description": "Madd en conserve, une sélection pour les repas et les moments de partage. Prix et provenance fictifs pour cet exercice.","image": "/images/madd.svg","active": false,"featured": false}
    ]
</script>

<template>
  <div class="container page-space">
    <!-- DEMANDE 01 — À PROGRAMMER : Lier le nom, le slogan, le logo et les images avec les données de la boutique. -->
    <section class="hero">
      <div class="hero-copy">
        <p class="eyebrow">
          <span> </span>
          Le marché, autrement.
        </p>
        <h1>
          Les saveurs du quartier.
          <br />
          <em> À portée de main. </em>
        </h1>
        <p>
          Du riz pour le ceebu jën, du bissap à partager… Retrouvez vos
          essentiels chez Awa, avec toute la teranga.
        </p>
        <a class="btn" href="boutique.html">
          Faire mon marché
          <svg
            aria-hidden="true"
            class="icon"
            fill="none"
            height="20"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="1.7"
            viewbox="0 0 24 24"
            width="20"
          >
            <path d="M5 12h14m-5-5 5 5-5 5"></path>
          </svg>
        </a>
        <div class="hero-proof">
          <span>
            <svg
              aria-hidden="true"
              class="icon"
              fill="none"
              height="15"
              stroke="currentColor"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="1.7"
              viewbox="0 0 24 24"
              width="15"
            >
              <path d="M20 3C8 2 2 8 5 15s17 4 15-12ZM5 20l10-10"></path>
            </svg>
            Une sélection de proximité
          </span>
          <span>
            <svg
              aria-hidden="true"
              class="icon"
              fill="none"
              height="15"
              stroke="currentColor"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="1.7"
              viewbox="0 0 24 24"
              width="15"
            >
              <path
                d="M20 10c0 6-8 12-8 12S4 16 4 10a8 8 0 1 1 16 0Zm-5 0a3 3 0 1 1-6 0 3 3 0 0 1 6 0"
              ></path>
            </svg>
            Castors, Dakar
          </span>
        </div>
      </div>
      <div aria-hidden="true" class="hero-art">
        <span class="hero-stamp">
          LE GOÛT
          <br />
          DU PARTAGE
        </span>
        <img
          alt=""
          class="hero-rice"
          height="280"
          src="/images/riz.svg"
          width="250"
        />
        <img
          alt=""
          class="hero-veg"
          height="205"
          src="/images/tomates.svg"
          width="205"
        />
        <div class="hero-note">
          Ñu bokk, ñu partage.
          <small> Un marché fait pour vous. </small>
        </div>
      </div>
    </section>
    <section class="categories-section">
      <div class="section-heading">
        <div>
          <p class="overline">À CHAQUE ENVIE, SON RAYON</p>
          <h2>De quoi se régaler</h2>
        </div>
      </div>
      <!-- DEMANDE 01 / 03 — À PROGRAMMER : Utiliser les catégories de l’API pour les images, la couleur CSS et le filtre. -->
      <div class="categories">
        <a
          class="category"
          href="categories/cereales.html"
          style="--category-color: #b98a38"
        >
          <img alt="" height="48" src="/images/cereales.svg" width="56" />
          <span> Céréales </span>
        </a>
        <a
          class="category"
          href="categories/legumes.html"
          style="--category-color: #468060"
        >
          <img alt="" height="48" src="/images/legumes.svg" width="56" />
          <span> Légumes </span>
        </a>
        <a
          class="category"
          href="categories/epicerie.html"
          style="--category-color: #b65c3a"
        >
          <img alt="" height="48" src="/images/epicerie.svg" width="56" />
          <span> Épicerie </span>
        </a>
        <a
          class="category"
          href="categories/poisson.html"
          style="--category-color: #477d87"
        >
          <img alt="" height="48" src="/images/poisson.svg" width="56" />
          <span> Poisson </span>
        </a>
        <a
          class="category"
          href="categories/saveurs-locales.html"
          style="--category-color: #956687"
        >
          <img alt="" height="48" src="/images/local.svg" width="56" />
          <span> Saveurs locales </span>
        </a>
      </div>
    </section>
    <section id="catalogue">
      <div class="section-heading">
        <div>
          <p class="overline">LA SÉLECTION D’AWA</p>
          <h2>Nos produits du moment</h2>
        </div>
        <a class="text-button" href="boutique.html">
          Tout le marché
          <svg
            aria-hidden="true"
            class="icon"
            fill="none"
            height="16"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="1.7"
            viewbox="0 0 24 24"
            width="16"
          >
            <path d="M5 12h14m-5-5 5 5-5 5"></path>
          </svg>
        </a>
      </div>
      <div class="product-grid">
        <!-- DEMANDE 02 / 05 — À PROGRAMMER : Transformer cette carte en ProductCard, déclarer les props et émettre add. Répéter les cartes depuis les données. -->
        <article
          class="product-card"
          data-component="ProductCard"
          data-product-id="1"
        v-for="product in products"
        :key="product.id">
          <div class="product-media">
            <a aria-label="Voir Riz brisé parfumé" href="produits/01-riz.html">
              <img
                alt="Riz brisé parfumé"
                height="240"
                loading="lazy"
                :src="product.image"
                width="360"
              />
            </a>
          </div>
          <div class="product-body">
            <p class="overline">{{ product.origin}}</p>
            <h3>
              <a href="produits/01-riz.html"> {{ product.name}} </a>
            </h3>
            <p class="muted small">{{ product.unit}} · {{ product.stock}} disponible(s)</p>
            <span class="stock">
              <span aria-hidden="true"> </span>
              Disponible
            </span>
            <div class="product-bottom">
              <div>
                <del v-if="product.salePrice"> {{ product.price}}  </del>
                <strong> {{product.salePrice ?  product.salePrice :product.price}} FCFA </strong>
              </div>
              <button
                :aria-label="`Ajouter ${product.name} au panier`"
                class="add-button"
                data-action="ajouter-panier"
                type="button"
              >
                <svg
                  aria-hidden="true"
                  class="icon"
                  fill="none"
                  height="20"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="1.7"
                  viewbox="0 0 24 24"
                  width="20"
                >
                  <path d="M12 5v14M5 12h14"></path>
                </svg>
              </button>
            </div>
          </div>
        </article>


      </div>
    </section>
    <section class="loyalty-banner mt">
      <div>
        <p class="overline">LES PETITS GESTES QUI COMPTENT</p>
        <h2>Un panier généreux, une attention en plus.</h2>
        <p>
          5 % de réduction dès 25 000 FCFA. Avec TERANGA10, profitez de 10 % :
          seule la meilleure remise est retenue.
        </p>
      </div>
      <span class="coupon">
        TERANGA10
        <small> Votre code de démonstration </small>
      </span>
    </section>
    <section class="promise-strip">
      <div>
        <svg
          aria-hidden="true"
          class="icon"
          fill="none"
          height="20"
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.7"
          viewbox="0 0 24 24"
          width="20"
        >
          <path d="M6 7h12l2 14H4L6 7Zm3 0V5a3 3 0 0 1 6 0v2"></path>
        </svg>
        <strong> Votre marché, à votre rythme </strong>
        <span> Préparez votre panier depuis chez vous. </span>
      </div>
      <div>
        <svg
          aria-hidden="true"
          class="icon"
          fill="none"
          height="20"
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.7"
          viewbox="0 0 24 24"
          width="20"
        >
          <path
            d="M20 10c0 6-8 12-8 12S4 16 4 10a8 8 0 1 1 16 0Zm-5 0a3 3 0 1 1-6 0 3 3 0 0 1 6 0"
          ></path>
        </svg>
        <strong> Au cœur du quartier </strong>
        <span> Retrait à Castors ou livraison à domicile. </span>
      </div>
      <div>
        <svg
          aria-hidden="true"
          class="icon"
          fill="none"
          height="20"
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.7"
          viewbox="0 0 24 24"
          width="20"
        >
          <path d="M20 3C8 2 2 8 5 15s17 4 15-12ZM5 20l10-10"></path>
        </svg>
        <strong> Le plaisir de partager </strong>
        <span> Des essentiels et des saveurs bien de chez nous. </span>
      </div>
    </section>
    <p class="template-note">
      <svg
        aria-hidden="true"
        class="icon"
        fill="none"
        height="16"
        stroke="currentColor"
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="1.7"
        viewbox="0 0 24 24"
        width="16"
      >
        <path d="m8 6-6 6 6 6m8-12 6 6-6 6M14 3l-4 18"></path>
      </svg>
      <span>
        Les données sont des exemples fixes. Les actions métier seront
        programmées par les étudiants.
      </span>
    </p>
  </div>
</template>



<style>
</style>