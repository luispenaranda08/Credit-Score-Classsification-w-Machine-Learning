# 1. PROYECTO FINAL. CREDIT SCORE CLASSIFICATION

**Desarrollado por:**  
Johan Díaz  
Héctor Sanjuan  
Miguel Lugo  
Luis David Peñaranda

## 1. Contexto

Antes de comenzar con el análisis exploratorio, es necesario conocer el contexto en el que vamos a trabajar, para así poder entender las variables que vamos a utilizar y qué queremos predecir.

El dataset utilizado para este proyecto reposa en `Kaggle` y puede acceder a el mediante el siguiente enlace: https://www.kaggle.com/datasets/parisrohan/credit-score-classification

### 1.1 Puntuación crediticia

Una compañía financiera global ha recolectado durante años detalles bancarios de sus clientes e información crediticia de los mismos. La gestión de la empresa quiere crear un sistema que clasifique a las personas en diferentes grupos de puntaje crediticio: Bueno, Normal y Malo. Todo esto con el fin de reducir el trabajo manual que conlleva esta clasificación.


### 1.2 Variables disponibles

En esta sección brindaremos un diccionario de las variables con las que contamos para realizar la clasificación:

- ID: Identificador único de cada entrada del dataset.

- Customer_ID: Identificador para cada cliente.

- Month: Mes en que se recolectó la información.

- Name: Nombre del cliente.

- Age: Edad del cliente.

- SSN: Número de seguridad social del cliente.

- Occupation: Ocupación del cliente.

- Annual_Income: Ingreso anual del cliente.

- Monthly_Inhand_Salary: Salario mensual luego de impuestos.

- Num_Bank_Accounts: Número de cuentas bancarias que posee el cliente.

- Num_Credit_Card: Número de tarjetas de crédito que posee el cliente.

- Interest_Rate: Tasa de interés aplicada en los créditos.

- Num_of_Loan: Número de créditos que tiene el cliente.

- Type_of_Loan: Tipos de créditos que tiene el cliente.

- Delay_from_due_date: Número de días de retraso desde el vencimiento del plazo de pago de los créditos.

- Num_of_Delayed_Payment: Numéro de pagos retrasados hechos por el cliente.

- Changed_Credit_Limit: Indica, si lo ha hecho, cuanto ha cambiado el límite del crédito.

- Num_Credit_Inquiries: Número de veces que el cliente ha solicitado un crédito.

- Credit_Mix: Mezcla del tipo de productos de crédito que posee el cliente.

- Outstanding_Debt: Monto de la deuda pendiente.

- Credit_Utilization_Ratio: Tasa de utilización del crédito.

- Credit_History_Age: Edad crediticia del cliente.

- Payment_of_Min_Amount: Indica si se alcanzó el monto mínimo de pago.

- Total_EMI_per_month: Cuota mensual equivalente pagada por el cliente.

- Amount_invested_monthly: Monto mensual invertido por el cliente.

- Payment_Behaviour: Comportamiento de pago del cliente.

- Monthly_Balance: Saldo mensual en la cuenta del cliente.

- Credit_Score: Variable objetivo, clasificación de la puntuación crediticia.


### Objetivo

El objetivo de este proyecto es la implementación de distintos modelos clásicos de Machine Learning con el fin de encontrar el que mejores clasificaciones de puntuación crediticia entregue para ofrecerlo a la empresa.

### Tabla de contenido

```{tableofcontents}
```