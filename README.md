# PUC-sistemas-recomendadores
Foro 4 del curso Modelamiento Estadístico y Sistemas Recomendadores

## Instrucciones

Considere los datos de una empresa dedicada a la venta de paquetes de viajes a destinos exclusivos en Europa. La empresa tiene información histórica de 704 clientes, a lo largo de tres países de américa latina, y le interesa realizar recomendaciones para un grupo selecto de clientes, a los cuales se desea fidelizar.

La empresa cuenta con destinos en tres ciudades: Madrid, Londres y París. De estas tres ubicaciones, Londres y París corresponden a destinos recientemente incorporados, mientras que Madrid corresponde al primer destino en la cual la empresa comenzó su operación. La empresa cuenta con cierta información personal sobre los clientes. Adicionalmente, ha registrado el motivo más usual del viaje, y si han viajado a su locación original (Madrid) en el pasado.

Recientemente, la empresa ha decidido lanzar un programa de fidelización para un grupo selecto de clientes poco activos en su plataforma web, en el cual desea plantear atractivas ofertas a los dos nuevos destinos exclusivos ubicados en las ciudades de Londres y París. Para ello, la empresa ha decidido desarrollar un sistema recomendador que le permita maximizar el interés de estos clientes en su oferta. La información de estos clientes se encuentra en el archivo “fidelización.csv”.

La empresa no sabe a priori si estos clientes tienen interés o no en los destinos. Sin embargo, tiene acceso a los registros de comportamiento web de los clientes presentes en el conjunto de datos “travel.csv”, en particular, si han cotizado o no los destinos a Londres y París.

El objetivo de este Foro consiste en construir dos sistemas recomendadores, basados en filtrado colaborativo (modelando el problema de recomendación como uno de clasificación), que le permitan a la empresa realizar recomendaciones efectivas al grupo selecto de clientes.

Las variables que se encuentran en el conjunto de datos se describen en la siguiente tabla:

|**Variable**|**Descripción**|
|:-|:---------------|
|Gender | Género (“male” o “female”).|
|Children | Indica 1 si viaja con hijos, 0 si no.|
|Country | País de residencia (Argentina, Perú o Chile).|
Motive | Indica “travel” si el motivo del viaje es turismo, y “business” si está asociado a negocios.|
|Age | Edad.|
|Madrid | Indica 1 si el año anterior viajó a madrid, 0 si no.| 
|London | Indica 1 si manifestó interés en viajar a Londres, 0 si no.|
|París | Indica 1 si manifestó interés en viajar a París, 0 si no.|

Para lograr lo anterior, desarrolle las siguientes actividades:
1. Responda y argumente en el Foro. ¿Por qué es posible interpretar el sistema recomendador deseado como un problema de clasificación binaria?
2. Cargue el conjunto de datos en la sesión de trabajo de `R` usando la función `read.table`.
3. Separe los datos en *datos.paris* y *datos.londres*. El objetivo de esta separación es desarrollar un sistema recomendador para cada destino, basado en la data de cada usuario, si aprovecharon o no la oferta a madrid el año anterior, y si manifiestan interés en viajar a la ciudad en cuestión.
4. Desarrolle un sistema recomendador que le permita determinar si debe o no ofrecer una oferta que tenga como destino la ciudad de París. Para ello:

    a. Seleccione de manera aleatoria 70% de las observaciones para crear sus datos de entrenamiento y guarde el 30% restante para objeto de validación, tal como lo hizo en el Foro 2.

    b. Entrene al menos 3 de los algoritmos de clasificación vistos en clase, que tengan como variable objetivo el interés en viajar a parís.

    c. Evalúe el desempeño de los clasificadores a través de realizar una predicción en el conjunto de prueba utilizando la métrica de exactitud, y comente en el foro qué algoritmo resulta ganador.

    d. Responda en el foro: ¿Por qué puede ser conveniente utilizar la métrica de exactitud, y no otra, desde el punto de vista de la recomendación?.

5. Repita el paso anterior para el sistema recomendador asociado a la ciudad de Londres.
6. Una vez construidos ambos sistemas recomendadores, cargue el conjunto de datos `fidelizacion.csv`, en la cual se presentan clientes pertenecientes al programa de fidelización. Para estos clientes, solamente se sabe si viajan o no a madrid el año anterior, por lo cual las columnas “london” y “paris” han sido dejadas en un valor nulo.
7. Utilizando los recomendadores, realice una recomendación hacia las ciudades de Londres y París para cada cliente.
8. En base a las recomendaciones realizadas, calcule:
    
    a. La cantidad de clientes a cuales se les recomiendan ambas ciudades.
    b. La cantidad de clientes a los cuales se les recomienda solamente Londres.
    c. La cantidad de clientes a los cuales se les recomienda solamente París.
    d. La cantidad de clientes a los cuales no se les recomienda ningún viaje.
9. En base a los cálculos del punto anterior, reflexione: ¿Qué servicio/oferta podría plantear la empresa para cada uno de los grupos anteriores?. Responda fundamentadamente en el Foro.
