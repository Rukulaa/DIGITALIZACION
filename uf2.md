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

**Nota:** He puesto el MES como mix porque hace de puente entre la planta (PLC) y la parte de gestión (ERP). El control de accesos también lo veo así, ya que maneja algo físico (las puertas) pero va conectado a la red de la oficina.

---

## EC2.2 Departamentos IT de una empresa

*Empresa de referencia:* una pyme de software como servicio (SaaS).

| Área / Departamento | ¿Qué gestiona? | ¿Por qué es entorno IT? |
|---------------------|----------------|--------------------------|
| Desarrollo | El código y el producto | Trabaja puramente con software y datos |
| Sistemas / Infraestructura | Servidores, redes y cloud | Es la base técnica que sostiene a toda la empresa |
| Ciberseguridad | Accesos, incidentes y protección de datos | Se encarga de cuidar la información y los sistemas |
| Soporte / Helpdesk | Las incidencias de usuarios y clientes | Atiende los equipos y las aplicaciones |
| Datos / BI | Informes y análisis de datos | Trata la información de negocio |

---

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

---

## EC2.4 Qué hace que IT y OT se parezcan y se diferencien

| Aspecto | IT | OT |
|---------|----|----|
| Coincidencia 1 | Usa redes para comunicar equipos entre sí | También, y cada vez más utilizando Ethernet/IP |
| Coincidencia 2 | Necesita mantenimiento y control de accesos | Igual: hay que dar mantenimiento a los equipos y controlar quién entra |
| Coincidencia 3 | Maneja datos que hay que proteger | También maneja datos, concretamente los del proceso productivo |
| Diferencia 1 | Lo más importante es que los datos sean confidenciales | Lo más importante es que todo esté disponible y sea seguro para las personas |
| Diferencia 2 | Los equipos se renuevan cada pocos años y se actualizan con frecuencia | Los equipos duran décadas y casi nunca se pueden parar para actualizar |
| Diferencia 3 | Si falla, se pierde información o cae algún servicio | Si falla, puede haber daños en las máquinas o incluso en las personas |

---

## EC2.5 Convergencia IT-OT de una consultora IT (BIT Consultores)

**1. ¿Cuál es el entorno IT de BIT y cuál el OT que entra en casa del cliente?**  
El entorno IT de BIT son sus propias oficinas, sus servidores, la nube y las herramientas que usan los técnicos. El entorno OT que les toca ahora es el del cliente: la línea de producción, la sala de servidores y la climatización donde van a meter mano instalando sensores.

**2. ¿Qué sistema hace de puente entre los dos entornos?**  
Los sensores IoT junto con su pasarela (gateway), que son los encargados de pillar los datos de la planta y mandarlos hacia la nube.

**3. ¿Qué tecnología permite ver el estado de la línea a 500 km en tiempo real?**  
La conexión a Internet combinada con la nube y el IoT (lo que en la industria llaman IIoT).

**4. ¿Qué ventajas tiene para el cliente industrial?**  
Pues que te ahorras paradas imprevistas porque pillas los fallos antes, reduces costes en mantenimiento y en viajes, respondes más rápido y tienes datos reales para decidir mejor.

**5. ¿Qué riesgo nuevo introduce?**  
Antes la planta solía estar totalmente aislada de Internet. Al conectarla ahora, se abre la puerta a ciberataques desde fuera que podrían jorobar la producción.

---

## EC2.6 Ventajas de una digitalización de extremo a extremo (DeltaCode)

| Ámbito | Ventaja | Justificación |
|--------|---------|---------------|
| Operativo | Datos en tiempo real | El dato viaja solo desde el sensor o el MES hasta el SaaS sin pasos manuales, así que nadie tiene que meterlo a mano. |
| Cliente | Menos roturas de stock | El inventario se actualiza solo según lo que va pasando en producción. |
| Soporte | Anticiparse a los fallos | El NOC 24×7 ve las alertas y puede actuar antes de que el cliente tenga que parar la máquina. |
| Económico | Ingresos recurrentes | En vez de cobrar horas sueltas de programación, pillan una suscripción mensual fija. |
| Escalabilidad | Un producto para muchas pymes | Con el mismo SaaS sirven a todos los clientes sin tener que reprogramar desde cero para cada uno. |

---

## EC2.7 Riesgos de conectar OT a Internet (planta de packaging)

| Riesgo | Medida de mitigación |
|--------|----------------------|
| Acceso no autorizado al SCADA | Usar VPN con autenticación de doble factor (MFA) y no dejar nunca el SCADA abierto directamente a Internet. |
| Ransomware que llegue desde IT o Internet y pare la planta | Separar las redes IT y OT usando un firewall industrial y una DMZ. |
| Sistemas viejos que no se pueden parchear | Hacer un inventario de lo que hay, meterlos en su propia red aislada y aplicar parcheo virtual. |
| Cagarla con acciones erróneas o maliciosas del proveedor en remoto | Dar acceso solo de lectura por defecto, con sesiones que caduquen y queden registradas. |
| Protocolos industriales sin cifrar (como Modbus) | Usar túneles cifrados y pasarelas seguras. |
| Caída de la conexión a Internet | Configurar la planta para que pueda tirar en local si se cae la red, sin depender de estar siempre online. |