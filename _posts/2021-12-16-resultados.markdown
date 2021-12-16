---
layout: post
title:  "Resultados"
date:   2021-12-16 00:00:00 -0300
categories: timag
---
La primer imágen es la proporcionada y luego las estimaciones de: núcleos muertos, núcleos vivos y parásitos, núcleos vivos, citoplasma y membrana, generadas para un par de valores de niveles de gris y ratio de morfología matemática.

Para cada estimación de núcleos se realizó el etiquetado en fiji y luego se midió el error con la función de python implementada. Por ejemplo, para una de las imágenes se obtuvieron dos cuadros, uno con la medida de precisión y otro con recall, como los siguientes:

(cuadro como los del excel)

Se observa que a medida que crece el ratio aumenta la precisión y cae el recall, esto tiene sentido pues filtra componentes pero las que quedan son más seguras. Un análisis similar se puede hacer para los niveles de gris, teniendo en cuenta que los niveles más oscuros son de núcleos muertos y por encima del 100 es casi todo citoplasma y membrana. A partir de estas medidas para 10 imágenes se eligió el mejor par de parámetros tanto para núcleos vivos como muertos. Estos fueron:

núcleos muertos:
	ratio=8
	threshold=[0;40]

núcleos vivos:
	ratio=8
	threshold=[20,80]
	
Para estos parámetros, se midió la precisión y el recall para las 5 imágenes restantes y se obtuvieron los siguientes resultados:

núcleos muertos:
	precisión=35%
	recall=82%

núcleos vivos:
	precisión=58%
	recall=75%
	
(Imagenes de componentes superpuestas, imagen y núcleos vivos e imágen y núcleos muertos, con y sin dilatar)

Por último se realizaron medidas cualitativas de las áreas consideradas y se vio que dilatar un poco aproximaba mejor a las superficies reales.