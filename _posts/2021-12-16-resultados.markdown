---
layout: post
title:  "Resultados"
date:   2021-12-16 00:00:00 -0300
categories: timag
---
La macro de Fiji y el script de Python para medida de error se encuentran en el [repositorio de github](https://github.com/mottavianelli/timag-trypanosomacruzi) asociado al proyecto. 

A continuación se exponen las imágenes resultantes del procesamiento aplicado. En primer lugar se muestra una de las imágenes proporcionadas por las científicas; las siguientes corresponden a los resultados obtenidos en cuanto a representaciones binarias aproximadas de: núcleos muertos, núcleos vivos y parásitos, núcleos vivos, citoplasma y membrana, generadas para una combinación de valores de niveles de gris y radio de elemento estructurante de morfología matemática.

![img_original](https://figshare.com/ndownloader/files/31868033/preview/31868033/preview.jpg)

![nucleos_muertos](https://figshare.com/ndownloader/files/31868042/preview/31868042/preview.jpg)

![nucleos_vivos_parasitos](https://figshare.com/ndownloader/files/31868048/preview/31868048/preview.jpg)

![nucleos_vivos](https://figshare.com/ndownloader/files/31868045/preview/31868045/preview.jpg)

![citoplasma](https://figshare.com/ndownloader/files/31868024/preview/31868024/preview.jpg)

![membrana](https://figshare.com/ndownloader/files/31868039/preview/31868039/preview.jpg)



Para cada estimación de núcleos se realiza el etiquetado en Fiji y se mide el error con la función de Python implementada. A modo de ejemplo se presenta a continuación la medida del error obtenido para una de las imágenes, donde puede observarse dos cuadros: uno corresponde a la precisión y el otro al recall:

| Recall   |     Radio   |              |  |              |              |              |
|----------|--------|--------------|-----------------|--------------|--------------|--------------|
|    Niveles de gris       | 		| 0-20         | 0-25            | 0-30         | 0-35         | 0-40         |
|    |      6 | 0.6153846154 | 0.7692307692    | 0.8846153846 | 0.9615384615 | 1            |
|          |      8 | 0.5384615385 | 0.7307692308    | 0.8076923077 | 0.8846153846 | 0.9230769231 |
|          |     10 | 0.4615384615 | 0.5             | 0.6538461538 | 0.7307692308 | 0.7692307692 |
|          |     12 | 0.3076923077 | 0.3461538462    | 0.5384615385 | 0.6538461538 | 0.7307692308 |


| Precission |     Radio     |              |  |              |              |              |
|----------|------------|--------------|-----------------|--------------|--------------|--------------|
|       Niveles de gris   |  | 0-20         | 0-25            | 0-30         | 0-35         | 0-40         |
|     |          6 | 0.5          | 0.5263157895    | 0.4107142857 | 0.3623188406 | 0.3661971831 |
|          |          8 | 0.6363636364 | 0.6333333333    | 0.5384615385 | 0.4509803922 | 0.380952381  |
|          |         10 | 0.9230769231 | 0.619047619     | 0.5666666667 | 0.5          | 0.4444444444 |
|          |         12 | 0.8888888889 | 0.6428571429    | 0.5833333333 | 0.5666666667 | 0.5277777778 |

A partir de los datos obtenidos, se observa que a medida que crece el radio de la operación morfológica, aumenta la precisión y disminuye el recall. Este comportamientO puede explicarse considerando que un elemento estructurante de mayor radio filtrará más compoenentes, pero aquellos que no son filtrados, garantizan mayor precisión. Un análisis similar puede aplicarse para los rangos de nivel de gris, teniendo en cuenta que los niveles más oscuros son de núcleos de células muertas y por encima del nivel 100, se encuentra principalmente citoplasma y membrana. En función de estas medidas para 10 imágenes, se elige el mejor par de parámetros tanto para núcleos vivos como muertos. Estos parámetros resultan:

- Núcleos de células muertas:
	 - radio = 8
	 - threshold = [0;40]

- Núcleos de células vivas:
	- radio = 8
	- threshold = [20,80]
	
Para estos parámetros, se mide la precisión y el recall para las 5 imágenes restantes, obteniendo los siguientes resultados:

- Núcleos de células muertas:
	- precisión = 35%
	- recall = 82%

- Núcleos de células vivas:
	- precisión = 58%
	- recall = 75%
	


Por último se realizaron medidas cualitativas de las áreas consideradas y se vio que dilatar un poco aproximaba mejor a las superficies reales.