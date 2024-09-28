<template>
    <div class="header">
      <div class="logo-container">
        <div class="logo-wrapper">
          <img src="@/assets/bg.png" alt="bg" class="bg-image" />
          <img src="@/assets/logo.png" alt="Laurus Invest Logo" class="logo-image" />
        </div>
        <div class="info">
          <div class="info-item">
            <img src="@/assets/earth.png" alt="earth"/>
            <span>Astana, Kazakhstan</span>
          </div>
          <div class="info-item">
            <img src="@/assets/location.png" alt="location"/>
            <span>Turan avenue, 30A</span>
          </div>
          <div class="info-item">
            <img src="@/assets/mail.png" alt="mail"/>
            <span>info@laurusinvest.kz</span>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

export default {
  name: 'Header',
  mounted() {
    // Анимация для логотипа и фонового изображения
    gsap.from('.logo-wrapper', {
      opacity: 0,
      y: -50,
      duration: 1.5,
      ease: 'power3.out',
      scrollTrigger: {
        trigger: '.logo-wrapper',
        start: 'top 80%',
        end: 'bottom 20%',
        toggleActions: 'play none none none',
      }
    });

    // Параллакс-эффект для фонового изображения
    gsap.to('.bg-image', {
      yPercent: 20,
      scrollTrigger: {
        trigger: '.logo-container',
        scrub: true,
      }
    });

    // Плавное появление блоков информации
    gsap.from('.info-item', {
      opacity: 0,
      y: 30,
      duration: 1,
      ease: 'power3.out',
      stagger: 0.3, // задержка между элементами
      scrollTrigger: {
        trigger: '.info',
        start: 'top 90%',
        toggleActions: 'play none none none',
      }
    });
  }
};
  </script>
  
  <style scoped lang="scss">
@keyframes fade-in-up {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fade-in-down {
  0% {
    opacity: 0;
    transform: translateY(-20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

  .header {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 90vh; 
    padding: 20px;
    background-color: #003d33;
  }
  
  .logo-container {
    display: flex;
    flex-direction: column; 
    justify-content: center;
    align-items: center;
    position: relative; 
    width: 1300px; 
    height: 500px;
    margin-bottom: 30px;
    border: 1px solid #ffffff;
    padding: 40px;
    animation: fade-in 2.5s cubic-bezier(0.25, 0.1, 0.25, 1.0);
  }
  
  .logo-wrapper {
    position: relative; 
    display: flex;
    justify-content: center;
    align-items: center;
    animation: fade-in 1s ease-out; 
  }
  
  .logo-image {
    position: relative; 
    z-index: 2;
    max-width: 150px; 
  }
  
  .bg-image {
    position: absolute; 
    bottom:-120px; 
    left: 50%; 
    transform: translate(-50%, -50%); 
    z-index: 1; 
    max-width: 250px; 
  }
  
  .info {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 30px;
    font-size: 16px;
    margin-top: 20px;
    color: white;
    flex-wrap: wrap; 
    animation: fade-in 1.5s ease-out; 
  }
  
  .info-item {
    display: flex;
    align-items: center;
    gap: 10px;
    position: relative; 
    top: 150px;
    animation: fade-in 1.5s ease-out; 
    
    &:not(:last-child)::after {
      content: "";
      position: absolute;
      right: -15px; 
      top: 0;
      bottom: 0;
      width: 1px;
      height: 24px; 
      background-color: #ffffff;
      margin: auto; 
    }
  }
  
  @media (max-width: 768px) {
    .header {
      padding: 10px;
    }
  
    .logo-container {
      width: 80%; 
      height: 550px;
      padding: 20px;
    }
  
    .logo-image {
      max-width: 100px; 
    }
  
    .bg-image {
      max-width: 200px; 
    }
  
    .info {
      flex-direction: column;
      position: relative;
      bottom: -20px;
      gap: 15px; 
      margin-top: 10px;
      animation: fade-in 1.5s ease-out; 
    }
  
    .info-item {
      &:not(:last-child)::after {
        display: none; 
      }
    }
  }
  </style>
  