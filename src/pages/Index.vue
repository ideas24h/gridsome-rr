<template>
  <Layout>
    <Pager :info="$page.posts.pageInfo" />
      <div class="px-4 py-4 rounded shadow-lg">
   ¿Te has hartado de pelear contra el polvo, pelusas y pelos y no tienes tiempo ni ganas de barrer todos los días?

Estás de suerte. Los robots aspiradora llevan ya más de una década en el mercado y en ese tiempo han evolucionado mucho.

Los primeros no eran el sistema más efectivo del mundo. Limpiaban, pero a veces se quedaban dando golpes contra un rincón o girando sin sentido en una esquina de la casa.

Hoy puedes encontrar robots inteligentes que identifican el nivel de suciedad del suelo y escanean la casa para que no quede ni un zócalo sin limpiar. Los hay que aspiran cuando tú no estás, que evitan las escaleras e identifican las zonas en las que no quieres que entren, o incluso que pasan una mopa húmeda para que no tengas que fregar tan a menudo.

También los precios se han democratizado, y lo que antes era un electrodoméstico solo para gente con gran poder adquisitivo, hoy empieza a ser de uso común con precios que pueden bajar de los cien euros. Aunque existen otros tipos de aspiradoras sin cable, éstos son los únicos automáticos que nos ahorran un buen esfuerzo.

En esta guía encontrarás los 10 mejores robots aspirador en calidad-precio según nuestros analistas, desde modelos básicos a bajo coste hasta los que cuentan con avanzados sistema de navegación.

PD: al final también encontrarás una práctica tabla comparativa y una completa guía de compra para que no te quede ninguna duda al hacer tu elección.
      </div>
    <div class="max-w rounded overflow-hidden shadow-lg mt-8"  v-for="post in $page.posts.edges" :key="post.id">
      <g-link :to="post.node.path">
        <img v-if="post.node.coverImage" :src="post.node.coverImage" class="w-full h-48 object-cover" alt="Cover" />
        <div class="px-6 py-4">
          <div class="font-bold text-xl mb-2">{{post.node.title}}</div>
          <p class="text-gray-700 text-base">
            {{post.node.excerpt}}
          </p>
          <div class="mt-2">
            Posted {{ post.node.date }}
            <template v-if="post.node.timeToRead">
              <strong>{{ post.node.timeToRead }} min read.</strong>  
            </template>
          </div>
        </div>
      </g-link>
      <div class="px-6 py-4">
        <div class="post-tags">
          <g-link v-for="tag in post.node.tags" :key="tag.id" :to="tag.path">
            <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#{{ tag.title }}</span>
          </g-link>
        </div>
      </div>
    </div>
  </Layout>
</template>

<page-query>
  query Home ($page: Int) {
    posts: allPost (perPage: 10, page: $page) @paginate {
      pageInfo {
        totalPages
        currentPage
      }
      edges {
        node {
          _id
          date (format: "MMM Do YYYY")
          title
          path
          excerpt
          tags {
            id
            title
            path
          }
          coverImage (height: 320, quality: 100)
          timeToRead
        }
      }
    }
  }
</page-query>

<script>
import { Pager } from 'gridsome'
export default {
  components: {
    Pager
  }
}
</script>

<style>
.post__link {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0.0;
  overflow: hidden;
  text-indent: -9999px;
  z-index: 0;
}
</style>
