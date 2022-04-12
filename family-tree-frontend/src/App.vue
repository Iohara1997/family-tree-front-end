<template>
  <div id="app">
    <header>
      <NavBar />
    </header>
    <body>
      <VueFamilyTree
        :tree="tree"
        @card-click="cardClick"
      >
        <template
        
          v-slot:card="{item}"
        >
          <div class="custom-card">
            <div
              :style="{backgroundImage: item.image ? `url(${item.image})` :  null}"
              class="custom-card__image"
            />
            <div class="custom-card__info">
              <div class="custom-card__name">
                <p :style="{marginBotton: 0}"> {{ item.name }} </p>
              </div>
              <div
                v-show="item.age"
                class="custom-card__age"
              >
                Age: {{ item.age }}
              </div>
            </div>
          </div>
        </template>
      </VueFamilyTree>
    </body>
    <footer>
      <FooterCustom/>
    </footer>
  </div>
</template>

<script>
import VueFamilyTree from './components/VueFamilyTree';
import NavBar from './components/NavBar';
import FooterCustom from './components/FooterCustom';

export default {
  name: 'App',
  components: {
    VueFamilyTree,
    NavBar,
    FooterCustom
  },
  data () {
    return {
      customCard: false,
      tree: [{
        firstPerson: {
          name: 'John Walker',
          image: 'https://picsum.photos/300/300?random=1'
        },
        secondPerson: {
          name: 'Jannet Grem',
          image: 'https://picsum.photos/300/300?random=2',
          age: 23
        },
        children: [{
          firstPerson: {
            name: 'Katia'
          },
          secondPerson: {
            name: 'Oleg'
          },
          children: [{
            firstPerson: {
              name: 'Gleb'
            },
            secondPerson: {
              name: 'Viktoriya'
            },
            children: [{
              firstPerson: {
                name: 'Rim'
              },
              secondPerson: {
                name: 'Natasha'
              }
            },
            {
              firstPerson: {
                name: 'Leonid'
              }
            }]
          },
          {
            firstPerson: {
              name: 'Olga'
            },
            secondPerson: {
              name: 'Nikita'
            }
          }]
        },
        {
          firstPerson: {
            name: 'Vitia'
          },
          secondPerson: {
            name: 'Dasha'
          },
          children: [{
            firstPerson: {
              name: 'Michael'
            },
            secondPerson: {
              name: 'Maria'
            }
          }]
        },
        {
          firstPerson: {
            name: 'Antonio Wild',
            image: 'https://picsum.photos/300/300?random=3'
          },
          secondPerson: {
            name: 'Olivia Olson'
          },
          children: [{
            firstPerson: {
              name: 'Kristina Wild'
            }
          },
          {
            firstPerson: {
              name: 'Alexey Wild'
            }
          },
          {
            firstPerson: {
              name: 'Viktor Wild'
            }
          }]
        }]
      }]
    }
  },
  methods: {
    cardClick (item) {
      console.log(item);
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100%;
}

html {
  height: 100%;
  width: 100%;
}

.navbar { 
  align-items: center;
}

.navbar-expand-lg .navbar-collapse {
  display: flex !important;
  flex-basis: auto;
  justify-content: flex-end;
  margin-right: 3rem;
}

.dropdown-menu {
  min-width: 6rem !important;
}

body {
  margin-top: 0px;
  height: 100%;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* Works on Firefox */
* {
  scrollbar-width: thin;
  scrollbar-color: #91C996 #643C12;
}

/* Works on Chrome, Edge, and Safari */
*::-webkit-scrollbar {
  width: 12px;
}

*::-webkit-scrollbar-track {
  background: #643C12;
}

*::-webkit-scrollbar-thumb {
  background-color: #91C996;
  border-radius: 20px;
  border: 3px solid #643C12;
}
.custom-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  height: 150px;
  width: 100px;
  padding: 16px;
  border: 1px solid #ddd;
  border-radius: 10px;
  box-sizing: border-box;
  background-color: #fff;
  cursor: pointer;
  box-shadow: 0 0 6px 2px rgba(#000, 0);
  transition: box-shadow .2s ease;
  &:hover {
    box-shadow: 0 0 6px 2px rgba(#000, .1);
  }
  &__image {
    flex: 0 0 auto;
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background-color: #dedede;
    background-size: cover;
    background-position: 50%;
  }
  &__info {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  &__name {
    font-weight: 500;
    flex: 1; /* This make p take the full width of column*/
    text-align: center;
  }
  &__age {
    font-size: 12px;
  }
}

p {
  margin-bottom: 0px !important;
}

</style>