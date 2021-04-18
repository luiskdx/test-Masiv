# Masiv Test

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Preguntas y Respuestas

**P: ¿Cómo construyó la solución de la prueba?**

R: Usé Vue Cli, con una instalación lo más limpia posible para aprovechar los modulos necesarios. De forma idependiente instalé el componente vue-star-rating. Por la parte de estilos usé SCSS para acomodar pequeños detalles globales de la prueba.


**b. ¿Cuáles fueron los principales problemas con los que se encontró?**

R: El principal problema fue tener acceso al APi de xkcd, ya cuenta con la restricción de la politica CORS. Otro punto fue buscar una opción para el manejo de la calificación por estrellas.


**c. ¿Cómo solucionó los problemas encontrados?**

R: El problema de CORS lo solucioné usando un servicio llamado allorigins.win que me permitia tener acceso al API de xkcd en mi local.
Para la calificación de estrellas usé el componente vue-star-rating, donde tuve que aprender a darle el uso adecuado, y tomando la opción de guardar la calificación dentro del localStorage.