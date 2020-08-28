## Coloración de imágenes de naturaleza a partir del uso de una red generativa adversaria condicional (cGAN)

### Resumen

En el presente trabajo se aplica una red generativa adversaria condicional basada en el trabajo de Isola et al. (2016) para generar imágenes ficticias de naturaleza condicionadas a imágenes reales utilizadas como entradas al modelo. Se puede observar que esta estructura es capaz de colorear imágenes en blanco y negro de una dimensión mediana (256x256) en un corto periodo de entrenamiento, pero tiende a aplicar la misma tonalidad de colores generando poca variedad de contrastes. Por otro lado, dicha estructura no es capaz de colorear de forma consistente y realista imágenes con información faltante en ellas lo que sugiere la necesidad de aplicar otro tipo de estructura generativa.

#### 1.	Introducción y Marco Teórico

Los modelos generativos adversarios (GAN) para muchos autores son de las aplicaciones más interesantes de Deep Learning por su capacidad de generar información, por lo general imágenes, extremadamente realistas. Las GANs son un tipo de red neuronal relativamente nuevo planteado por primera vez por Goodfellow et al. (2014) el cual consiste en entrenar de forma simultánea dos modelos: un modelo generativo G que captura la distribución de los datos y un modelo discriminador D que estima la probabilidad de que una muestra provenga de los datos de entrenamiento en lugar que de G. El procedimiento de entrenamiento consiste en que G maximiza la probabilidad de que D cometa un error (Goodfellow et al., 2014), es decir, el generador trata de crear imágenes falsas que sean capaces de engañar al discriminador, mientras este último trata de no ser engañado.
En la actualidad este tipo de red es de las más populares y cada año se presentan nuevas arquitecturas cada vez más complejas, más difíciles de entrenar y capaces de crear imágenes cada vez más realistas. Las estructuras de las GANs son tan variadas como el propósito de estas, Brock et al. (2018) y Jin et al. (2017) desarrollan estructuras capaces de crear imágenes condicionadas a una descripción en palabras de estas, Mordvintsev et al. (2015)  crea una red capaz de crear imágenes que resaltan los patrones surrealistas presentes en estas, Gatys et al. (2015) crea nuevas imágenes transfiriendo el estilo desde otra, Zhu et al. (2017) realiza un proceso similar en una red denominada cycleGAN la cual se base en el trabajo de Isola et al. (2016) quienes desarrollan una red capaz de conservar el contorno de una imagen de entrada y modificar el fondo de esta. Todos estos modelos se enmarcan en tu tipo especial de GAN llamada red generativa adversaria condicional (cGAN) (Mirza & Osindero, 2014) las cuales generan imágenes no solo a partir de ruido, sino que este es acompañado de información extra, etiquetas u otras imágenes.
Uno de los problemas de procesamiento de imágenes y visión computacional corresponde a trasladar una imagen de entrada a una de salida. Isola et al. (2016) platean una solución a dicho problema a través de una red generativa adversaria condicional (cGAN) que emplea una imagen de entrada para generar una imagen de salida diferente, de forma sencilla, transforma una imagen en otra. En este trabajo se empleará esta red para generar imágenes de naturaleza y estudiar los alcances de la capacidad generativa de este modelo.

### 2.	Metodología
#### 2.1.	Red Pix2Pix

En el presente trabajo se aplica la cGAN desarrollada por Isola et al. (2016) denominada pix2pix la cual al igual que todas las GANs está conformada por generador y un discriminador, pero con algunas variaciones. 
En una cGAN el generador mapea desde un vector de imágenes x junto con ruido z para generar una imagen de salida y de la forma G:{x,y} →y. En este caso el generador está conformado por una U-net (Ronneberger et al. 2015) la cual es una red convolucional encoder - decoder donde en el decoder se hacen pasar nuevamente las imágenes obtenidas en el encoder apiladas con las obtenidas en la capa anterior del decoder





