# T02 — Ejercicios de clase

## EC2.1 ¿IT u OT?

| # | Sistema | IT | OT | Mix |
|---|---------|:--:|:--:|:---:|
| 1 | Servidor de correo corporativo (Microsoft 365) | X | | |
| 2 | SCADA de una planta química (válvulas y sensores) | | X | |
| 3 | ERP en la nube (pedidos y facturación) | X | | |
| 4 | PLC de una cadena de montaje | | X | |
| 5 | Plataforma de tickets de soporte (Jira, Zendesk) | X | | |
| 6 | Sistema MES (conecta el PLC con el ERP) | | | X |
| 7 | Software de copias de seguridad de servidores | X | | |
| 8 | Control de accesos de un edificio (tarjetas) | | | X |

**Nota:** el MES lo puse como mix porque hace de puente entre la planta (PLC) y la parte de gestión (ERP). El control de accesos también, porque controla algo físico (las puertas) pero funciona conectado a la red de la empresa.

## EC2.2 Departamentos IT de una empresa

Empresa de referencia: una empresa mediana de software como servicio (SaaS).

| Área / Departamento | ¿Qué gestiona? | ¿Por qué es entorno IT? |
|---------------------|----------------|--------------------------|
| Desarrollo | El código y el producto | Trabaja con software y datos |
| Sistemas / Infraestructura | Servidores, redes y cloud | Es la base técnica de toda la empresa |
| Ciberseguridad | Accesos, incidentes y protección de datos | Protege la información y los sistemas |
| Soporte / Helpdesk | Las incidencias de usuarios y clientes | Atiende equipos y aplicaciones |
| Datos / BI | Informes y análisis de datos | Trata datos de negocio |

## EC2.3 Tecnología de negocio vs. de planta

| Tecnología | Negocio | Planta |
|------------|:-------:|:------:|
| ERP (SAP, Oracle, etc.) | X | |
| SCADA / HMI | | X |
| CRM (Salesforce, HubSpot) | X | |
| MES (Manufacturing Execution System) | | X |
| E-commerce (PrestaShop, Shopify) | X | |
| PLC / PAC | | X |
| BI / Data Warehouse | X | |
| Robots colaborativos (cobots) | | X |

## EC2.4 Qué hace que IT y OT se parezcan y se diferencien

| Aspecto | IT | OT |
|---------|----|----|
| Coincidencia 1 | Usa redes para comunicar equipos entre sí | También, y cada vez más con Ethernet/IP |
| Coincidencia 2 | Necesita mantenimiento y control de quién accede | Igual: hay que mantener los equipos y controlar accesos |
| Coincidencia 3 | Maneja datos que hay que proteger | También maneja datos (los del proceso productivo) |
| Diferencia 1 | Lo más importante es la confidencialidad de los datos | Lo más importante es que todo esté disponible y sea seguro para las personas |
| Diferencia 2 | Los equipos se renuevan cada pocos años y se actualizan a menudo | Los equipos duran décadas y casi nunca se pueden parar para actualizar |
| Diferencia 3 | Si falla, se pierde información o un servicio | Si falla, puede dañar máquinas o incluso a personas |

## EC2.5 Convergencia IT-OT de una consultora IT (BIT Consultores)

**1. ¿Cuál es el entorno IT de BIT y cuál el OT que entra en casa del cliente?**
El entorno IT de BIT son sus oficinas, sus servidores, la plataforma en la nube y las herramientas de sus técnicos. El entorno OT que ahora entra es el del cliente: la línea de producción, la sala de servidores y la climatización donde instalan los sensores.

**2. ¿Qué sistema hace de puente entre los dos entornos?**
Los sensores IoT junto con su pasarela (gateway), que recogen los datos de la planta y los mandan a la plataforma en la nube.

**3. ¿Qué tecnología permite ver el estado de la línea a 500 km en tiempo real?**
La conectividad a Internet combinada con la nube y el IoT (en industria se le llama IIoT).

**4. ¿Qué ventajas tiene para el cliente industrial?**
Se evitan paradas imprevistas porque se detectan los problemas antes, se ahorra en mantenimiento y desplazamientos, se reacciona más rápido y se tienen datos para tomar mejores decisiones.

**5. ¿Qué riesgo nuevo introduce?**
Antes la planta solía estar aislada de Internet. Ahora está conectada, así que aparece el riesgo de ciberataques desde fuera que podrían afectar a la producción.

## EC2.6 Ventajas de una digitalización de extremo a extremo (DeltaCode)

| Ámbito | Ventaja | Justificación |
|--------|---------|---------------|
| Operativo | Datos en tiempo real | El dato va del sensor o del MES al SaaS sin pasos manuales, así que no hay que introducirlo a mano. |
| Cliente | Menos roturas de stock | El inventario se actualiza solo según lo que pasa en producción. |
| Soporte | Anticiparse a los fallos | El NOC 24×7 ve las alertas y puede actuar antes de que el cliente tenga que parar. |
| Económico | Ingresos recurrentes | Cobran una suscripción mensual en vez de vender horas sueltas de programación. |
| Escalabilidad | Un producto para muchas pymes | El mismo SaaS sirve a todos los clientes sin reprogramar para cada uno. |

## EC2.7 Riesgos de conectar OT a Internet (planta de packaging)

| Riesgo | Medida de mitigación |
|--------|----------------------|
| Acceso no autorizado al SCADA | Usar VPN con autenticación multifactor y no exponer nunca el SCADA directamente a Internet |
| Ransomware que llegue desde IT o Internet y pare la planta | Segmentar las redes IT y OT con un firewall industrial y una DMZ |
| Sistemas viejos que no se pueden parchear | Hacer un inventario de equipos, aislarlos en su propia red y aplicar parcheo virtual |
| Acciones erróneas o maliciosas del proveedor en remoto | Dar acceso de solo lectura por defecto, con sesiones temporales y auditadas |
| Protocolos industriales sin cifrado (por ejemplo Modbus) | Usar túneles cifrados y gateways seguros |
| Caída de la conexión a Internet | Que la planta pueda seguir funcionando en modo local, sin depender de la conexión |
