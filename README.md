<div align="justify">

# Diseño y Simulación de Robot Planar con Autodesk Inventor

En este repositorio se presenta el desarrollo completo del **Diseño y Simulación de un Robot Planar** utilizando **Autodesk Inventor**. El objetivo fue concebir un manipulador de tres grados de libertad, simular su comportamiento dinámico bajo acción de la gravedad y trayectorias predefinidas, y, finalmente, seleccionar apropiadamente motores de corriente continua acoplados a reductores planetarios basados en los resultados obtenidos.

## Introducción

Durante la primera fase se definió la arquitectura mecánica del robot, partiendo de cinco piezas principales: la base, tres eslabones consecutivos y la herramienta final. Cada componente se modeló como un archivo independiente (.ipt) siguiendo los requisitos geométricos establecidos, de modo que la geometría final del ensamblaje respondiera a las especificaciones de rigidez y alcance requeridas para un robot planar.

## Diseño Mecánico

El proceso de diseño implicó crear cada pieza en **Inventor**, donde se parametrizaron cotas lineales y angulares para asegurar una fácil adaptación de medidas. Posteriormente, las piezas se ensamblaron en un solo archivo (.iam), definiendo restricciones de unión rotacional en cada articulación. Esta etapa garantizó que los ejes de giro coincidieran perfectamente y que la disposición volumétrica respetara los límites de colisión entre eslabones.

## Simulación Dinámica

Con el modelo ensamblado, se configuró la simulación dinámica activando la gravedad en el eje vertical y asignando curvas de velocidad específicas a cada junta. Las curvas —diseñadas previamente en Inventor— describen perfiles suaves de aceleración y desaceleración, permitiendo reproducir trayectorias realistas. Durante la simulación, se registraron las gráficas de posición, velocidad y momento en Z para las tres articulaciones, lo que proporcionó los valores máximos de par necesarios para dimensionar correctamente los actuadores.

## Selección de Motor y Reductor

A partir de los valores de par máximo extraídos de la simulación, se incorporó un factor de seguridad para calcular el par final requerido en cada articulación. A continuación, se eligieron motores de **corriente continua** y **reductores planetarios** de catálogo (fabricante: Maxon Motor) que cumplían simultáneamente dos condiciones: el par nominal del conjunto debía ser igual o superior al par final calculado, y la velocidad de salida resultante debía igualar o superar la velocidad angular máxima obtenida en la simulación. Las ecuaciones  
\[
\tau_{\text{final}} = \tau_{\text{motor}} \times \text{reducción} \times \text{eficiencia}, 
\quad
\omega_{\text{final}} = \frac{\omega_{\text{motor}}}{\text{reducción}}
\]  
fueron empleadas para validar cada combinación motor-reductor, garantizando así un dimensionado óptimo.

## Simulación de Trayectorias Adicionales

Finalmente, se diseñó una trayectoria alternativa partiendo de la configuración inicial. Inventor permitió actualizar las curvas de velocidad y volver a simular el movimiento completo, verificando de nuevo las gráficas de posición, velocidad y momento. La confirmación de que los actuadores seleccionados soportan las cargas y velocidades de ambas trayectorias valida la robustez del diseño y la coherencia del proceso de selección de componentes.

</div>