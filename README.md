Reconocimiento del abecedario en el Lenguaje de Señas Peruano(LSP)
========
Abstract
-----

Resumen
-----

Introduccion
-----

Ha habido personas sordas en todos los momentos de la historia humana, y en todas partes en que estas han formado una comunidad, una lengua de señas ha surgido.

El lenguaje de señas es un tipo de lenguaje que utiliza movimientos de manos, expresiones faciales y lenguaje corporal para comunicarse. Lo utilizan las personas sordas y las personas que no pueden hablar pero si oir. Pero también lo utilizan personas oyentes, con mayor frecuencia familias y parientes de los sordos, e intérpretes que permiten que los sordos y comunidades más amplias se comuniquen entre sí.

El Lenguaje de Señas(LSP) es una lengua originaria peruana creada por la comunidad sorda del Peru. De igual manera a todas las lenguas, a partir de ella se construye la identidad, la cultura, el conocimiento ancestral y las prácticas sociales de sus usuarios. 

Por tal motio el Lenguaje de Señas entre países y regiones puede diferir en diversas partes de su estructura y gramatica, el Lenguaje de Señas Peruano(LSP) es diferente al que se usa en Brasil, USA, Bolivia, Uruguay, Argentina o en Chile.



![cnn](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/cnn.png)


  Con la ayuda de la ciencia y la tecnología avanzadas, el investigador desarrolla muchas técnicas para que las personas sordas se comuniquen con mucha fluidez. Los lenguajes de señas son los medios básicos de comunicación entre las personas con discapacidad auditiva. Imagine que desea tener una conversación con una persona sorda, entonces el lenguaje de señas tiene varios gestos y lenguajes corporales para transmitir mensajes a diferencia del patrón de habla verbal. Esto ya puede parecer una tarea tediosa, especialmente si no tienes idea de cómo comunicarte usando el lenguaje de señas. Tal es el problema al que se enfrentan millones de personas sordas que no pueden comunicarse e interactuar con personas oyentes. p.ej. sistemas de reconocimiento de texto y gestos. El reconocimiento del lenguaje de señas es muy importante no para el campo de la ingeniería sino también para la sociedad. Por lo tanto, los avances tecnológicos prometen brindar soluciones para que los sordos se comuniquen con la sociedad. Los sistemas de traducción del lenguaje de señas podrán mejorar la comunicación y permitir que la comunidad sorda disfrute de una participación plena en la interacción diaria y el acceso a la información y los servicios. Los lenguajes de señas de todo el mundo utilizan gestos estáticos y dinámicos, expresiones faciales y posturas corporales para la comunicación. A primera vista, como idea, qué difícil podría hacer un conversor de lenguajes de señas. La pérdida de la audición y del habla puede hacer que las personas se aíslen y se sientan solas, lo que afectará aún más su vida social y laboral. Buscar el significado de un signo no es una tarea sencilla. El lenguaje de señas es un gesto de código bien estructurado donde cada gesto tiene un significado asignado. La Lengua de Signos es el único medio de comunicación para las personas sordas. Con el avance de la ciencia y la tecnología se han desarrollado muchas técnicas no solo para minimizar el problema de las personas sordomudas sino también para implementarlo en diferentes campos. El lenguaje de señas es un lenguaje que, en lugar de patrones de voz o sonido, utiliza la comunicación manual y el lenguaje corporal para transmitir el significado. Esto implica principalmente la combinación de formas, orientación y movimiento de las manos. El lenguaje de señas no solo lo usan los sordos, sino también los que pueden oír, pero no pueden hablar físicamente. Toda la Federación India de Sordos estima que alrededor de 4 millones de personas sordas y más de 10 millones de personas tienen problemas de audición en la India. Los estudios dicen que una de cada cinco personas sordas en el mundo es india. De ellos, más de 1,5 millones de sordos

Motivacion
-----

Facilitar la comunicacion entre personas no sordomudas y personas sordomudas. Fortaleciendo el desarrollo personal y profesional de las personas sordomudas en la sociedad.  

Objetivos de Investigacion
-----

Construir un algoritmo que mediante la visualizacion de signos estaticos del Lenguaje de Señas pueda convertirlos a texto, haciendo uso de las redes neuronales convolucionales por siglas en ingles CNN.


Estado del Arte
-----

Realidad
-----

El Lenguaje de Señas Peruano(LSP) no cuenta con el debido reconocimiento por parte de las políticas públicas. A pesar de ser una lengua oficial(Ley 29535), hasta el momento los textos especializados que listan las lenguas peruanas no la incluyen. 
La educación de la persona sorda en nuestro país está todavía estancada en el viejo paradigma clínico y oralista. Las niñas sordas y los niños sordos en el Perú no reciben oportunamente acceso a la lengua de señas, y quedan así privados de oportunidades valiosas para su desarrollo academico y social, lo que constituye un acto de negligencia que vulnera sus derechos básicos como persona.

Problematica
-----

El Lenguaje de Señas es un lenguaje visual, por ello nuestro proyecto no asimila los siguientes signos: j, ñ, ll, rr, s, z. Signos realizados mediante movimientos de zig-zag o de repeticion, a diferencia de los demas signos que se pueden entender de manera estatica. Debido a su complejidad visual para poder formar parte de nuestro algoritmo de reconocimiento de signos, no son asimilados en nuestro proyecto.   

Metodologia
-----

Para poder construir nuestro dataset, comenzamos grabando nuestra mano ya sea la mano izquierda o la derecha debido a que los signos se interpretan de la misma manera sin importar con que mano se realizan. Grabando cada signo durante 40s siendo 02 videos por signo(02 manos), en total 46 videos de 40s cada uno. 

Creamos las siguientes carpetas: GS_28, GS_50, RGB_28, RGB_50. Donde se almacenaran nuestros dataset conforme sea customizados. 

Seguidamente ordenamos nuestos videos en carpetas con el nombre de las letras del abecedario, cargamos nuestro dataset de videos, definiendo las dimensiones en pixeles que deseamos obtener de los frames de nuestros videos y customizando los canales a analisar(RGB y GRAYSCALE), al siguiente script:

```
from_mp4_to_jpg.py
```

Ordenamos nuestro nuevo dataset de fotos en carpetas con el nombre de las letras del abecedario. 
Cargamos nuestro dataset de fotos,ordenandolos en las filas por etiquetas y en las columnas por pixeles , al siguiente script:

```
convert_to_csv.py
```

Con un tal de 784 columnas para los frames de (28px)x(28px), 2500 columnas para los frames de (50px)x(50px) en escalas de grises. Y en los 03 canales(RGB) 2352 columnas para los frames de (28px)x(28px), 7500 columnas para los frames de (50px)x(50px).

Ahora que tenemos nuestro dataset en archivos csv,mezclaremos las filas con susrespectivas etiquetas para ser mas dinamico el aprendizaje de nuestro modelo.
Para ello cargaremos nuestro dataset de archivos csv al siguiente script:

```
shuffle.py
```
Seguidamente separamos cada archivo csv en dos tipos, el primero sera para el entrenamiento del modelo y el segundo sera para la prueba(testeo) del modelo este ultimo archivo sera de menor cantidad. Todos los archivos(csv) de entrenamiento tienen en total 32992 filas y los archivos(csv) de prueba(testeo) tienen en total 13000 filas. 

Obteniendo 04 conjuntos de datasets:

*Primer Conjunto: S_GRAY_28, T_GRAY_28

*Segundo Conjunto: S_GRAY_50, T_GRAY_50

*Tercer Conjunto: S_RGB_28, T_RGB_28

*Cuarto Conjunto: S_RGB_50, T_RGB_50

S_ : Data de entrenamiento.
T_ : Data de prueba(testeo).


Experimental
-----

Iniciamos ploteando nuestros frames con sus respectivas etiquetas, en un grid de (5)x(5): 

```
Ploting_images.py
```

Seguidamente ploteamos nuestro conteo de frames por etiquetas, para ello hacemos uso del siguiente script:

```
Ploting_images.py
```
Ademas en el codigo anterior se construye nuestro modelo de entrenamiento(Sequential), veamoslo detenidamente:

```
# La funcion ImageDataGenerator, permitira a nuestro modelo aprender mediante rotaciones de nuestros frames en su mismo plano
datagen = ImageDataGenerator(featurewise_center=False, 
    samplewise_center=False, 
    featurewise_std_normalization=False, 
    samplewise_std_normalization=False,
    zca_whitening=False,
    zca_epsilon=1e-06,
    rotation_range=15,
    width_shift_range=0.1, 
    height_shift_range=0.1,
    shear_range=0.3, 
    zoom_range=0.1,
    channel_shift_range=0.0, 
    fill_mode="nearest",
    horizontal_flip=False, 
    vertical_flip=True, 
    validation_split=0.0,)

datagen.fit(x_train)

# Comienza la construcción del modelo en Keras: Sequential.
model = Sequential()

# Primera capa Conv2D con un numero de filtros: 64.  Ancho de la ventana convolucional: 3.
model.add(Conv2D(64, kernel_size = (3, 3), activation = 'relu', input_shape = (t, t, 3)))

# Introduciendo la primera capa de pooling, para reducir las dimensiones de salida
model.add(MaxPooling2D(pool_size = (2, 2)))
model.add(Dropout(0.20))

# Primera capa Conv2D con un numero de filtros: 64  Ancho de la ventana convolucional: 3.
model.add(Conv2D(64, kernel_size = (3, 3), activation = 'relu'))

# Introduciendo la tercera capa de pooling, para reducir las dimensiones de salida
model.add(MaxPooling2D(pool_size = (2, 2)))
model.add(Dropout(0.20))

# Primera capa Conv2D con un numero de filtros: 64  Ancho de la ventana convolucional: 3.
model.add(Conv2D(64, kernel_size = (3, 3), activation = 'relu'))

# Introduciendo la cuarta capa de pooling, para reducir las dimensiones de salida
model.add(MaxPooling2D(pool_size = (2, 2)))
model.add(Dropout(0.20))

# La instruccion Flatten() convierte los elemntos de la matriz de la imagen en un array plano.
model.add(Flatten())

# Cuarta capa con 128 nudos.
model.add(Dense(128, activation = 'relu'))
model.add(Dropout(0.20))

# Capa de salida con activacion "softmax" y 24 nudos.
model.add(Dense(num_classes, activation = 'softmax'))
```

Guardando el modelo de entrenamiento de nuestros 04 conjuntos de dataset, en archivos de extension h5:

*Modelo GRAY_28: GRAY_28_100Epocas.h5

*Modelo GRAY_50: GRAY_50_100Epocas.h5

*Modelo RGB_28: RGB_28_100Epocas.h5

*Modelo RGB_28: RGB_50_100Epocas.h5

Resultados
-----

Visualizacion de los frames con su respectivas etiquetas:

*GRAY_BINARY_28

![GRAY_BINARY_28](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/GRAY_BINARY_28.png)

*GRAY_GREEN_28

![GRAY_GREEN_28](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/GRAY_GREEN_28.png)

*GRAY_BINARY_50

![GRAY_BINARY_50](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/GRAY_BINARY_50.png)

*GRAY_GREEN_50

![GRAY_GREEN_50](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/GRAY_GREEN_50.png)

*RGB_BINARY_28

![RGB_BINARY_28](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/RGB_BINARY_28.png)

*RGB_BINARY_50

![RGB_BINARY_50](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/RGB_BINARY_50.png)


Ahora, mostrandose los ploteos del conteo de frames por etiqueta de cada uno de nuestros conjuntos de dataset:

*Conteo de GRAY_28

![CONTEO_28](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/CONTEO_28.png)

*Conteo GRAY_50

![Conteo](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/Conteo.png)

*Conteo RGB_28

![RGB_conteo_28](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/RGB_conteo_28.png)

*Conteo RGB_50

![RGB_conteo_50](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/RGB_conteo_50.png)

Ahora mostramos las graficas de "Accuracy vs Epocas" y "Loss vs Epocas", obtenidas de cada dataset:

*GRAY_28

![GRAY_Accuracy_28](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/GRAY_Accuracy_28.png)

![GRAY_Loss_28](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/GRAY_Loss_28.png)

*GRAY_50

![GRAY_Accuracy_50](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/GRAY_Accuracy_50.png)

![GRAY_Loss_50](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/GRAY_Loss_50.png)

*RGB_28

![RGB_Accuracy_28](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/RGB_Accuracy_28.png)

![RGB_Loss_28](https://github.com/M-O-R-P-H-E-U-S/N_Clasificacion-del-Abecedario-Mudo-Peruano/blob/main/RGB_Loss_28.png)

*RGB_50

![RGB_Accuracy_50]()

![RGB_Loss_50]()


Ahora la evaluacion el modelo, con dataset GRAY_28:
```
722/722 - 3s - loss: 0.0375 - accuracy: 0.9877 - 3s/epoch - 4ms/step
```
El accuracy del modelo, con dataset GRAY_28:
```
0.9877457618713379
```

Ahora la evaluacion el modelo, con dataset GRAY_50:
```
722/722 - 8s - loss: 2.5148e-04 - accuracy: 1.0000 - 8s/epoch - 11ms/step
```
El accuracy del modelo, con dataset GRAY_50:
```
0.9999567270278931
```

Ahora la evaluacion el modelo, con dataset RGB_28:
```
722/722 - 3s - loss: 0.0238 - accuracy: 0.9935 - 3s/epoch - 4ms/step
```
El accuracy del modelo, con dataset RGB_28:
```
0.9935048222541809
```


Ahora la evaluacion el modelo, con dataset RGB_50:
```

```
El accuracy del modelo, con dataset RGB_50:
```

```





Conclusiones
-----




Trabajos Futuros
-----

El presente proyecto traza el camino para poder desarrollar un algoritmo mas sofisticado que cuente con un dataset mas robusto, donde se pueda facilitar la comunicacion entre las personas no sordomudas y las personas sordomudas.
