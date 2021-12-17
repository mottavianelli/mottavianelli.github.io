---
layout: post
title:  "Conclusiones y trabajo a futuro"
date:   2021-12-16 00:00:00 -0300
categories: timag
---
Como conclusiones generales, consideramos que teniendo en cuenta las limitaciones de tiempo, el alcance del proyecto, y las dimensiones del problema planteado, si bien no se alcanzaron completamente los objetivos planteados dado que las estimaciones de los parásitos no logran alcanzar un nivel óptimo de detección, si se logró generar un algoritmo capaz de delimitar y contar núcleos con una medida de error razonable aunque no distingue correctamente en todos los casos entre núcleos vivos y núcleos muertos. A continuación se detallan las diferentes dificultades que se encontraron en el desarrollo del proyecto, y algunas consideraciones sobre el trabajo a futuro.

# Dificultades observadas y trabajo a futuro 

Se presenta un compromiso entre los niveles de gris que se dejan pasar, filtrados con la morfología matemática y las medidas de error (por ejemplo aumentar el radio, aumenta la precisión y disminuye el recall); podrían mejorar los resultados variando estos parámetros. De todas formas, consideramos que este método tiene ciertas limitaciones que requieren la incorporación de nuevas técnicas; y dado que se tienen datos de la función de conteo que se quiere estimar, es un problema al que se podría aplicar inteligencia artificial.
Como trabajo a futuro se propone utilizar algoritmos de crecimiento de regiones, en lugar de dilatar, para mejorar la estimación de las superficies. Es decir, una vez aplicadas las aperturas, tomar las superficies como semillas y correr crecimiento de regiones. También es una posibilidad aplicar Voronoi para determinar las zonas del citoplasma asociadas a cada núcleo; con esto se podría generar una herramienta que halle automáticamente los núcleos, citoplasma y membrana y que al ingresar el conteo de parásitos devuelva el porcentaje de células infectadas y cuántos amastigotes por célula infectada hay en promedio.
Asimismo, es necesario continuar desarrollando el algoritmo para resolver algunos problemas que aún no logra delimitar, por ejemplo el reconocimiento de núcleos vivos y muertos.