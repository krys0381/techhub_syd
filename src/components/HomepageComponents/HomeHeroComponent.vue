<template>
  <div class="container-fluid hero-container  d-flex flex-column justify-content-center align-items-center">
    <div class="container ">
      <div class="row ">
          <div class="content-container d-flex flex-column justify-content-center align-items-center mb-5">
              <h1 class="hero-title" data-aos="fade-down-right">Because starting up a tech business should be possible.</h1>
              <h3 class="hero-subtitle col-lg-8 my-5" data-aos="fade-up-left">
                  We are a community that connects, inspires and helps start-ups, students and investors build their tech business through networking events.
              </h3>
              <button type="button" class="btn btn-primary btn-lg 2 col-lg-4 col-md-12 col-sm-12 col-12" @click="$router.push('events')" data-aos="flip-up" data-aos-delay="800">JOIN OUR EVENT NOW!</button>
          </div>
      </div>
    </div>
     <div class="hero-image-container d-none d-xl-flex"></div>
  </div>  
</template>

<script>
import AOS from 'aos';
import 'aos/dist/aos.css';
AOS.init({
    delay: 300,
    duration: 1000
});

export default {
  
}
</script>

<style lang="scss" scoped>
@import "../../assets/shared.scss";
@include light-heading1;
@include heading3;
@include heading6;

.hero-container{
  width: 100vw;
  min-height: 90vh;
  background: transparent linear-gradient(180deg, #7E42BE 0%, #10041C 100%) ;
  position: relative;

}

.hero-image-container{
  background-image: url('../../assets/img/hero_transparent-6-01.svg');
  background-size: cover;
  background-position: center;
  width: 100vw;
  min-height: 90vh;
  position: absolute;
 
}

.content-container{
  padding-bottom: 150px;
}

.btn-primary{
 padding: 15px 30px;
 background-color: #E69B5A;
 border-radius: 0;
 border-color: #E69B5A;
 transition: 0.3s;
    &:hover{
        background-color: $accentdarkcolor;
      }
}

.hero-title,
.hero-subtitle,
.btn-primary{
z-index: 1;
}

// Media queries

@media (max-width: 767.98px) { 
  .content-container{
    padding-bottom: 0px;
  }
}

@media (max-width: 991.98px) { 
  .content-container{
    padding-bottom: 0px;
  }
}

@media (max-width: 1199.98px) {
  .content-container{
    padding-bottom: 0px;
  }
}

</style>