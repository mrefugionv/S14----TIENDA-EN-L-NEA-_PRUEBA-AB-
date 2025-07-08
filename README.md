# S14----TIENDA-EN-LINEA-_PRUEBA-AB
Probar cambios relacionados con la introducción de un sistema de recomendaciones mejorado.

## Descripción

* Nombre de la prueba: recommender_system_test
* Grupos: А (control), B (nuevo embudo de pago)
* Fecha de lanzamiento: 2020-12-07
* Fecha en la que dejaron de aceptar nuevos usuarios: 2020-12-21
* Fecha de finalización: 2021-01-01
* Audiencia: 15% de los nuevos usuarios de la región de la UE
* Propósito de la prueba: probar cambios relacionados con la introducción de un sistema de recomendaciones mejorado.
* Resultado esperado: dentro de los 14 días posteriores a la inscripción, los usuarios mostrarán una mejor conversión en vistas de la página del producto (el `evento product_page`), instancias de agregar artículos al carrito de compras (`product_cart`) y compras (`purchase`). En cada etapa del embudo `product_page` → `product_cart` → `purchase`, habrá al menos un 10% de aumento.
* Número previsto de participantes de la prueba: 6 000
  
## Herramientas utilizadas
![Python](https://img.shields.io/badge/:Python-024A86?style=for-the-badge&logo=python&logoColor=white&labelColor=101010)</br>
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/seaborn-%233F4F75.svg?style=for-the-badge&logo=seaborn&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-%230C55A5.svg?style=for-the-badge&logo=scipy&logoColor=%white)
![Datetime](https://img.shields.io/badge/datetime-%233F4F75.svg?style=for-the-badge&logo=datetime&logoColor=white)

![Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&color=525252)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)

## Conclusiones
De acuerdo a lo que se pudo revisar en el Análisis exploratorio de los datos y los resultados estadísticos de la prueba A/B se puede concluir:
* Los resultados de la prueba pudieron verse afectados por la alsa en las ventas de la temporada de Navidad.
* El número de participantes previsto en la prueba era de 6000, mientras que solo se registraron 3675.
* No se obtuvo el resultado deseado, de un aumento del 10% en cada etapa del embudo : `product_page` → `product_cart` → `purchase`
* Sin embargo, sí hay una aumento en las proporciones de conversión en cada etapa del grupo B con respecto al A:
  * `product_page` → `product_cart`, grupo A cae 31.1% mientras que B 22.55%
  * `product_cart` → `purchase`, grupo A cae 5.33% mientras B 3.75%

Aunque para validar esta última observación se debe tomar en cuenta que en grupo A hay 2545 registradas , y en B hay únicamente 655. Sin embargo al hacer los embudos, tomando en cuenta el orden secuencial de los pasos, para A quedan 0 y para B 1.

## Profundización técnica
* Importación de librerías
* Importación y exploración de datos 
* Manejo de nombres de columnas, tipos de datos, valores auscentes y duplicados.
* Asegurarse que no se repiten usuarios en ambos grupos A y B
* Asegurarse que número de usuarios y eventos se reparte equitativamente entre las muestras
* Comparación entre los embudos de conversión entre los grupos
* Parámetros acumulativos - Cantidad de eventos por día
* Observar si la prueba pudo haber sido afectada por algún otro factor, como las ventas de temporada.
* Prueba estadística de una cola (Z Test), comparando el grupo B con el 10% de aumento esperado a la tasa de conversión.
