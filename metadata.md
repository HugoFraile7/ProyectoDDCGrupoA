ENTREGA 1: RECOGIDA DE DATOS COMPLEJOS - GRUPO A

-Fuente de datos: El dataset original ha sido recopilado de la página
Kaggle
(https://www.kaggle.com/datasets/michaelmatta0/amazon-cell-phones-cleaned-scraped-data),
la otra parte de los datos, se ha obtenido de la propia página de Amazon
de cada
producto(https://www.amazon.com/Apple-iPhone-XR-Fully-Unlocked/dp/B07P6Y7954/ref=sr_1_12?dib=eyJ2IjoiMSJ9._eY91ZyjAdQKEzzR6DNcMdFRe0yHQ0CEnmbO0QizIqRt5nq6hCQqYJObh553vsAKozdGdTb-QY2LLU680L8eittx2AGozuBKoU8BRNw3Bvk7V7vkKNxQUT9sAV5DLP4uzJbYBpYBln7jwHEQSnKdcFbZ7Uk9SlmxevYlus6yXDiw7wT70DC1eJx1XEmZWBL1wewGK1viWK1cBEAF75Ad8ZACg06WrbV-lk7R-Qh9OGbYEvlbYTm9IeDy7gw6x6FrSH2LnUXnFY-mLBDgZdMx2KrF3weim9B9dhw130zBQUc.qjapENuaQ2He-Dqp-B7cVnFn3WK2B-BBawgzZ6J78WE&dib_tag=se&qid=1725951521&s=wireless&sr=1-12),
mediante a técnicas de web scrapping. Esta url irá variando con cada
producto.

-Fecha de recogida: No hay una fecha específica disponible dentro del
conjunto de datos, pero la columna de marcas de tiempo sugiere que los
datos fueron recopilados a partir del 6 de septiembre de 2024,
basándonos en la reseña más reciente. Los datos complementario que
obtuvimos, fueron extraídos el día
4 de Octubre de 2024.

-Formato de los datos: Estos se encuentra en formato csv.

-Licencia de uso: No se proporciona información explícita sobre ningún
tipo de licencia de uso, sin embargo es preciso cumplir con lo términos
y condiciones de la política de Scrapping de la api de
Amazon(https://www-scraperapi-com.translate.goog/blog/amazon-web-scraping-policy/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=rq#:~:text=While%20scraping%20Amazon's%20public%20data,data%2C%20or%20any%20sensitive%20information.).

-Descripción de las Variables o Atributos:

        1       ID: Identificador del producto (entero).
        2       product_name (nombre del producto): Nombre del producto Apple (cadena de texto).
        3       product_link (enlace del producto): URL a la página del producto (cadena de texto).
        4       image_link (enlace de la imagen): URL de la imagen del producto (cadena de texto).
        5       Price (Dollar) (precio en dólares): Precio actual del producto en USD (número decimal).
        6       discount_percentage (porcentaje de descuento): Porcentaje de descuento aplicado al producto.(número decimal).
        7       price_before_discount (precio antes del descuento): Precio del producto antes de aplicar el descuento (número decimal).
        8       rating_out_of_5 (valoración sobre 5): Valoración media dada por los clientes (número decimal).
        9       number_of_ratings (número de valoraciones): Total de valoraciones de los clientes (número decimal).
        10      brand (marca): Marca del producto, que en este caso es siempre "Apple" (cadena de texto).
        11      operating_system (sistema operativo): Sistema operativo del dispositivo (cadena de texto).
        12      RAM (GB): Cantidad de memoria RAM en gigabytes (número decimal).
        13      CPU: Información del procesador (si está disponible, cadena de texto).
        14      Storage (GB) (almacenamiento en GB): Cantidad de almacenamiento en gigabytes (número decimal).
        15      screen_size (Inches) (tamaño de pantalla en pulgadas): Tamaño de la pantalla en pulgadas (número decimal).
        16      cellular_technology (tecnología celular): Lista de tecnologías celulares compatibles (cadena de texto).
        17      model_name (nombre del modelo): Nombre o serie del modelo del producto (cadena de texto).
        18      cpu_model (modelo del procesador): Modelo específico del procesador (cadena de texto).
        19      available_colors (colores disponibles): Lista de colores disponibles para el producto (cadena de texto).
        20      review (reseña): Comentarios o reseñas de los clientes sobre el producto (cadena de texto).
        21      timestamp (marca de tiempo): Fecha de la reseña (cadena de texto).
        22      stars (estrellas): Valoración en estrellas de la reseña (número decimal).

