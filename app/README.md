# Proceso Bonita — RescueSync

## Proceso

- Nombre: `Gestionar Emergencia`
- Archivo: `diagrams/GestionarEmergencia-1.0.proc`
- Versión de trabajo: `1.0`

El proceso orquesta el ciclo de una emergencia: registro, revisión, lotes,
convocatoria, ofertas, validación, decisión, adjudicación, compromiso,
ejecución y cierre.

## Parámetros del proceso

Configurar por ambiente: `claveIntegracion`, `webAppUrl`, `snUrl`, `snUsuario`
y `snClave`. La clave se envía como `X-Integration-Key` a `/api/internal/*`.
No guardar secretos en conectores, URLs hardcodeadas ni archivos versionados.

## Variables del proceso

El contrato prevé `emergenciaId`, `caminoASeguir`, `todosLosLotesCubiertos`,
`duracionConvocatoria` (entero, minutos), `snToken`, `consolidado`,
`resultadoValidacion`, `compromisoConfirmado` (booleano) y
`detalleCompromiso`.

## Despliegue

Levantar PostgreSQL y la web-app, iniciar Bonita Studio, desplegar la
organización `RescueSync`, configurar los parámetros del proceso e incrementar
la versión antes de crear casos nuevos. Los casos existentes conservan la
versión con la que fueron creados.

## E5-30

- [ ] Parámetros configurados en Studio.
- [ ] Variables configuradas en Studio.
- [x] Tarea huérfana eliminada del diagrama.
- [x] README agregado.
