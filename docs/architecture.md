# Contratos y generación

Este repositorio mantiene modelos, procedencia y generación. Cada SDK nativo tiene código, pruebas, credenciales y releases propios. Los modelos generados y el corpus verificado se conservan dentro del SDK para evitar dependencias de runtime o de pruebas sobre carpetas hermanas.

El generador recibe un lenguaje y un directorio de salida. Solo escribe la proyección seleccionada. Las referencias comunes se fijan mediante commits completos y SHA-256; una actualización es un cambio revisable, no una operación al instalar o invocar el SDK.

Go y Python implementan HTTP, OAuth y lectura de respuestas de forma independiente, usando el mismo corpus. No hay motor de ejecución compartido. RENIEC es provisional y solo dispone de un proveedor sintético. La emisión fiscal permanece fuera del alcance actual.

Las versiones de los SDKs no deben coincidir entre sí; cada una registra qué contratos y corpus utiliza. La publicación de modelos tampoco publica SDKs automáticamente.
