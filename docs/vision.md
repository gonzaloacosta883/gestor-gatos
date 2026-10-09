# Gestor de Gastos — Visión del Proyecto

## Idea

Una aplicación para registrar, organizar y analizar los gastos e ingresos
personales (o de un hogar), de forma simple y clara. El objetivo es que
cualquier persona pueda saber en qué gasta su dinero y tomar mejores
decisiones financieras sin necesidad de hojas de cálculo complejas.
## Objetivo

Construir una aplicación web con **Symfony 8.1 / PHP 8.4** que permita:

- Registrar movimientos de dinero de forma manual (gastos e ingresos).
- Sincronizar los movimientos realizados en su cuenta de mercadopago.
- Clasificar cada movimiento por categoría (comida, transporte, ocio, etc.).
- Consultar el estado financiero mediante resúmenes y reportes.
- Visualizar la evolución del gasto en el tiempo.

## Alcance inicial (MVP)

1. **Movimientos**: alta, edición, baja y listado de gastos e ingresos
   (importe, fecha, descripción, categoría).
2. **Categorías**: gestión de categorías propias para clasificar movimientos.
3. **Resúmenes**: totales por período (día, mes, año) y por categoría.
4. **Balance**: ingresos menos gastos en un período dado.

## Fuera de alcance (por ahora)

- Multiusuario con roles y permisos avanzados.
- Integración con bancos o importación automática de extractos.
- Presupuestos y alertas automáticas.
- Aplicación móvil nativa.

## Usuarios objetivo

- Personas que quieren controlar sus finanzas personales.
- Hogares que llevan un presupuesto compartido.

## Principios

- **Simplicidad**: pocas pantallas, flujos claros.
- **Datos propios**: la información del usuario le pertenece y es exportable.
- **Incremental**: entregar un MVP útil y crecer sobre él.

## Stack técnico

- Lenguaje: PHP 8.4
- Framework: Symfony 8.1
- Gestor de dependencias: Composer
- Configuración: archivos YAML en `config/`

## Métricas de éxito

- Un usuario puede registrar un gasto en menos de 10 segundos.
- Se puede ver el balance del mes actual en una sola pantalla.
- Los datos se pueden exportar en un formato estándar (CSV).
