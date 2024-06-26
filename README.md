# docs-condominio

# Indice
[Casos de Uso](#casos-de-uso)

Flujo Servicio Personalizado
- [CU16: Gestionar Solicitud de Servicio Personalizado](#cu16-gestionar-solicitud-de-servicio-personalizado)
- [CU17: Gestionar y Responder a Solicitudes de Servicio Personalizado](#cu17-gestionar-y-responder-a-solicitudes-de-servicio-personalizado)
- [CU18: Gestionar Respuesta Solicitud de Servicio Personalizado](#cu18-gestionar-respuesta-solicitud-de-servicio-personalizado)

# Casos de Uso

## CU16: Gestionar Solicitud de Servicio Personalizado

**Tipo de Caso de uso:** Primario

**Actores:** Habitante y Cohabitante (primario), Proveedor (secundario)

**Precondicion:** El habitante ya inicio sesion.

**Resumen**: El habitante selecciona la categoría de servicio que desea recibir y proporciona una breve descripción del servicio personalizado que desea, junto con la prioridad de su solicitud (Alta, Media, Baja), la fecha y la hora de preferencia para la visita del proveedor, y adjunta fotos relevantes. A continuación, el habitante envía esta solicitud al Pool de Servicio Personalizado, donde los proveedores de la comunidad pueden revisarla e inspeccionarla. El sistema envia confirmacion de que se creo y se envio la solicitud de servicio personalizado.

**Poscondicion:** La solicitud de servicio personalizado se envio con exito y espera una respuesta de algun proveedor perteneciente a la comunidad de proveedores.

**Caminos Alternativos:**
1.  **Modificar Servicio Personalizado Solicitado:** El habitante modifica el servicio personalizado. El sistema reflejara esta modificacion en el pool de servicio personalizado.
2. **Eliminar Servicio Personalizado Solicitado:** El habitante cancela la solicitud de servicio personalizado. El sistema retira el servicio personalizado creado.

3. **Descripcion Incompleta:** Si el habitante no proporciona una descripción completa del servicio deseado, el sistema puede solicitar más detalles antes de permitir que continúe con la solicitud.

### Diagrama de Caso de Uso
![Use Case Diagram 16](./docs/out/usecases/CU16/UCD16/UCD16.png)

### Diagrama de Secuencia
![Secuence Diagram](./docs/out/usecases/CU16/SD16/SD16.png)

### Diagrama de Colaboracion
![Colaboration Diagram](./docs/out/usecases/CU16/CD16/CD16.png)

### CO01: Modificar Servicio Personalizado
- **Operacion:** modificarServicioPersonalizado()
- **Referencia cruzadas:** CU Gestionar Solicitud de Servicio Personalizado
- **Precondicion:** El habitante ya inicio sesion y tiene creado al menos un Servicio Personalizado en el Pool que selecciono para modificar.
- **Postcondicion:**   El sistema reflejara esta modificacion en el pool de servicio personalizado. 
#### Diagrama de Secuencia
![Secuence Diagram](./docs/out/usecases/CU16/CO01/SD/SD.png)


#### Diagrama de Colaboracion
![Colaboration Diagram](./docs/out/usecases/CU16/CO01/CD/CD.png)


### CO2: Eliminar Servicio Personalizado
- **Operacion:** eliminarServicioPersonalizado()
- **Referencia cruzadas:** CU Gestionar Solicitud de Servicio Personalizado
- **Precondicion:** El usuario tiene al menos un servicio personalizado en el pool de servicios personalizado que selecciono para eliminar.
- **Postcondicion:**  El sistema retira el servicio personalizado creado.    

#### Diagrama de Secuencia
![Secuence Diagram](./docs/out/usecases/CU16/CO02/SD/SD.png)


#### Diagrama de Colaboracion
![Colaboration Diagram](./docs/out/usecases/CU16/CO02/CD/CD.png)

## CU17: Gestionar y Responder a Solicitudes de Servicio Personalizado
**Actores:** Proveedor (p), Habitante y Cohabitante (s), Administrador de Condominio (s).

**Precondicion:** El proveedor ya ingreso sesion e ingreso al Pool de Servicios Personalizados

**Resumen**: El proveedor revisa las solicitudes de servicio personalizado enviadas por usuarios asociados a condominios. El proveedor puede visualizar los detalles de cada servicio personalizado, incluyendo nombre, descripción, fecha de inicio, hora de inicio y fotos adjuntas. Posteriormente, el proveedor selecciona el servicio deseado y agrega un precio preferencial, para luego enviar la respuesta al solicitante.

**Poscondicion:** El sistema envia una respuesta confirmando de que se envio correctamente y retira la solicitud del pool de servicio personalizado. 

**Caminos Alternativos:**
1.  **El servicio ya no esta:** El proveedor intenta responder a solucitud pero, el sistema envia notificacion de que el servicio personalizado fue eliminado o ya fue seleccionado por otro proveedor.
2. **Ver respuestas:** El proveedor puede ver todas sus respuestas a todos los servicios personalizados. 
3. **Eliminar respuesta:** El proveedor decide eliminar su respuesta y el sistema retira su respuesta, confirmando con una notificacion.
4. **Modificar respuesta:** El proveedor decide modificar su respuesta y el sistema notifica de que se modifico exitosamente. 

### Diagrama de Caso de Uso
![Use Case Diagram](./docs/out/usecases/CU17/UCD17/UCD17.png)

### Diagrama de Secuencia
![Secuence Diagram](./docs/out/usecases/CU17/SD17/SD17.png)

### Diagrama de Colaboracion
![Colaboration Diagram](./docs/out/usecases/CU17/CD17/CD17.png)


### CO1: Modificar respuesta a solicitud de servicio personalizado
- **Operacion:** modificarRespuestaSolicitudDeServicioPersonalizado()
- **Referencia cruzadas:** CU17 Gestionar y Responder a Solicitudes de Servicio Personalizado
- **Precondicion:** El proveedor selecciona la respuesta que desee modificar.
- **Postcondicion:** El sistema notifica de que se modifico exitosamente

#### Diagrama de Secuencia
![Secuence Diagram](./docs/out/usecases/CU17/CO01/SD/SD.png)


#### Diagrama de Colaboracion
![Colaboration Diagram](./docs/out/usecases/CU17/CO01/CD/CD.png)


### CO2: Eliminar respuesta a solicitud de servicio personalizado
- **Operacion:** elimianarRespuestaSolicitudDeServicioPersonalizado()
- **Referencia cruzadas:** CU17 Gestionar y Responder a Solicitudes de Servicio Personalizado
- **Precondicion:** El proveedor selecciona la respuesta que desee elimianr.
- **Postcondicion:** El sistema notifica de que se elimino exitosamente



#### Diagrama de Secuencia
![Secuence Diagram](./docs/out/usecases/CU17/CO02/SD/SD.png)


#### Diagrama de Colaboracion
![Colaboration Diagram](./docs/out/usecases/CU17/CO02/CD/CD.png)


## CU18: Gestionar Respuesta Solicitud de Servicio Personalizado
**Actores:** Habitante (p), Administridor de Condominio (p), Proveedor (s)

**Precondicion:** El habitante ha creado su solicitud de servicio personalizado y uno o varios proveedores de la comunidad han respondido a la solicitud.

**Resumen:** El habitante o administrador del condominio accede a la lista de respuestas de sus solicitudes de servicio personalizado y evalúa cuál ofrece la mejor combinación entre calidad y precio. Pueden seleccionar entre descartar o aceptar una respuesta según sus preferencias.

**Poscondicion:** El habitante acepta y todas las respuestas de la solicitud son removidas exeptuando la aceptada, ademas de retirar la solicitud de pool de servicios personalizados. El proveedor que realizo la respuesta es notificado.

**Caminos Alternativos:**
1.  **Cancelar agendado:** El solicitante decide cancelar el servicio. El sistema notifica al proveedor.
2. **Respuesta inexistente:** La respuesta fue elimina. El sistema notifica al solicitante de ello. 
3. **Ver detalla de respuesta:** El solicitante puede ver mas detalla sobre la respuesta.


### Diagrama de Caso de Uso
![Use Case Diagram](./docs/out/usecases/CU18/UCD18/UCD18.png)

### Diagrama de Secuencia
![Secuence Diagram](./docs/out/usecases/CU18/SD18/SD18.png)

### Diagrama de Colaboracion
![Colaboration Diagram](./docs/out/usecases/CU18/CD18-1/CD18-1.png)

![Colaboration Diagram](./docs/out/usecases/CU18/CU18-2/CU18-2.png)

# Modelo de Dominio
![domain model](./docs/out/domain-model/domain-model/domain-model.png)

# Diagrama de Clases de Diseño

![Design Class](./docs/out/design-class/design-class/design-class.png)

# Diagrama de Paquetes