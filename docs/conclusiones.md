---
layout: default
title: Conclusiones
nav_order: 6
---


# Conclusiones

## Dificultades encontradas

Durante la fase de diseño y planificación, los mayores retos han sido:

- **Modelado de datos:** Definir la estructura correcta para las tablas intermedias (`USUARIO_JUEGO`), ya que unificar reseñas, puntuaciones y estados en una sola relación requirió varias iteraciones.
- **Definición del alcance:** Acotar las funcionalidades para el MVP (producto viable mínimo) y dejar fuera ideas complejas como un sistema de amigos.
- **Integración de APIs de terceros:** Gestionar los límites de peticiones (rate limiting) de la API de videojuegos y mapear sus estructuras de datos JSON al esquema de base de datos relacional.
- **Configuración del entorno:** Ajustar los permisos de PHP-FPM y Nginx para permitir la subida de imágenes de perfil (avatares) de forma segura.

## Aprendizajes

Este proyecto ha permitido consolidar conocimientos en:

- **Diseño Relacional:** Normalización de bases de datos para evitar redundancia.
- **Flujo de trabajo Git:** Uso de ramas y _commits_ atómicos para mantener un historial limpio.
- **Documentación como código:** Uso de Markdown para generar documentación técnica profesional y mantenible.
- **Administración de Sistemas:** Configuración básica de un stack LEMP y gestión de despliegues estáticos en GitHub Pages.

## Posibles mejoras futuras

Para siguientes versiones de **LogNow!**, se plantean las siguientes evoluciones:

1. **Social Login:** Permitir acceso con cuentas de Google o Steam.
2. **Sistema de Amigos:** Implementar interacciones sociales, muros de actividad y comparativas de bibliotecas.
3. **App Móvil:** Desarrollo de una aplicación nativa para móviles que consuma la misma base de datos.
