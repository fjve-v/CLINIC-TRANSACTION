---

# Análisis de Transacciones Clínicas y Comportamiento del Paciente

Este proyecto contiene el análisis de un conjunto de datos transaccionales de una red de clínicas. El objetivo es extraer insights sobre la eficiencia operativa, la satisfacción del cliente y la rentabilidad por servicio y canal.

## 📊 Descripción del Dataset

El archivo `sprint7_webinar22_clinic_transactions.csv` contiene registros detallados de citas médicas, perfiles de pacientes y métricas de servicio. Cada fila representa una transacción única identificada por un `transaction_id`.

### Diccionario de Datos

| Columna | Descripción | Tipo de Dato |
| --- | --- | --- |
| `transaction_id` | Identificador único de la transacción.

 | String |
| `customer_id` | Identificador único del paciente.

 | String |
| `appointment_date` | Fecha programada de la cita.

 | Date |
| `service_type` | Tipo de servicio (Especialista, Urgencias, Odontología, Laboratorio, etc.).

 | Categorical |
| `appointment_channel` | Medio por el cual se agendó la cita (Web, App, Call Center, Presencial).

 | Categorical |
| `payment_method` | Método de pago utilizado (Tarjeta, PSE, Efectivo, Débito, Transferencia).

 | Categorical |
| `amount_gross` | Valor bruto de la transacción antes de descuentos.

 | Float |
| `discount_pct` | Porcentaje de descuento aplicado.

 | Float |
| `amount_net` | Valor final pagado por el paciente.

 | Float |
| `is_refund` | Indicador binario (1 si hubo reembolso, 0 si no).

 | Boolean |
| `refund_reason` | Motivo del reembolso (ej. Duplicado, Error de facturación).

 | Categorical |
| `wait_time_min` | Tiempo de espera en minutos antes de ser atendido.

 | Float |
| `service_duration_min` | Duración de la atención médica en minutos.

 | Float |
| `satisfaction_score` | Calificación del paciente (escala 1-10).

 | Integer |
| `signup_date` | Fecha en la que el paciente se registró en el sistema.

 | Date |
| `age` / `gender` | Edad y género del paciente.

 | Integer / Categorical |
| `city` | Ciudad donde se realizó el servicio.

 | Categorical |
| `acquisition_channel` | Canal por el cual se adquirió al cliente (Organic, Paid Search, Email, etc.).

 | Categorical |
| `plan` | Tipo de plan del paciente (Básico, Plus, Premium).

 | Categorical |
| `has_insurance` | Si el paciente cuenta con seguro médico (1: Sí, 0: No).

 | Boolean |

## 🛠️ Roadmap de Análisis Propuesto


1. **Análisis de Ingresos (Revenue):**
* Calcular el Ticket Promedio por `service_type` y `plan`.
* Identificar el impacto de los reembolsos (`is_refund`) en la rentabilidad total.


2. **Eficiencia Operativa:**
* Correlación entre `wait_time_min` y `satisfaction_score`.
* Análisis de la duración del servicio por tipo de especialidad.


3. **Segmentación de Clientes (Perfilado):**
* Distribución demográfica por ciudad y edad.
* Análisis de "Churn" o recurrencia comparando `signup_date` con `appointment_date`.


4. **Efectividad de Canales:**
* Determinar qué canal de adquisición (`acquisition_channel`) trae pacientes con mayor `amount_net`.
* Preferencia de uso entre `Web` vs `App` por rango de edad.



## 📝 Notas de Calidad de Datos (Data Cleaning)

* 
**Valores Nulos:** Se observa que la columna `refund_reason` solo tiene datos cuando `is_refund` es 1.


* 
**Outliers:** Revisar los valores de `wait_time_min` (algunos registros superan los 80 minutos) y su posible impacto en la satisfacción.


* **Formatos:** Asegurar que las columnas de fecha se conviertan a formato `datetime` para análisis de series temporales.

---

*README generado para propósitos de análisis avanzado de datos clínicos.*