# Violencia Invisible

Landing page PWA de una sola página orientada a conversión por WhatsApp para el servicio Violencia Invisible.

Sitio publicado en GitHub Pages:

https://braianruaimi.github.io/Violencia-invisible-/

## Resumen

El proyecto presenta una experiencia visual inmersiva, mobile-first y enfocada en conversión. Toda la interfaz principal vive en un único archivo HTML con estilos y lógica inline, pensado para desplegarse de forma simple en GitHub Pages y seguir funcionando como PWA instalable.

La web está íntegramente en español y dirige la mayoría de los puntos de contacto hacia WhatsApp con mensajes predefinidos o construidos desde formulario.

## Qué incluye hoy

- Hero de portada con imagen de fondo, parallax suave y transición cinematográfica al hacer scroll.
- Barra de progreso superior y header que se compacta al avanzar por la página.
- Diseño responsive optimizado para mobile y desktop.
- Sección de servicios con llamadas directas a reserva.
- Sección Cultura y Valores con fondo visual dedicado.
- CTA y botones de WhatsApp con mensaje predeterminado.
- Formulario/modal de reserva que arma un mensaje con los datos cargados por la persona.
- Asistente de preguntas frecuentes con respuestas automáticas.
- Panel CEO oculto de forma discreta en el footer.
- Analítica local de clics a WhatsApp almacenada en localStorage.
- PWA con manifest y service worker.

## Flujos de WhatsApp

La web usa dos comportamientos distintos:

- Botones directos de WhatsApp: envían el mensaje predeterminado Hola vengo desde la web, quiero una entrevista !!
- Formulario de reserva: abre WhatsApp con el encabezado Hola Quiero una entrevista, seguido por los datos completados en el formulario.

Esto permite mantener una conversión rápida desde los CTA generales y, al mismo tiempo, conservar contexto detallado cuando la persona completa la reserva.

## Panel CEO

El panel se abre desde el punto discreto ubicado al final del footer, junto al último texto.

Datos actuales:

- Contraseña: 1234
- Persistencia: localStorage del navegador
- Alcance de analítica: local al dispositivo y navegador desde donde se generan los clics

El panel permite revisar métricas simples de clics a WhatsApp y operar sobre ese almacenamiento local.

## Formulario de reserva

El modal de reserva solicita:

- Nombre y apellido
- Email
- Número de teléfono
- Servicio seleccionado
- Resumen del caso o situación

Opciones actuales del selector:

- Guía personalizada
- Entrevista 1 a 1
- PDF + 1 a 1 conmigo
- Reserva general

La interfaz mantiene foco controlado en overlays y devuelve el foco al disparador al cerrar el modal, para mejorar accesibilidad y navegación por teclado.

## Estructura real del proyecto

Archivos principales:

- [index.html](index.html)
- [manifest.json](manifest.json)
- [service-worker.js](service-worker.js)
- [vsg.png](vsg.png)
- [fontawesome.html](fontawesome.html)

Notas de estructura:

- La implementación visual principal, estilos y JavaScript están concentrados en [index.html](index.html).
- [vsg.png](vsg.png) se usa como recurso visual de portada y fondo en secciones clave.
- [fontawesome.html](fontawesome.html) funciona como referencia mínima para la carga de Font Awesome.

## Ejecutar localmente

Al ser un sitio estático, alcanza con un servidor simple.

Ejemplo con Python:

```bash
python -m http.server 8000
```

Luego abrir:

http://localhost:8000/

También se puede usar Live Server de VS Code o cualquier servidor estático equivalente.

## Despliegue

El proyecto está preparado para GitHub Pages usando la rama main y la carpeta raíz del repositorio.

Configuración esperada:

- Source: Deploy from a branch
- Branch: main
- Folder: / (root)

## Datos del servicio

- Marca: Violencia Invisible
- WhatsApp: +54 9 2494 28 4798
- URL directa: https://wa.me/5492494284798

## Notas técnicas

- El service worker usa versionado manual de caché.
- Si una actualización visual no aparece de inmediato, conviene hacer recarga forzada o reinstalar la PWA.
- La analítica del panel no usa backend ni base de datos.
- La experiencia visual actual incorpora scroll suave, reveals por sección e interacción progresiva del hero.

## Próximas mejoras posibles

- Reemplazar la contraseña fija del panel por un mecanismo más seguro.
- Persistir reservas en backend además del envío a WhatsApp.
- Conectar analítica real con una solución externa.
- Seguir refinando la narrativa visual del scroll si se busca un efecto todavía más editorial.
