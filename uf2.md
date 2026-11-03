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

El MES y el control de accesos los he puesto como mix porque conectan la parte física con la red y la gestión de la empresa.

## EC2.2 Departamentos IT de una empresa

Empresa de referencia: una empresa de software SaaS.

| Área / Departamento | ¿Qué gestiona? | ¿Por qué es entorno IT? |
|---------------------|----------------|--------------------------|
| Desarrollo | Programa y mantiene el software | Todo su trabajo es con software y datos |
| Sistemas | Servidores, redes y nube | Mantiene los equipos informáticos de la empresa |
| Ciberseguridad | Accesos y protección de datos | Protege la información de la empresa |
| Soporte | Problemas de usuarios y clientes | Ayuda con equipos y programas |
| Datos / BI | Informes y análisis | Trabaja con los datos del negocio |

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
| Coincidencia 1 | Usa redes para conectar equipos | También usa redes, cada vez más parecidas a las de IT |
| Coincidencia 2 | Hay que mantener los equipos | También hay que mantener las máquinas y los sistemas |
| Coincidencia 3 | Maneja datos importantes | También, sobre todo datos de la producción |
| Diferencia 1 | Lo más importante es proteger los datos | Lo más importante es que no se pare y que sea seguro para las personas |
| Diferencia 2 | Los equipos se cambian y se actualizan a menudo | Las máquinas duran muchos años y no se pueden parar fácilmente para actualizarlas |
| Diferencia 3 | Un fallo puede perder datos o dejar un servicio sin funcionar | Un fallo puede romper máquinas o ser peligroso para las personas |

## EC2.5 Convergencia IT-OT de una consultora IT (BIT Consultores)

**1. ¿Cuál es el entorno IT de BIT? ¿Y cuál es el entorno OT que ahora entra en casa del cliente?**
El IT de BIT son sus oficinas, sus servidores, la plataforma en la nube y los ordenadores de los técnicos. El OT es el del cliente: la línea de producción, la sala de servidores y la climatización, que es donde se ponen los sensores.

**2. ¿Qué sistema hace de puente entre los dos entornos?**
Los sensores IoT y la pasarela (gateway) que manda sus datos a la nube.

**3. ¿Qué tecnología permite ver la línea de producción a 500 km?**
Internet junto con la nube y el IoT.

**4. ¿Qué ventajas tiene para el cliente industrial?**
Hay menos paradas porque los fallos se ven antes, se gasta menos en mantenimiento y en viajes, se responde más rápido y se pueden tomar mejores decisiones con los datos.

**5. ¿Qué riesgo nuevo introduce?**
Antes la planta no estaba conectada a Internet y ahora sí, así que puede recibir ciberataques desde fuera.

## EC2.6 Ventajas de una digitalización de extremo a extremo (DeltaCode)

| Ámbito | Ventaja | Justificación |
|--------|---------|---------------|
| Operativo | Datos en tiempo real | Los datos pasan del sensor al SaaS sin que nadie tenga que meterlos a mano. |
| Cliente | Menos faltas de stock | El inventario se actualiza solo con lo que pasa en producción. |
| Soporte | Se evitan averías | El NOC vigila las 24 horas y avisa de los problemas antes de que paren la producción. |
| Económico | Ingresos fijos | Cobran una suscripción mensual en vez de horas sueltas. |
| Escalabilidad | Un producto para muchas pymes | El mismo SaaS sirve para todos los clientes sin programar de nuevo. |

## EC2.7 Riesgos de conectar OT a Internet (planta de packaging)

| Riesgo | Medida de mitigación |
|--------|----------------------|
| Acceso sin permiso al SCADA | Usar VPN con contraseña y doble verificación, y no dejarlo abierto a Internet |
| Virus o ransomware desde la red de la oficina | Separar la red de la planta de la de la oficina con un firewall |
| Equipos viejos que no se pueden actualizar | Ponerlos en una red aparte y vigilarlos |
| Errores del proveedor cuando se conecta | Que solo pueda mirar y no cambiar nada, con acceso temporal y un registro de lo que hace |
| Datos que viajan sin cifrar | Enviarlos por un canal cifrado, como una VPN |
| Se cae Internet | Que la planta pueda seguir funcionando sola, sin depender de la conexión |
