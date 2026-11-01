# Mesa Norte | IA Automation
Proyecto final de Carolina Machado, comisión 102385.

Mesa Norte convierte una idea editorial y sus fuentes vinculadas en un borrador. Claude propone el texto y una persona decide si autoriza el envío. Gmail entrega la versión aprobada al buzón del laboratorio. Airtable conserva el estado y el comprobante.

## Reproducir el circuito
Importar workflow.json en n8n. En Configuracion de laboratorio indicar la base académica y el buzón propio de revisión y entrega. Asignar credenciales de Airtable, Anthropic, Gmail y autenticación del webhook. Usar una idea nueva con conocimiento vinculado. El disparador recibe un objeto con ideaRecordId.

## Pruebas observadas
| Caso | Resultado |
|---|---|
| Entrada sin ideaRecordId | ENTRADA_INVALIDA |
| Idea ya procesada | IDEA_YA_PROCESADA |
| Idea sin fuente vinculada | SIN_CONOCIMIENTO |
| Ejecución inicial 622662 | Error de expresión y credencial de registro pendiente |
| Reservas | Borrador aprobado y enviado al buzón de prueba. Cierre Correcta en la ejecución 624691 |
| Ensayo integral | Llegó a la espera de aprobación |

Reservas se verificó por etapas después de corregir expresiones. Se observaron 636 tokens de entrada y 170 de salida. Gmail y Airtable registraron el mismo identificador de hilo, terminado en 855e. Las pruebas usaron datos fijados en el disparador de n8n.

## Comparación de costos
Dos resultados de procesamiento por lotes consumieron 1.015 tokens de entrada y 388 de salida en total. Aplicando las tarifas usadas en el ensayo a ese mismo volumen, el equivalente estándar fue USD 0,00029550 y la estimación por lotes USD 0,00014775. El ahorro estimado del 50 % corresponde a la generación por lotes. La validación, el control de versión y el registro se resuelven sin llamadas al modelo.
