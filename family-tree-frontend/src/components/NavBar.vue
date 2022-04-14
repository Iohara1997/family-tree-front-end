<template>
    <div>
      <b-navbar toggleable="lg" type="dark" style="background: rgb(29,98,34); background: linear-gradient(90deg, rgba(29,98,34,1) 0%, rgba(145,201,150,1) 26%);">
        <div class="search__container">
          <input class="search__input" type="text" placeholder="Procurar Parente">
        </div>
        <b-navbar-brand class="title" style="margin-left:15%; color: #253726; font-family: 'Russo One', serif; font-size: 25px;">Árvore Genealógica - Família Souza</b-navbar-brand>
        <b-collapse id="" is-nav>
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-item-dropdown>
              <!-- Using 'button-content' slot -->
              <template #button-content>
                <img src="https://placekitten.com/g/30/30" class="d-inline-block align-top" alt="Usuário" style="border-radius: 20px; border: 2px solid brown; width: 40px; height: 40px;">
              </template>
              <b-dropdown-item href="#">Perfil</b-dropdown-item>
              <b-dropdown-item href="#">Sair</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Russo+One&display=swap');
@use postcss-color-function;
@use postcss-nested;
@import url('https://fonts.googleapis.com/css?family=Raleway:400,700,900');

/* Base styling */

.search {
    &__container {
      width: 240px;
      margin-left: 20px;
    }
    
    &__input {
        width: 100%;
        padding: 12px 24px;

        background-color: transparent;
        transition: transform 250ms ease-in-out;
        font-size: 14px;
        line-height: 18px;
        
        color: #B3DCC6;
        background-color: transparent;
 
      background-image: url("data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3Cpath d='M15.5 14h-.79l-.28-.27C15.41 12.59 16 11.11 16 9.5 16 5.91 13.09 3 9.5 3S3 5.91 3 9.5 5.91 16 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79l5 4.99L20.49 19l-4.99-5zm-6 0C7.01 14 5 11.99 5 9.5S7.01 5 9.5 5 14 7.01 14 9.5 11.99 14 9.5 14z'/%3E%3Cpath d='M0 0h24v24H0z' fill='none'/%3E%3C/svg%3E");
        background-repeat: no-repeat;
        background-size: 18px 18px;
        background-position: 95% center;
        border-radius: 50px;
        border: 2px solid #B3DCC6;
        transition: all 250ms ease-in-out;
        backface-visibility: hidden;
        transform-style: preserve-3d;
        
        &::placeholder {
            color: #B3DCC6;
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }
        
        &:hover,
        &:focus {
            padding: 12px 0;
            outline: 0;
            border: 1px solid transparent;
            border-bottom: 1px solid #253726;
            border-radius: 0;
            background-position: 100% center;
        }
    }
}

.title {
	font-family: 'Russo One', sans-serif;
	perspective: 1000px; 
}

.title span {
	cursor: pointer;
	display: inline-block;
	font-size: 100px;
	user-select: none;
	line-height: .8;
}

@keyframes slideInFromLeft {
  0% {
    opacity: 0;
    height: 20px;
     /* width and color */
    filter: blur(0);
  }
  100% {
    opacity: 1;
    height: 48px;
    filter: blur(0);
  }
}

.title {
  animation: 4s ease-out 0s 1 slideInFromLeft;
}

</style>

<script>
export default{
  name:'NavBar'
}
</script>