# ETL-completa
## Second project - ETL
El objetivo de este tercer proyecto era realizar el proceso completo de ETL(Extract,Transform and Load) con dos restricciones:obligatorio usar dos métodos de extracción de datos y obtener datos de tres fuentes.

Los métodos de extracción de datos elegidos han sido a través de una API y a través de Web Scrapping:
- Las APIs elegidas son la de Twitch y la de Youtube.
- El Web Scrapping ha sido realizado a través de Selenium.

Las fuentes elegidas han sido:
- Youtube.
- Twitch.
- Twitch tracker.

### Proceso:

Primero hemos elegido nuestro objeto de estudio. Por acotar la búsqueda hemos elegido los streamers/canales pertenecientes a la Kings League.Más adelante comentaremos cúal es el motivo para análisis posteriores.
Tras una primera exploración observamos que de los 13 canales, 11 retransmiten en Twitch y 2 en Youtube, de ahí nuestra elección de las APIs.
Empezamos la fase de extracción.

En el proceso de extracción de datos desde la API de Twitch, observamos que los datos son insuficientes ya que solo guarda los de los últimos dos meses( la Kings League empezo en Enero), lo cual nos lleva a realizar una extracción de datos desde la pagina Twitch tracker. Durante el proceso aprovechamos para que los datos extraídos ya esten transformados segun nuestras necesidades, juntando el siguiente paso (Transform).

Para el último paso tenemos que cargar los datos extraidos en una base de datos. La base de datos elegida es MySQL: primero contenemos los datos en dataframe a través de pandas(supervisando que esten transformados); segundo convertimos los dataframes en CSV; por último cargamos a través de MySQL WorkBench los CSV en una base de datos generando un total de 24 tablas, 2 para cada streamer de Twitch y 1 para cada streamer de Youtube.

### Próximamente:

El objetivo al crear esta base de datos es determinar que impacto ha tenido el evento de Kings League en cada canal. Para ello será necesario un estudio de los datos obtenidos para determinar el crecimiento del canal en el último año, una comparativa con streams/videos que no estén relacionados con la Kings League.

Un objetivo secundario será el de automatizar ciertos procesos de obtención de datos para extraer datos de futuros streams/videos.

