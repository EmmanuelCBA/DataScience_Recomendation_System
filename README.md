# DataScience_Recomendation_System

Proceso:

- Dividir set en train y test. Tomar como train los datos hasta el 1 de marzo de 2021. Desde el 1ro de marzo en adelante, reservar para test.
- Desarrollar un recomendador. El recomendador debe ser capaz de generar recomendaciones para TODOS los usuarios (incluyendo los cold start que no tengan visualizaciones en el set de train). Generar 20 recomendaciones por usuario.
- Las recomendaciones tienen que ser para cada account_id y hay que recomendar content_id (NO asset_id). Pueden encontrar esto en el repositorio de la competencia.
- Los contenidos que recomienden, no tienen que haber sido vistos previamente por los usuarios (filtrar).
- Evaluarlo con MAP.


train.csv:

Este dataset contiene los registros de visualizaciones de contenidos de Flow del formato video on demand (VOD), correspondiente a una muestra aleatoria de más de 113 mil perfiles. A continuación, se detalla el diccionario de variables de esta tabla:

- customer_id: código de identificación de cada cliente de Flow (puede tener asociados uno o más account_id)
- account_id: código de identificación de cada perfil de Flow (se corresponde con un único customer_id)
- device_type: indica el tipo de dispositivo desde el que se efectuó la visualización. Las categorías posibles son:
    - CLOUD: cliente web
    - PHONE: teléfono celular
    - STATIONARY: smart TV
    - STB: set-top box, el decodificador Flow
    - TABLET
- asset_id: código de identificación de cada activo (video) disponible en la plataforma
- tunein: fecha y hora de inicio de cada visualización
- tuneout: fecha y hora de finalización de cada visualización
- resume: variable dummy que indica si se reanuda un consumo anterior del mismo asset_id


metadata.csv:

Contiene la metadata asociada a cada uno de los contenidos. Las variables incluidas son:

- asset_id: código de identificación de cada activo (video) disponible en Flow
- content_id: código de identificación que agrupa los distintos asset_id asociados a un mismo contenido (por ejemplo, cada 
 episodio de una misma serie tiene su propio asset_id, mientras que la serie se identifica con un content_id único)
- title: título
- reduced_title: título reducido
- episode_title: título del episodio (válido para contenidos episódicos, como las series)
- show_type: tipo de show - las categorías son autorreferenciales con excepción de “Rolling”, que indica que se trata de  una serie incompleta, y “Web”, la cual remite a contenidos pensados íntegramente en formato digital (series web) -
- released_year: año de lanzamiento
- country_of_origin: país de origen – expresado con el código de dos letras propio del estándar internacional de normalización ISO 3166 -
- category: categoría o género al que pertenece el contenido - puede haber una o más -
- keywords: palabras clave o tags asociadas al contenido - puede haber una o más -
- description: descripción (sinopsis)
- reduced_desc: descripción (sinopsis) reducida
- cast_first_name: nombre y apellido de los actores y actrices principales
- credits_first_name: nombre y apellido del director o directora
- run_time_min: duración total, expresada en minutos
- audience: audiencia target
- made_for_tv: variable dummy que indica si el contenido fue hecho para TV
- close_caption: variable dummy que indica si el contenido posee subtítulos
- sex_rating: variable dummy que indica si el contenido tiene escenas de sexo explícitas
- violence_rating: variable dummy que indica si el contenido tiene escenas de violencia explícitas
- language_rating: variable dummy que indica si el contenido posee lenguaje que puede ser considerado ofensivo o inapropiado
- dialog_rating: variable dummy que indica si el contenido posee diálogos que pueden ser considerado ofensivos o inapropiados
- fv_rating: variable dummy que indica si el contenido tiene rating de FV, que corresponde a público infantil con violencia ficticia
- pay_per_view: variable dummy que indica si se trata de un alquiler
- pack_premium_1: variable dummy que indica si se trata de un contenido exclusivo del pack premium 1
- pack_premium_2: variable dummy que indica si se trata de un contenido exclusivo del pack premium 2
- create_date: fecha de creación del activo
- modify_date: fecha de modificación del activo
- start_vod_date: fecha desde la cual el activo se encuentra disponible en la plataforma
- end_vod_date: fecha de finalización de la disponibilidad del activo en la plataforma
