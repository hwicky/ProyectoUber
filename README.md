# Proyecto de Estimación de la Demanda de UBER en New York

Proyecto de predeicción la demanda de viajes de uber en función del horario en la ciudad de New York.<br><br>

#### 1.- Contexto UBER - New York

![](https://assets.turbologo.com/blog/es/2019/12/19132827/uber-logo-cover-958x575.png)

Uber es una empresa de Tecnología que facilita, por medio de su aplicación, que conductores privados encuentren personas que necesitan viajes seguros y confiables [Uber, 2015]. Hoy en día, es la principal empresa proveedora de servicios de transporte a través de una aplicación, siendo en latinoamérica la principal plataforma de viajes privados [Ramos, D. (27 de agosto 2018). Uber: Latinoamérica posee el mayor número de viajes. LatinAmerican Post, https://normas-apa.org/referencias/citar-revista/].

Las tarifas se cotizan al cliente por adelantado, pero varían mediante un modelo de precios dinámicos basado en la oferta y la demanda local en el momento de la reserva  [Uber, 2015], Por lo que el valor del servicio es fluctuante. En Estados Unidos, el Estado de New York cuenta con aproximadamente de 19,84 millones de acuerdo al último censo en 2021 [United States Census Bureau (Census), 2022] donde se suman alrededor de 50 millones de turistas anualmente [NYC Company,2019] , lo que la convierte en una de las principales ciudades turísticas e importantes del mundo; Lo anterior conlleva a que sea un mercado atractivo para el transporte privado de pasajeros, donde además los servicios de Uber son legales y regidos por el Gobierno de EEUU.<br><br>



#### 2.- Objetivo Proyecto UBER - New York
El objetivo de este proyecto es predecir la demanda de Uber en New York en función de la hora utilizando datos históricos. Para eso se utilizarán datos de 4.5 millones de viajes de Abril a Septiembre del 2014. La importancia de predecir lo anterior, radica en poder entregar información relevante a Uber, que ha tenido problemas de conductores específicamente en EEUU en los últimos años  [Hawkins, A. (11 de febrero de 2021). Uber and Lyft are getting less unprofitable, but COVID-19 is still a drag on their business. The Verge, https://www.theverge.com/2021/2/11/22277043/uber-lyft-earnings-q4-2020-profit-loss-covid], lo que permitiría ajustar sus tarifas para incentivar a conductores y mantener en equilibrio la oferta y demanda, además de implementar estrategias comerciales para poseer una sostenibilidad en un mercado competitivo, donde existen los Taxis y otras aplicaciones como Lyft y Cabify.<br><br>


##### Fuentes de Datos Proyecto UBER - New York

De las fuentes de datos disponibles de manera pública en la plataforma Kaggle, se identificaron 19 dataset potencialmente útiles para el desarrollo del proyecto, tras examinarlos  en detalle, se determinó que existen 6 de ellos con información relevante para realizar una predicción de demanda de la empresa Uber, puesto que poseen una temporalidad continua de sus datos y éstos están etiquetados y se pueden interpretar como una serie de tiempo. Donde dicho dataset seleccionados corresponden a toma de datos mensuales, en el periodo Abril-Septiembre del año 2014, donde existiendo datos etiquetados respecto a 4 variables:

- Date/Time: Que indica el mes, día y hora en que fue solicitado el Uber.<br>
- Lat: Que indica la latitud, medida en grados, donde fue solicitado el Uber, que combinada con la variable longitud determina una ubicación geográfica específica.<br>
- Lon: Que indica la latitud, medida en grados, donde fue solicitado el Uber, que combinada con la variable latitud determina una ubicación geográfica específica.<br>
- Base: La clasificación del Tipo de Vehículo (Uber) de acuerdo a la Comisión de Taxis y Limusina de EEUU (TLC).<br><br>

#### 4.- Requisitos Proyecto UBER - New York

Para poder desarrollar el presente Proyecto es importante comentar que es necesario, en primer lugar, la utilización de un lenguaje de programación y su interperete correspondiente.

**A) Lenguajes de Programación e Intérprete**

En este proyecto se recomienda utilizar:<br> 

- Como lenguaje de programamación -->**Python 3.6 o superior**.<br> 

- Como interprete se recomienda usar --> **Google Colab**.





**B) Librerías, Bibliotecas o Módulos del Lenguaje de Programación**
Además es importante obtener e instalar las últimas versiones de los siguientes móduloes/librerías, en este proyecto se recomienda utilizar:<br> 

- pandas
- numpy
- os
- matplotlib.pyplot
- adfuller, (importándola desde statsmodels.tsa.stattools)
- seaborn 
- KMeans (importándola desde sklearn.cluster) 
- Counter (importándola desde collections)
- acf, pacf (importándola desde statsmodels.tsa.stattools)
- ARIMA (importándola desde statsmodels.graphics.tsaplots)
- plot_predict (importándola desde statsmodels.graphics.tsaplots) 
- RandomForestRegressor (importándola desde sklearn.ensemble)
- mean_absolute_error (importándola desde sklearn.metrics)  
- Image (importándola desde IPython.display) <br> <br> 

**C) Datasets o Fuentes de Datos**

Es necesario contar con un data ser que cuente con un mínimo de información, tal como:

1.- Mes, día y hora en que fue solicitado el Uber.

2.- Latitud, medida en grados, donde fue solicitado el Uber.

3.- Longitud, medida en grados, donde fue solicitado el Uber.

Adicionalmente algúna variable que permita identificar el tipo de Vehículo (Uber).

<br> 


#### 5.- Instalación de Requerimientos para Proyecto UBER - New York

**A) Lenguaje e Interprete**

- Para la instalación de  Python 3.6 o superior, se puede descargar e instalar desde (https://www.python.org/downloads/).

- En el caso de usar un interpetrete como el recomendado, se realiza desde la web,  el cual se recomienda por el consumo de recursos y se puede trabajar en línea desde https://colab.google/, contando con una sesión o cuenta de Google.  <br> 

- Es posible utilizar otros entornos locales de Python como Anaconda.


**B) Librerías, Bibliotecas o Módulos del Lenguaje de Programación**
Para la importación e instalación de librerías/blibliotecas y módulos mencionados es necesario llamarlos en el interprete de código de la siguiente manera.

```javascript
import pandas as pd
import numpy as np
import os
import matplotlib.pyplot as plt
from statsmodels.tsa.stattools import adfuller
import seaborn as sns

from sklearn.cluster import KMeans
from collections import Counter
from statsmodels.tsa.stattools import acf, pacf
from statsmodels.tsa.arima.model import ARIMA
from statsmodels.graphics.tsaplots import plot_predict
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import mean_absolute_error
from IPython.display import Image
```
En el caso de no contar con alguna libreria instalada (que no debiese ocurrir) se debe instalar a traves de
```javascript
!pip install <Inserte nombre de librería a instalar>
```

<br> 

**C) Datasets o Fuentes de Datos**
Para la obtención de un data set, se recomienda utilizar la plataforma kaggle o similar.
En el caso de este proyecto se trabajó con el siguiente data set:  https://www.kaggle.com/datasets/fivethirtyeight/uber-pickups-in-new-york-city

El cual se recomienda descargar localmente y luego cargar Google Coolab a través del navegador utilizado (Chrome recomendado) en la carpeta /data y concatenarlos dentro del libro a utilizar el proyecto, lo cual se puede realizar a través de los siguientes comandos:

```javascript
data_path  ='data/'
dfs = []

for f in os.listdir('data'):
    dfs.append(pd.read_csv(data_path+f))
    print(data_path+f)

len(dfs)

dataset = pd.concat(dfs) 
dataset.info(verbose = True , null_counts = True)

```
#### 6.- Uso y Caso Práctico
Para explicar el uso, se realizará a través del caso implementado se debe dirigir al archivo 

https://github.com/hwicky/ProyectoUber/blob/main/Proyecto%20Uber%20-%20Septiembre%202023.ipynb <br> <br> 

### 7.- Contribuciones
En el proyecto en cuestión, se aceptan todo tipo de contribuciones, ya sea corrección u oprimización del código, aumento del dataset disponible, prueba de nuevos modelos, etc. <br> <br> 

###8.- Autores
El presente proyecto fue desarrollado por Manuel Pérez Beltrán y Hans Wicky Torres en el marco de un Proyecto Aplicado para la aprobación de la asignatura de Análitica de Datos del Magíster en Ciencia de Datos para la Innovación de la Universidad de Concepción, Chile. <br> <br> 

###9.- Licencias

-	Licencia

Este proyecto se distribuye bajo los términos de la Licencia MIT.

-	Términos de Uso

Puede utilizar, modificar y distribuir este software de acuerdo con los términos de la Licencia MIT.

-	Licencia Completa

Para obtener más detalles sobre los términos de la Licencia MIT, consulte el archivo [LICENSE](LICENSE) en este repositorio.

-	Aviso de Licencia de Terceros

Este proyecto utiliza bibliotecas de terceros, incluyendo NumPy, Pandas,otras, que pueden tener sus propias licencias. Consulte la documentación de cada biblioteca para obtener información sobre sus respectivas licencias.
