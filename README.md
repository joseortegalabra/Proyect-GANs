## Coloración de imágenes de naturaleza a partir del uso de una red generativa adversaria condicional (cGAN)
#### (Link informe completo) 
[https://drive.google.com/file/d/1S94INBuDNJGI3bO0whVZpmp7f5e6UTlF/view?usp=sharing]

#### (Link poster del trabajo_Inglés)
[https://drive.google.com/file/d/1KcOA67vkNROQczDyfhLlKvlfStsnO0OM/view?usp=sharing]



### 1. Resumen

En el presente trabajo se aplica una red generativa adversaria condicional basada en el trabajo de Isola et al. (2016) para generar imágenes ficticias de naturaleza condicionadas a imágenes reales utilizadas como entradas al modelo. Se puede observar que esta estructura es capaz de colorear imágenes en blanco y negro de una dimensión mediana (256x256) en un corto periodo de entrenamiento, pero tiende a aplicar la misma tonalidad de colores generando poca variedad de contrastes. Por otro lado, dicha estructura no es capaz de colorear de forma consistente y realista imágenes con información faltante en ellas lo que sugiere la necesidad de aplicar otro tipo de estructura generativa.



#### 2.1.	Red Pix2Pix

En el presente trabajo se aplica la cGAN desarrollada por Isola et al. (2016) denominada pix2pix la cual al igual que todas las GANs está conformada por generador y un discriminador, pero con algunas variaciones. 
En una cGAN el generador mapea desde un vector de imágenes x junto con ruido z para generar una imagen de salida y de la forma G:{x,y} →y. En este caso el generador está conformado por una U-net (Ronneberger et al. 2015) la cual es una red convolucional encoder - decoder donde en el decoder se hacen pasar nuevamente las imágenes obtenidas en el encoder apiladas con las obtenidas en la capa anterior del decoder





