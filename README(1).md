# DocMed

**DocMed** es un proyecto estudiantil de aplicación web orientado a la
educación y consulta informativa sobre medicamentos, síntomas y recursos
sanitarios.

> **Importante:** DocMed no diagnostica enfermedades, no prescribe
> tratamientos y no reemplaza la consulta con médicos, farmacéuticos ni
> otros profesionales de la salud.

## Funciones principales

-   Buscador de medicamentos por nombre y categoría terapéutica.
-   Buscador completo de síntomas organizado por categorías.
-   Identificación visual de síntomas considerados señales de alarma.
-   Búsqueda por voz para síntomas y medicamentos en navegadores
    compatibles.
-   Avatar humano con síntesis de voz para explicar información.
-   Información farmacológica organizada por:
    1.  Clasificación por efecto.
    2.  Qué cura o controla.
    3.  Síntomas o situaciones compatibles.
    4.  Pros y beneficios.
    5.  Contras, riesgos y efectos adversos.
-   Indicador de medicamentos que requieren indicación profesional.
-   Escáner mediante cámara o carga de imágenes para:
    -   Recetas médicas.
    -   Medicamentos, cajas y blísteres.
    -   Facturas y tickets.
-   Detección de códigos de barras o QR de medicamentos cuando el
    navegador lo permite.
-   Historial local de escaneos.
-   Directorio sanitario de la República Argentina.
-   Acceso a registros oficiales para consultar:
    -   Farmacias mediante REFAR.
    -   Clínicas, hospitales y establecimientos sanitarios mediante
        REFES.
-   Selector de idioma y arquitectura preparada para múltiples idiomas.
-   Compatibilidad con voces instaladas en el dispositivo.

## Medicamentos incluidos

La base educativa inicial contiene ejemplos de diferentes grupos
terapéuticos, entre ellos:

-   Enalapril
-   Losartán
-   Amlodipina
-   Bisoprolol
-   Aspirina (ácido acetilsalicílico)
-   Clopidogrel
-   Simvastatina
-   Atorvastatina
-   Espironolactona
-   Furosemida
-   Metformina
-   Empagliflozina
-   Dapagliflozina
-   Insulina humana
-   Insulina glargina
-   Semaglutida
-   Liraglutida
-   Tirzepatida
-   Amoxicilina
-   Azitromicina
-   Diazepam
-   Carbamazepina
-   Fluoxetina
-   Clorpromazina
-   Paracetamol
-   Ibuprofeno
-   Morfina

La base no pretende ser un vademécum completo y puede ampliarse
progresivamente.

## Síntomas

DocMed incluye un catálogo inicial de 39 síntomas relacionados con áreas
como:

-   Cardiovascular.
-   Diabetes y metabolismo.
-   Salud mental.
-   Neurología.
-   Enfermedades infecciosas.
-   Sistema respiratorio.
-   Dolor e inflamación.
-   Síntomas generales.

Los síntomas potencialmente graves se muestran como **señales de
alarma** y no deben utilizarse para generar automáticamente una
recomendación farmacológica.

## Búsqueda por voz

DocMed utiliza las capacidades de reconocimiento de voz disponibles en
el navegador.

Ejemplos:

-   "Dolor en el pecho".
-   "Fiebre".
-   "Metformina".
-   "Losartán".

La compatibilidad depende del navegador, sistema operativo, permisos del
micrófono y servicios de voz disponibles en el dispositivo.

## Avatar con voz

El avatar de DocMed utiliza síntesis de voz del navegador para leer
explicaciones sobre medicamentos y síntomas.

Para visualizar el avatar correctamente, colocar el archivo:

`docmed_avatar_humano.png`

en la misma carpeta que el archivo HTML principal.

La cantidad de idiomas y voces disponibles depende del dispositivo.

## Escáner

El módulo **Escáner DocMed** permite utilizar la cámara del teléfono o
seleccionar una imagen existente.

### Recetas

Permite fotografiar una receta y registrar manualmente información
visible como medicamento, concentración, fecha y profesional.

### Medicamentos

Permite fotografiar envases y, cuando el navegador dispone de
`BarcodeDetector`, intentar reconocer códigos de barras o QR.

### Tickets y facturas

Permite capturar comprobantes y registrar farmacia, fecha, productos,
importe y número de comprobante.

La versión actual no debe considerarse un sistema OCR médico
certificado. Una lectura automática avanzada de recetas requiere
incorporar posteriormente un motor OCR/IA y mecanismos de validación.

## Directorio sanitario argentino

DocMed incorpora las 24 jurisdicciones de la República Argentina y
permite acceder a fuentes oficiales para verificar establecimientos.

-   **REFAR:** Registro Federal de Farmacias.
-   **REFES:** Registro Federal de Establecimientos de Salud.
-   **SISA:** Sistema Integrado de Información Sanitaria Argentino.

La aplicación evita mantener como definitiva una copia estática de
farmacias o establecimientos porque las habilitaciones y datos pueden
cambiar.

## Instalación

No requiere instalación tradicional ni servidor para las funciones
básicas.

1.  Descargar el archivo principal de DocMed.
2.  Renombrarlo como `index.html` si se desea.
3.  Colocar `docmed_avatar_humano.png` en la misma carpeta.
4.  Abrir `index.html` en un navegador moderno.

Estructura recomendada:

``` text
DocMed/
├── index.html
├── docmed_avatar_humano.png
└── README.md
```

## Tecnologías

-   HTML5
-   CSS3
-   JavaScript
-   Web Speech API
-   Speech Synthesis API
-   Barcode Detection API, cuando está disponible
-   LocalStorage
-   Cámara/selector de imágenes mediante APIs del navegador

## Privacidad

La versión local de DocMed no necesita una cuenta de usuario ni una base
de datos remota para sus funciones básicas.

Los registros guardados mediante `localStorage` permanecen en el
navegador del dispositivo hasta que el usuario los elimina o borra los
datos del navegador.

No se recomienda almacenar información clínica sensible o
identificatoria en un prototipo estudiantil sin implementar previamente
medidas adecuadas de seguridad, consentimiento y protección de datos.

## Limitaciones

DocMed es un prototipo educativo. Entre sus limitaciones actuales:

-   La base farmacológica no es exhaustiva.
-   No realiza diagnóstico médico.
-   No prescribe dosis.
-   No reemplaza una receta.
-   No valida automáticamente la autenticidad de una receta.
-   La disponibilidad de reconocimiento y síntesis de voz depende del
    dispositivo.
-   La detección de códigos depende de la compatibilidad del navegador.
-   Las traducciones clínicas deben revisarse antes de utilizarse en
    contextos reales.
-   Los establecimientos sanitarios deben verificarse contra fuentes
    oficiales actualizadas.

## Próximas mejoras posibles

-   PWA instalable en Android/iOS.
-   Geolocalización voluntaria para buscar farmacias y centros cercanos.
-   Mapas y rutas.
-   OCR para recetas y tickets.
-   Reconocimiento visual de envases.
-   Base farmacológica ampliada.
-   Interacciones medicamentosas.
-   Favoritos e historial de consultas.
-   Traducciones clínicas verificadas.
-   Backend y panel administrativo.
-   Sistema de actualización de establecimientos sanitarios desde
    fuentes oficiales.

## Uso académico

DocMed fue concebido como proyecto estudiantil para demostrar la
integración de interfaces móviles, información farmacológica educativa,
reconocimiento y síntesis de voz, captura de imágenes y acceso a
recursos sanitarios.

## Aviso médico

La información proporcionada por DocMed tiene fines exclusivamente
educativos e informativos. No debe utilizarse para diagnosticar,
iniciar, modificar o suspender tratamientos.

Ante síntomas graves, persistentes o de aparición repentina, se debe
buscar atención médica profesional. Los medicamentos de prescripción
deben utilizarse únicamente bajo indicación y seguimiento de
profesionales habilitados.
