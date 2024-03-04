# Proyecto para predecir la deserción de clientes en una entidad bancaria.

El dataset contiene las siguientes variables

* customer_id: Identificador único para cada cliente. Aparentemente, no se utiliza en el análisis.

* credit_score: Puntuación de crédito del cliente. Se utiliza como entrada, posiblemente como un indicador de la salud financiera del cliente.

* country: País del cliente. Se utiliza como entrada, posiblemente para analizar patrones según la ubicación geográfica.

* gender: Género del cliente. Se utiliza como entrada, lo que podría ser relevante para analizar comportamientos según el género.

* age: Edad del cliente. Se utiliza como entrada, posiblemente para entender cómo la edad afecta el comportamiento bancario.

* tenure: Tiempo que el cliente ha estado siendo cliente del banco. Se utiliza como entrada, podría ser relevante para entender la lealtad del cliente.

* balance: Saldo en la cuenta del cliente. Se utiliza como entrada, posiblemente como un indicador de la situación financiera del cliente.

* products_number: Número de productos financieros que el cliente tiene con el banco. Se utiliza como entrada, puede indicar la relación y compromiso del cliente con el banco.

* credit_card: Indica si el cliente tiene una tarjeta de crédito (presumiblemente binario, sí/no).

* active_member: Indica si el cliente es un miembro activo (presumiblemente binario, sí/no).

* estimated_salary: Salario estimado del cliente. Se utiliza como entrada, posiblemente para entender la capacidad financiera del cliente.

* churn: Variable objetivo. Es 1 si el cliente ha abandonado el banco durante algún período y 0 si no lo ha hecho. Se utiliza para predecir la fuga de clientes.

# Resumen de métricas y conclusiones

        Modelo                             Precision    Sensibilidad  Especificidad  Pred_Positivo  Pred_Negativo      F1         AUC
      Arbol de decisión (sin balanceo)     0.8576667    0.4402619     0.9644203      0.7598870      0.8707483       0.5575130  0.7023411

      Random Forest (sin balanceo)         0.8663333    0.4877250     0.9631645      0.7720207      0.8802601       0.5977934  0.7254448

      Regresión Logística (sin balanceo)   0.8460000    0.3960720     0.9610716      0.7223881      0.8615385       0.5116279  0.6785718

      Árbol de decisión (con balanceo)     0.7476667    0.7606204     0.7350033      0.7372549      0.7585034       0.7487554  0.7478118

      Random Forest (con balanceo)         0.9200000    0.9372893     0.9030982      0.9043591      0.9364320       0.9205298  0.9201937

      Regresión Logística (con balanceo)   0.7556667    0.7559002     0.7554384      0.7513405      0.7599469       0.7536134  0.7556693

El significado de cada métrica es el siguiente:

* Precisión: Indica cuán frecuentemente las predicciones positivas del modelo son correctas.

* Sensibilidad: También conocida como Recall, es la proporción de positivos reales que se identificaron correctamente.

* Especificidad: La proporción de negativos reales que se identificaron correctamente. }

* Pred_Positivo: Es la precisión de las predicciones positivas, también conocida como el valor predictivo positivo.

* Pred_Negativo: Es la precisión de las predicciones negativas, conocido como valor predictivo negativo.

* F1: Es el promedio armónico de la precisión y la sensibilidad. Da una idea del balance entre estas dos métricas.

* AUC: Área Bajo la Curva ROC. Es una medida del rendimiento del modelo en términos de la capacidad de distinguir entre las clases.

De la tabla resumen podemos hacer las siguientes observaciones:

* El modelo de Random Forest con balanceo de datos parece tener el mejor rendimiento general, con el mayor AUC de 0.9201937, lo que indica una excelente capacidad de discriminación entre clases.

* La regresión logística sin balanceo tiene la menor sensibilidad (0.3960720), lo que indica que no es tan buena identificando la clase positiva (deserción de clientes).

* El árbol de decisión con balanceo de datos muestra una mejora considerable en sensibilidad comparado con su versión sin balanceo, lo que sugiere que el balanceo de clases ha ayudado a identificar de mejor manera la clase positiva.

* En términos de precisión, nuevamente el modelo de Random Forest con balanceo de datos sobresale con un valor de 0.9200000, indicando que las predicciones positivas son muy confiables.

* La métrica F1 es bastante balanceada para todos los modelos con balanceo dedatos, lo cual es deseable en situaciones donde se busca un equilibrio entre precisión y sensibilidad.

En resumen, si no hay restricciones específicas y se busca el mejor rendimiento en términos de obtener un equilibrio entre identificar positivos y negativos correctamente, el modelo de Random Forest con balanceo de datos es el mejor ya que tiene la más alta precisión, una excelente sensibilidad, y el AUC más alto, lo que indica que es muy bueno discriminando entre las clases; además, su valor F1 es alto, lo que sugiere un buen equilibrio entre precisión y sensibilidad.

