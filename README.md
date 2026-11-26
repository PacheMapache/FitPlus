# FitPlus

**Versión documentada: 1.0.0**  
**Tipo de aplicación:** biblioteca web estática de ejercicios y generador de rutinas por intervalos  
**Idioma principal de la interfaz:** español

FitPlus permite explorar ejercicios, consultar instrucciones y generar una rutina diaria enfocada en un grupo muscular. Está preparado para abrirse directamente en un navegador moderno: no requiere instalación de paquetes, un servidor de aplicación ni una cuenta.

## Funcionalidades

### Biblioteca de ejercicios

- Incluye 1.324 ejercicios con imágenes y animaciones locales.
- Busca por nombre y por términos de categoría, equipamiento y músculo objetivo; algunos nombres originales de ejercicios permanecen en inglés.
- Filtra por categoría corporal, equipamiento y músculo objetivo. Los valores de esos filtros se presentan traducidos al español.
- Abre una ficha con imagen animada, metadatos musculares, equipo necesario e instrucciones.
- Muestra primero las instrucciones en español. Cuando hay traducciones disponibles, permite consultar otros idiomas.
- Carga los ejercicios en una cuadrícula con desplazamiento progresivo.

### Selector de rutinas HIIT

Desde **Rutina HIIT del día**, el usuario elige un grupo muscular y un nivel. El selector ofrece ocho opciones: pecho, espalda, hombros, brazos, antebrazos, muslos y glúteos, pantorrillas y abdomen.

- Genera cuatro ejercicios de la biblioteca para el grupo seleccionado.
- Cambia la selección según la fecha y permite pedir otra variación del día.
- Presenta miniaturas, equipo e indicaciones en español para cada ejercicio.
- Incluye dos niveles: inicial, con intervalos de 20 segundos de actividad y 40 de recuperación; e intermedio, con 30 segundos de actividad y 30 de recuperación.
- Sugiere dos rondas, repeticiones controladas, una pausa entre rondas, esfuerzo percibido y duración estimada.
- Incluye pautas para calentar y volver a la calma, respirar, mantener una postura controlada, alternar grupos musculares y reconocer cuándo detenerse.
- Enlaza las fuentes de actividad física y seguridad consultadas desde el propio panel.

Los intervalos son una propuesta general de entrenamiento, no una prescripción clínica. Se aconseja alternar grupos musculares y no realizar trabajo intenso del mismo grupo en días consecutivos. Personas con lesiones, condiciones médicas, embarazo o dudas sobre su estado físico deben consultar a un profesional antes de empezar.

### Guía para desarrolladores

`setup.html` incluye una guía de integración que permite:

- Crear una tabla para SQL Server, PostgreSQL, MySQL o SQLite.
- Generar en el navegador un archivo SQL con los registros de ejercicios.
- Consultar ejemplos de integración de API en cURL, JavaScript, Python, C#, Java, PHP y Go.
- Revisar una plantilla de solicitud para crear una API con asistentes de IA.
- Ver cómo organizar las carpetas de imágenes y animaciones en un servidor o CDN.

La generación del archivo SQL se realiza en el navegador y no carga los datos a un servidor.

## Cómo abrir FitPlus

1. Extrae el contenido de `FitPlus.zip` en una carpeta.
2. Abre `index.html` en un navegador moderno.
3. Usa los filtros para encontrar ejercicios o selecciona **Rutina HIIT del día** para generar una sesión.
4. Abre **Configurar base de datos** para consultar la guía técnica.

Las páginas y los recursos de ejercicios se sirven desde los archivos incluidos. Se necesita conexión a internet únicamente para abrir los enlaces externos de referencias o servicios que se configuren en los ejemplos de API.

## Estructura del proyecto

```text
FitPlus/
├── index.html                  Aplicación principal y generador de rutinas
├── setup.html                  Guía de base de datos e integración de API
├── README.md                   Descripción, uso y registro de versiones
├── brand/
│   └── logo-fitplus.png        Logo y favicon de FitPlus
├── data/
│   ├── exercises.json          Datos de ejercicios
│   └── exercises.schema.json   Esquema de validación de los datos
├── images/                     1.324 miniaturas de ejercicios
├── videos/                     1.324 animaciones de ejercicios
├── LICENSE                     Licencia del código y datos indicados
└── NOTICE.md                   Atribución y condiciones de los medios
```

La página principal contiene los datos necesarios para ejecutarse como archivo local; `data/exercises.json` se distribuye también para integraciones. Al actualizar el catálogo, mantén sincronizados ambos conjuntos. La selección de ejercicios para rutinas usa identificadores definidos en `index.html`; comprueba que sigan existiendo en los datos.

## Datos y atribuciones

Cada registro puede incluir nombre, categoría, parte del cuerpo, equipamiento, músculo objetivo, grupo muscular, instrucciones en varios idiomas, miniatura, animación y otros metadatos.

Consulta [LICENSE](LICENSE) y [NOTICE.md](NOTICE.md) antes de reutilizar el contenido. La licencia MIT descrita en esos archivos no concede derechos sobre las imágenes ni las animaciones: los medios pertenecen a Gym visual y están sujetos a sus condiciones y atribución. El logo de FitPlus es un recurso de marca proporcionado para este proyecto.

## Versionamiento y mantenimiento del README

El historial sigue el formato **SemVer** (`MAJOR.MINOR.PATCH`):

- **MAJOR:** cambios incompatibles en la experiencia o estructura de datos.
- **MINOR:** nuevas funcionalidades compatibles.
- **PATCH:** correcciones, ajustes de contenido y mejoras pequeñas compatibles.

En cada actualización del proyecto, modifica este README junto con el cambio: actualiza la versión, añade una entrada fechada al principio del historial y resume lo añadido, cambiado, corregido o eliminado. Conserva las entradas anteriores y documenta las consideraciones de compatibilidad cuando apliquen. No registres una función hasta que esté incluida en el proyecto.

### Historial de versiones

#### 1.0.0 — 2026-11-25

- Establece la primera versión documentada de FitPlus.
- Reúne la biblioteca web en español, el catálogo de 1.324 ejercicios y las instrucciones multilingües.
- Incluye el selector de rutinas por grupo muscular con variación diaria, intervalos y consejos de seguridad.
- Incorpora la marca FitPlus, su logo y favicon, y la guía de integración con bases de datos y API.
- Añade esta guía y las reglas para mantener versiones futuras.
