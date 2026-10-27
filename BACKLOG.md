# Backlog e historias de usuario – MediKare

Cada historia está vinculada a los requerimientos levantados en los Issues de GitHub (RF, RNF y RD). Ver `README.md`.

## Paso a paso: de los requerimientos al backlog

1. **Levantar requerimientos** (RF-01 a RF-10, RNF-01 a RNF-04, RD-01 a RD-03).
2. **Identificar actores:** *Médico* (registra síntomas y cierra la factura), *Operador/Administrador* (gestiona clientes, planes y respaldo) y *Cliente*.
3. **Agrupar en épicas** los requerimientos relacionados.
4. **Escribir historias de usuario:** *Como [actor], quiero [acción], para [beneficio]*.
5. **Definir criterios de aceptación** para cada historia.
6. **Priorizar con MoSCoW** y estimar con puntos de historia.
7. **Ordenar en sprints.**
8. **Publicar en GitHub:** cada historia es un *Issue* con etiquetas (`historia-usuario`, prioridad, sprint, épica), y se organiza en un tablero *Projects* (Backlog → En progreso → Revisión → Hecho). El script `crear_backlog_github.sh` lo hace automáticamente.

## Épicas

| Épica | Contenido |
|-------|-----------|
| E1 Gestión de clientes | Registro e historial |
| E2 Planes y facturación | Plan, usuarios, valor mensual, descuento |
| E3 Persistencia | Respaldo, entorno, privacidad |
| E4 Operación continua | Ciclo del menú, parada, cierre de sesión, validaciones |

## Tablero resumen

| Historia | Título | Requerimiento | Prioridad | Puntos | Sprint |
|----------|--------|---------------|-----------|--------|--------|
| HU-01 | Registrar cliente | RF-01 | Must | 3 | 1 |
| HU-02 | Seleccionar tipo de plan | RF-02 | Must | 2 | 1 |
| HU-03 | Registrar otros usuarios | RF-03 | Must | 2 | 1 |
| HU-07 | Ciclo continuo del menú | RF-09 | Must | 2 | 1 |
| HU-10 | Cierre de sesión | RF-08 | Must | 1 | 1 |
| HU-04 | Calcular valor mensual | RF-04, RD-01 | Must | 3 | 2 |
| HU-05 | Aplicar descuento por gripa o alergia | RF-06 | Must | 3 | 2 |
| HU-06 | Protocolo de parada inmediata (medicamento) | RF-10 | Must | 3 | 2 |
| HU-11 | Entradas sin distinguir mayúsculas o minúsculas | RNF-02 | Should | 2 | 2 |
| HU-12 | Control de pasos y seguridad de los datos | RNF-03 | Should | 2 | 2 |
| HU-08 | Historial de clientes | RF-07, RD-02 | Should | 2 | 3 |
| HU-09 | Respaldo TXT seguro | RF-05, RNF-01 | Should | 3 | 3 |
| HU-13 | Funcionamiento en cualquier entorno | RNF-04 | Should | 2 | 3 |
| HU-14 | Privacidad de los datos personales | RD-03 | Must | 2 | 3 |

## Historias de usuario

### HU-01 Registrar cliente
**Épica:** E1 Gestión de clientes · **Prioridad:** Must · **Puntos:** 3 · **Sprint:** 1 · **Requerimiento:** RF-01

**Como** operador, **quiero** registrar nombre, cédula, dirección de residencia y síntomas del cliente, **para** crear su ficha de atención.

**Criterios de aceptación**
- [ ] Al elegir la opción 1 el sistema pide nombre, cédula, dirección y síntomas.
- [ ] Los síntomas se ingresan uno por uno.

### HU-02 Seleccionar tipo de plan
**Épica:** E2 Planes y facturación · **Prioridad:** Must · **Puntos:** 2 · **Sprint:** 1 · **Requerimiento:** RF-02

**Como** operador, **quiero** elegir el plan con las siglas PB o PP, **para** definir la tarifa del cliente.

**Criterios de aceptación**
- [ ] Si la sigla no es PB ni PP, el sistema la rechaza y la vuelve a pedir.

### HU-03 Registrar otros usuarios
**Épica:** E2 Planes y facturación · **Prioridad:** Must · **Puntos:** 2 · **Sprint:** 1 · **Requerimiento:** RF-03

**Como** operador, **quiero** indicar cuántas personas cubre el plan (número entero), **para** calcular el costo total.

**Criterios de aceptación**
- [ ] Un valor no entero o menor que 1 es rechazado.

### HU-04 Calcular valor mensual
**Épica:** E2 Planes y facturación · **Prioridad:** Must · **Puntos:** 3 · **Sprint:** 2 · **Requerimiento:** RF-04, RD-01

**Como** operador, **quiero** que el sistema calcule tipo de plan × otros usuarios, **para** conocer lo que paga el cliente respetando los precios fijos.

**Criterios de aceptación**
- [ ] PB (275.325) con 2 usuarios = 550.650 COP.
- [ ] PP (325.650) con 2 usuarios = 651.300 COP.
- [ ] Los precios no se pueden modificar durante la ejecución.

### HU-05 Aplicar descuento por gripa o alergia
**Épica:** E2 Planes y facturación · **Prioridad:** Must · **Puntos:** 3 · **Sprint:** 2 · **Requerimiento:** RF-06

**Como** operador, **quiero** aplicar 12,5 % de descuento si el síntoma es gripa o alergia en ambos planes, **para** beneficiar a esos clientes.

**Criterios de aceptación**
- [ ] PB con 2 usuarios y gripa = 481.819 COP (550.650 × 0,875).
- [ ] Sin gripa ni alergia no se aplica descuento.
- [ ] El descuento no se aplica dos veces.

### HU-06 Protocolo de parada inmediata (medicamento)
**Épica:** E4 Operación continua · **Prioridad:** Must · **Puntos:** 3 · **Sprint:** 2 · **Requerimiento:** RF-10

**Como** médico, **quiero** escribir la palabra "medicamento" para terminar la factura, **para** cerrar la atención del cliente.

**Criterios de aceptación**
- [ ] Escribir "medicamento" cierra la factura.
- [ ] La opción 1 siguiente abre un cliente nuevo.

### HU-07 Ciclo continuo del menú
**Épica:** E4 Operación continua · **Prioridad:** Must · **Puntos:** 2 · **Sprint:** 1 · **Requerimiento:** RF-09

**Como** operador, **quiero** que el menú se repita, **para** registrar varios clientes sin reiniciar el programa.

**Criterios de aceptación**
- [ ] El menú reaparece después de cada opción hasta elegir salir.

### HU-08 Historial de clientes
**Épica:** E1 Gestión de clientes · **Prioridad:** Should · **Puntos:** 2 · **Sprint:** 3 · **Requerimiento:** RF-07, RD-02

**Como** operador, **quiero** ver la información de todos los clientes registrados, **para** consultar el historial sin perder pacientes anteriores.

**Criterios de aceptación**
- [ ] La opción 7 muestra todos los clientes de la sesión.
- [ ] Registrar un cliente nuevo no borra los anteriores.

### HU-09 Respaldo TXT seguro
**Épica:** E3 Persistencia · **Prioridad:** Should · **Puntos:** 3 · **Sprint:** 3 · **Requerimiento:** RF-05, RNF-01

**Como** administrador, **quiero** guardar los datos en un archivo TXT en la computadora, **para** no perder la información.

**Criterios de aceptación**
- [ ] La opción 5 crea respaldo_clientes.txt con todos los clientes.
- [ ] Si falla el guardado se muestra un mensaje sin cerrar el programa.

### HU-10 Cierre de sesión
**Épica:** E4 Operación continua · **Prioridad:** Must · **Puntos:** 1 · **Sprint:** 1 · **Requerimiento:** RF-08

**Como** operador, **quiero** una opción para salir, **para** terminar el programa de forma ordenada.

**Criterios de aceptación**
- [ ] La opción 8 termina el ciclo y muestra un mensaje de despedida.

### HU-11 Entradas sin distinguir mayúsculas o minúsculas
**Épica:** E4 Operación continua · **Prioridad:** Should · **Puntos:** 2 · **Sprint:** 2 · **Requerimiento:** RNF-02

**Como** operador, **quiero** que "pb", "PB", "Medicamento" o "GRIPA" funcionen igual, **para** evitar errores por la forma de escribir.

**Criterios de aceptación**
- [ ] El plan y la palabra de parada se reconocen en cualquier combinación.
- [ ] El descuento detecta gripa o alergia sin importar el formato.

### HU-12 Control de pasos y seguridad de los datos
**Épica:** E4 Operación continua · **Prioridad:** Should · **Puntos:** 2 · **Sprint:** 2 · **Requerimiento:** RNF-03

**Como** operador, **quiero** que el sistema valide el orden de los pasos y los datos ingresados, **para** evitar facturas incorrectas.

**Criterios de aceptación**
- [ ] No se calcula el valor sin plan y usuarios definidos.
- [ ] No se aplica descuento sin valor mensual.
- [ ] Las entradas inválidas no detienen el programa.

### HU-13 Funcionamiento en cualquier entorno
**Épica:** E3 Persistencia · **Prioridad:** Should · **Puntos:** 2 · **Sprint:** 3 · **Requerimiento:** RNF-04

**Como** usuario, **quiero** que el programa funcione en Windows, Linux o macOS con Java instalado, **para** ejecutarlo en cualquier computadora.

**Criterios de aceptación**
- [ ] Compila con javac y corre con java sin dependencias externas.

### HU-14 Privacidad de los datos personales
**Épica:** E3 Persistencia · **Prioridad:** Must · **Puntos:** 2 · **Sprint:** 3 · **Requerimiento:** RD-03

**Como** cliente, **quiero** que mis datos personales estén protegidos, **para** confiar en el servicio.

**Criterios de aceptación**
- [ ] Los datos solo se guardan en el respaldo local.
- [ ] El archivo de respaldo no se sube a GitHub (.gitignore).

## Sprints

| Sprint | Historias | Objetivo |
|--------|-----------|----------|
| 1 | HU-01, HU-02, HU-03, HU-07, HU-10 | Menú base y registro |
| 2 | HU-04, HU-05, HU-06, HU-11, HU-12 | Facturación y reglas |
| 3 | HU-08, HU-09, HU-13, HU-14 | Historial, respaldo, privacidad, documentación y video |

## Mejoras futuras (Could)

- Base de datos en lugar de TXT.
- Leer el respaldo al iniciar el programa.
- Interfaz gráfica o web.
