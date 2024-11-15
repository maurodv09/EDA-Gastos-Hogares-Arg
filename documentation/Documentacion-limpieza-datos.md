### Selección de características
Se selecciónan las columnas que se usaran para este projecto:
-  Identificación: `id` `provincia`
-  Composición de los hogares: `cantmiem` `cantping` `reldep`
-  Ingresos y Gastos totales y per capita: `ingtoth` `ingpch` `gastot` `gastotpc`
-  Tipos de gatos: `gc_01` `gc_02` `gc_03` `gc_04` `gc_05` `gc_06` `gc_07` `gc_08` `gc_09` `gc_10` `gc_11` `gc_12`
-  Formas de pago: `fp_contado` `fp_credito` `fp_especie` `fp_prodprop` `fp_tarjetas` `fp_otras` `fp_indef`.
### Valores Faltantes
- `reldep`(17): Surgen de valores en `cantping` iguales a 0. Se eliminaron estos registros.
- `pf_indef`:(2) Estos registros contenian unicamente valores nulos para todas sus columnas por lo que se eliminaron.

### Integridad de datos

**Provincia**
- No se encontraron errores en los códigos de provincia.

**Miembros**
- No hubo registros con 0 miembros.
- No hubo registros cuya cantidad de miembros (`cantmiem`) sea menor que la cantidad de personas que perciben ingresos (`cantping`).
- No hubo errores en el cálculo de la relación de dependencia (`reldel`) = `cantmiem` / `cantping`.

### Ingresos
- No hubo registros con ingresos igual a 0.
- No hubo errores en el calculo de ingreso per cápita (`ingpc`) = (`ingtoth`) / (`cantmiem`).

### Gastos
- unicamente la categoria `g7` contenía valores negativos (208 - menor al 1%). Estos registros fueron eliminados
- No hubo errores en la sumatoria de tipos de gastos.
- No hubo errores en el calculo de gasto per cápita (`gastopc`) = (`gastot`) / (`cantmiem`).

### Formas de pago
- Se detectó un alto número de errores e inconsistencias en el cálculo de las formas de pago, por lo que se se dicidió prescindir de estas columnas para este análisis