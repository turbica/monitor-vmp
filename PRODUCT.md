# Monitor de Seguridad de Movilidad Personal (VMP) y Accesibilidad Intermunicipal: visión de producto

## Concepto

Mapa vivo de puntos negros de siniestralidad de patinetes y bicicletas. Observatorio vivo alimentado por flujos de datos automatizados, no un estudio estático.

## Problemática social

Auditar los puntos negros de accidentalidad de patinetes y bicicletas cruzando los indicadores locales de siniestralidad con las discontinuidades del carril bici, los desperfectos reportados en la calzada y los datos de movilidad metropolitana y provincial.

## Frecuencia de actualización

**Mensual / continua**

## Funcionamiento

- Sincronización vía API CKAN municipal: Avisos (n.º 11), Callejero (n.º 18) y Carril bici (n.º 19).
- Consumo de capas vectoriales (GeoJSON, KMZ, PBF) del Geoportal: vías de circulación y red ciclista.
- Indicadores Agenda 2030: 11.2.EL10 (accidentes con VMP por tipo) y 3.6.EL04 (accidentes con muertes).
- Aprovechamiento de la red IoT LPWAN y del marco analítico Python/JS de Connecta València (Diputación).

## Impacto esperado

Mapa vivo de puntos negros de siniestralidad de patinetes y bicicletas correlacionado con discontinuidades del carril bici y avisos de desperfectos viales no resueltos, para orientar la inversión pública en infraestructura segura.

## Por qué es viable a largo plazo

Los premios municipales ya cubren bicis y calles 30, pero nadie cruza de forma recurrente la siniestralidad VMP con infraestructura y avisos. Ojo: es el más cercano al nicho saturado de movilidad, conviene diferenciarse por el enfoque de seguridad y la escala intermunicipal.

## Fuentes de datos

Configuración programática en `config/fuentes.json`:

```json
{
  "valencia_ckan_portal": "https://opendata.vlci.valencia.es/",
  "geoportal_vias_y_redes": "https://geoportal.valencia.es/apps/GeoportalHome/es/inicio/geodatos-abiertos",
  "nodo_iot_telefonica_valencia": "https://opendata-valencia.iotplatform.telefonica.com/dataset/?organization=ajuntament-de-valencia",
  "indicadores_agenda_2030": [
    "11.2.EL10 - Proporción de accidentes de tráfico con intervención de VMP (bicicletas, patinetes, etc.) desglosado por tipo",
    "3.6.EL04 - Proporción de accidentes con muertes por lesiones"
  ],
  "datasets_municipales_femp80": [
    "Nº 11 - Avisos de incidencias en la vía pública",
    "Nº 18 - Callejero",
    "Nº 19 - Carril bici"
  ],
  "ecosistema_provincial_y_alianzas": {
    "connecta_valencia_dival": "https://turisme.dival.es/la-diputacio-destina-5-millones-de-euros-al-proyecto-connecta-valencia-para-analizar-los-datos-turisticos-en-toda-la-provincia/",
    "upv_las_naves_soberania_datos": "https://dadesvalencia.webs.upv.es/proyectos/"
  }
}
```

## Gobernanza

- Si un dataset clave llega con retraso o poca desagregación, solicitarlo por los canales formales (Ayuntamiento, Oficina de Estadística, mecanismo participativo de Dades Obertes GVA, Ley 1/2022) y llevar un registro público de esas solicitudes dentro de la plataforma.
- Alianzas en cuádruple hélice con Las Naves y el grupo de datos de la UPV; vincular el proyecto a la Misión Climática València 2030.
- Cuando haya prototipo, presentarlo a los Premios de Datos Abiertos y Periodismo de Datos del Ayuntamiento y a los encuentros de innovación de la Diputación y Red.es.
