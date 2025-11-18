# Prueba-ténica-en-POWER-BI
https://www.youtube.com/watch?v=h_OqFvhmwoE

PRUEBA TÉCNICA DE TRABAJO EN POWER BI

PARTE 1 MODELADO

* Establecer relaciones entre las tablas
  
* Establecer una tabla calendario
  
  Calendario = CALENDAR(MIN(Ventas[Fecha]), MAX(Ventas[Fecha]))
  Año = YEAR([Date])
  Mes = FORMAT([Date], "mmmm")
  MesNo = MONTH([Date])

* Calcular el Costo Total para cada venta(Cantidad Vendida * Costo de Producto)
  
  Costo = RELATED(Productos[Costo])  >  me trae  la columna  de otra tabla
  Costo total = [Cantidad Vendida]*[Costo]
  
* Calcular el Ingreso Total(Cantidad Vendida * Precio Unitario)
  Ingreso total = [Cantidad Vendida]*[Precio Unitario]


PARTE 2 ANÁLISIS Y VISUALIZACIÓN DE DATOS : DASHBOARDS INTERACTIVO

* Ventas totales por región
* Ventas por producto
* Segmento de cliente: distribución de ventas por segmento de clientes

* Top 3 productos mas vendidos: usa una medida para mostrar los 3 productos con mayores ingresos
  Top3 =
IF(RANKX(ALL(Productos),[Ventas t], ) <= 3, [Ventas t], BLANK())

* Crear medida Promedio de Ventas por cliente
  Promedio de ventas por cliente = AVERAGEX(ALL(Clientes),[Ventas t])
  
* Crear una etiqueta donde nos muestre la venta total, solo de cliente PREMIUM

* Filtro dinámico: agrega un filro que permita seleccionar el segmento de cliente y ver como afectan las ventas , los ingresos y la rentabilidad
* Análisis temporal: visualización usando gráfico de líneas: que muestre la tendencia de ventas por mes
* Slicers y Filtros: slicers para filtrar por Fecha, Producto, Región y Segmento de cliente.

* Estética y diseño: mejorar la apariencia del dashboard, usa colores y formatos para resaltar la información importante



