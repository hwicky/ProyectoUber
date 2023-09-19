# Proyecto de Estimación de la Demanda de UBER en New York

Proyecto de predeicción la demanda de viajes de uber en función del horario en la ciudad de New York.<br><br>

#### UBER - New York

![](https://assets.turbologo.com/blog/es/2019/12/19132827/uber-logo-cover-958x575.png)

Uber es una empresa de Tecnología que facilita, por medio de su aplicación, que conductores privados encuentren personas que necesitan viajes seguros y confiables [Uber, 2015]. Hoy en día, es la principal empresa proveedora de servicios de transporte a través de una aplicación, siendo en latinoamérica la principal plataforma de viajes privados [Ramos, D. (27 de agosto 2018). Uber: Latinoamérica posee el mayor número de viajes. LatinAmerican Post, https://normas-apa.org/referencias/citar-revista/].

Las tarifas se cotizan al cliente por adelantado, pero varían mediante un modelo de precios dinámicos basado en la oferta y la demanda local en el momento de la reserva  [Uber, 2015], Por lo que el valor del servicio es fluctuante. En Estados Unidos, el Estado de New York cuenta con aproximadamente de 19,84 millones de acuerdo al último censo en 2021 [United States Census Bureau (Census), 2022] donde se suman alrededor de 50 millones de turistas anualmente [NYC Company,2019] , lo que la convierte en una de las principales ciudades turísticas e importantes del mundo; Lo anterior conlleva a que sea un mercado atractivo para el transporte privado de pasajeros, donde además los servicios de Uber son legales y regidos por el Gobierno de EEUU.<br><br>



#### Objetivo Proyecto UBER - New York
El objetivo de este proyecto es predecir la demanda de Uber en New York en función de la hora utilizando datos históricos. Para eso se utilizarán datos de 4.5 millones de viajes de Abril a Septiembre del 2014. La importancia de predecir lo anterior, radica en poder entregar información relevante a Uber, que ha tenido problemas de conductores específicamente en EEUU en los últimos años  [Hawkins, A. (11 de febrero de 2021). Uber and Lyft are getting less unprofitable, but COVID-19 is still a drag on their business. The Verge, https://www.theverge.com/2021/2/11/22277043/uber-lyft-earnings-q4-2020-profit-loss-covid], lo que permitiría ajustar sus tarifas para incentivar a conductores y mantener en equilibrio la oferta y demanda, además de implementar estrategias comerciales para poseer una sostenibilidad en un mercado competitivo, donde existen los Taxis y otras aplicaciones como Lyft y Cabify.<br><br>


#### Fuentes de Datos Proyecto UBER - New York

De las fuentes de datos disponibles de manera pública en la plataforma Kaggle, se identificaron 19 dataset potencialmente útiles para el desarrollo del proyecto, tras examinarlos  en detalle, se determinó que existen 6 de ellos con información relevante para realizar una predicción de demanda de la empresa Uber, puesto que poseen una temporalidad continua de sus datos y éstos están etiquetados y se pueden interpretar como una serie de tiempo. Donde dicho dataset seleccionados corresponden a toma de datos mensuales, en el periodo Abril-Septiembre del año 2014, donde existiendo datos etiquetados respecto a 4 variables:

**Date/Time:** Que indica el mes, día y hora en que fue solicitado el Uber.<br>
**Lat:** Que indica la latitud, medida en grados, donde fue solicitado el Uber, que combinada con la variable longitud determina una ubicación geográfica específica.<br>
**Lon:** Que indica la latitud, medida en grados, donde fue solicitado el Uber, que combinada con la variable latitud determina una ubicación geográfica específica.<br>
**Base:** La clasificación del Tipo de Vehículo (Uber) de acuerdo a la Comisión de Taxis y Limusina de EEUU (TLC).<br><br><br>

#### Requisitos Proyecto UBER - New York

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

<br> <br> 


#### Instalación de Requerimientos para Proyecto UBER - New York

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

**Table de Contenidos**

[TOCM]

[TOC]

#H1 header
##H2 header
###H3 header
####H4 header
#####H5 header
######H6 header
#Heading 1 link [Heading link](https://github.com/pandao/editor.md "Heading link")
##Heading 2 link [Heading link](https://github.com/pandao/editor.md "Heading link")
###Heading 3 link [Heading link](https://github.com/pandao/editor.md "Heading link")
####Heading 4 link [Heading link](https://github.com/pandao/editor.md "Heading link") Heading link [Heading link](https://github.com/pandao/editor.md "Heading link")
#####Heading 5 link [Heading link](https://github.com/pandao/editor.md "Heading link")
######Heading 6 link [Heading link](https://github.com/pandao/editor.md "Heading link")

##Headers (Underline)

H1 Header (Underline)
=============

H2 Header (Underline)
-------------

###Characters
                
----

~~Strikethrough~~ <s>Strikethrough (when enable html tag decode.)</s>
*Italic*      _Italic_
**Emphasis**  __Emphasis__
***Emphasis Italic*** ___Emphasis Italic___

Superscript: X<sub>2</sub>，Subscript: O<sup>2</sup>

**Abbreviation(link HTML abbr tag)**

The <abbr title="Hyper Text Markup Language">HTML</abbr> specification is maintained by the <abbr title="World Wide Web Consortium">W3C</abbr>.

###Blockquotes

> Blockquotes

Paragraphs and Line Breaks
                    
> "Blockquotes Blockquotes", [Link](http://localhost/)。

###Links

[Links](http://localhost/)

[Links with title](http://localhost/ "link title")

`<link>` : <https://github.com>

[Reference link][id/name] 

[id/name]: http://link-url/

GFM a-tail link @pandao

###Code Blocks (multi-language) & highlighting

####Inline code

`$ npm install marked`

####Code Blocks (Indented style)

Indented 4 spaces, like `<pre>` (Preformatted Text).

    <?php
        echo "Hello world!";
    ?>
    
Code Blocks (Preformatted text):

    | First Header  | Second Header |
    | ------------- | ------------- |
    | Content Cell  | Content Cell  |
    | Content Cell  | Content Cell  |

####Javascript　

```javascript
function test(){
	console.log("Hello world!");
}
 
(function(){
    var box = function(){
        return box.fn.init();
    };

    box.prototype = box.fn = {
        init : function(){
            console.log('box.init()');

			return this;
        },

		add : function(str){
			alert("add", str);

			return this;
		},

		remove : function(str){
			alert("remove", str);

			return this;
		}
    };
    
    box.fn.init.prototype = box.fn;
    
    window.box =box;
})();

var testBox = box();
testBox.add("jQuery").remove("jQuery");
```

####HTML code

```html
<!DOCTYPE html>
<html>
    <head>
        <mate charest="utf-8" />
        <title>Hello world!</title>
    </head>
    <body>
        <h1>Hello world!</h1>
    </body>
</html>
```

###Images

Image:

![](https://pandao.github.io/editor.md/examples/images/4.jpg)

> Follow your heart.

![](https://pandao.github.io/editor.md/examples/images/8.jpg)

> 图为：厦门白城沙滩 Xiamen

图片加链接 (Image + Link)：

[![](https://pandao.github.io/editor.md/examples/images/7.jpg)](https://pandao.github.io/editor.md/examples/images/7.jpg "李健首张专辑《似水流年》封面")

> 图为：李健首张专辑《似水流年》封面
                
----

###Lists

####Unordered list (-)

- Item A
- Item B
- Item C
     
####Unordered list (*)

* Item A
* Item B
* Item C

####Unordered list (plus sign and nested)
                
+ Item A
+ Item B
    + Item B 1
    + Item B 2
    + Item B 3
+ Item C
    * Item C 1
    * Item C 2
    * Item C 3

####Ordered list
                
1. Item A
2. Item B
3. Item C
                
----
                    
###Tables
                    
First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell 

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

| Function name | Description                    |
| ------------- | ------------------------------ |
| `help()`      | Display the help window.       |
| `destroy()`   | **Destroy your computer!**     |

| Item      | Value |
| --------- | -----:|
| Computer  | $1600 |
| Phone     |   $12 |
| Pipe      |    $1 |

| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
                
----

####HTML entities

&copy; &  &uml; &trade; &iexcl; &pound;
&amp; &lt; &gt; &yen; &euro; &reg; &plusmn; &para; &sect; &brvbar; &macr; &laquo; &middot; 

X&sup2; Y&sup3; &frac34; &frac14;  &times;  &divide;   &raquo;

18&ordm;C  &quot;  &apos;

##Escaping for Special Characters

\*literal asterisks\*

##Markdown extras

###GFM task list

- [x] GFM task list 1
- [x] GFM task list 2
- [ ] GFM task list 3
    - [ ] GFM task list 3-1
    - [ ] GFM task list 3-2
    - [ ] GFM task list 3-3
- [ ] GFM task list 4
    - [ ] GFM task list 4-1
    - [ ] GFM task list 4-2

###Emoji mixed :smiley:

> Blockquotes :star:

####GFM task lists & Emoji & fontAwesome icon emoji & editormd logo emoji :editormd-logo-5x:

- [x] :smiley: @mentions, :smiley: #refs, [links](), **formatting**, and <del>tags</del> supported :editormd-logo:;
- [x] list syntax required (any unordered or ordered list supported) :editormd-logo-3x:;
- [x] [ ] :smiley: this is a complete item :smiley:;
- [ ] []this is an incomplete item [test link](#) :fa-star: @pandao; 
- [ ] [ ]this is an incomplete item :fa-star: :fa-gear:;
    - [ ] :smiley: this is an incomplete item [test link](#) :fa-star: :fa-gear:;
    - [ ] :smiley: this is  :fa-star: :fa-gear: an incomplete item [test link](#);
            
###TeX(LaTeX)
   
$$E=mc^2$$

Inline $$E=mc^2$$ Inline，Inline $$E=mc^2$$ Inline。

$$\(\sqrt{3x-1}+(1+x)^2\)$$
                    
$$\sin(\alpha)^{\theta}=\sum_{i=0}^{n}(x^i + \cos(f))$$
                
###FlowChart

```flow
st=>start: Login
op=>operation: Login operation
cond=>condition: Successful Yes or No?
e=>end: To admin

st->op->cond
cond(yes)->e
cond(no)->op
```

###Sequence Diagram
                    
```seq
Andrew->China: Says Hello 
Note right of China: China thinks\nabout it 
China-->Andrew: How are you? 
Andrew->>China: I am good thanks!
```

###End
