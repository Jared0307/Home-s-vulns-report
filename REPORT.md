## Informe de Escaneo de Red
Introducción

Este informe detalla los resultados de un escaneo de red realizado en una red local específica. El objetivo del escaneo fue identificar los dispositivos activos en la red y analizar los servicios y puertos abiertos en esos dispositivos.
Escaneo de Dispositivos Activos.

![captura_000](https://github.com/Jared0307/Home-s-vulns-report/assets/101056540/5ff59785-f20d-4ac5-a7d7-f9c74a0604d1)

Se realizó un escaneo inicial de dispositivos activos en la red utilizando la herramienta Nmap. A continuación se muestra un resumen de los dispositivos identificados:

    192.168.100.1 (Router o Punto de Acceso)
    192.168.100.2 (Caja de Totalplay)
    192.168.100.8
    192.168.100.9
    192.168.100.15
    192.168.100.16 (Computadora Windows)
    192.168.100.23
    192.168.100.26 (Pantalla LG)

## Análisis de Servicios y Puertos Abiertos

Después de identificar los dispositivos activos, se realizó un escaneo detallado de los puertos abiertos en los dispositivos clave. 

![captura](https://github.com/Jared0307/Home-s-vulns-report/assets/101056540/c3c5d656-0ebd-40af-92c6-f415868dbb24)

A continuación se presentan las observaciones sobre los servicios y puertos abiertos en cada dispositivo relevante:

192.168.100.2 (Caja de Totalplay)

    Servicios abiertos: HTTP (puerto 80), Sun Answerbook (puerto 8888), y dos puertos desconocidos (9431/tcp, 56789/tcp).
    Sistema operativo: Sagemcom Broadband SAS

192.168.100.16 (Computadora Windows)

    Servicios abiertos: HTTP (puerto 80), msrpc (puerto 135), netbios-ssn (puerto 139), microsoft-ds (puerto 445), y otros puertos desconocidos.
    Sistema operativo: Liteon Technology

192.168.100.23

    Servicios abiertos: Una amplia variedad de puertos abiertos, incluyendo algunos comunes y otros más oscuros como fjicl-tep-a (puerto 1901/tcp) y proremote (puerto 8183/tcp).
    Sistema operativo: LG Electronics
    
## Escaneo Dedicado a Puertos Abiertos

192.168.100.2:
    
        Puerto 80/tcp: El servicio no está identificado.
        Puerto 8888/tcp: Se detecta el servicio gSOAP 2.7. Parece que hay una página web sin título y sin autorización de acceso.
        Puerto 9431/tcp: Se detecta un servicio desconocido. La cadena de huellas puede indicar un servidor web en un enrutador Sagemcom.
        Puertos 56789/tcp y 56790/tcp: Están envueltos en TCP, lo que podría significar que hay servicios ejecutándose en esos puertos, pero no se puede identificar qué servicios son.

192.168.100.15:
    
        Puerto 45093/tcp: Está filtrado, lo que indica que el puerto está bloqueado o no hay respuesta del servicio.

192.168.100.16:
    
        Puerto 80/tcp: Ejecuta Microsoft IIS httpd 10.0. El método HTTP TRACE está habilitado, lo que puede ser una vulnerabilidad si no es necesario.
        Puerto 135/tcp: Ejecuta Microsoft Windows RPC.
        Puertos 139/tcp y 445/tcp: Ejecutan servicios de NetBIOS y Microsoft Windows netbios-ssn.
        Puerto 902/tcp: Ejecuta el demonio de autenticación de VMware.
        Puerto 912/tcp: También ejecuta el demonio de autenticación de VMware.
        Puerto 5040/tcp: Desconocido.
        Puerto 5357/tcp: Ejecuta Microsoft HTTPAPI httpd 2.0.
        Puerto 49668/tcp: Ejecuta Microsoft Windows RPC.

192.168.100.23:
    
        Puerto 1313/tcp: Ejecuta UPnP y podría estar asociado con un televisor webOS.
        Puerto 1339/tcp: También ejecuta UPnP y está asociado con un televisor LG WebOS.
        Puerto 1347/tcp: UPnP asociado con un televisor LG WebOS.
        Puerto 1357/tcp: UPnP asociado con un televisor LG WebOS.
        Puerto 1389/tcp: UPnP asociado con un televisor LG WebOS.
        Puertos 1897/tcp, 1901/tcp y 2032/tcp: Ejecutan UPnP.
        Puerto 3000/tcp: Envuelto en TCP.
        Puerto 3001/tcp: Es un servicio HTTP seguro de un televisor inteligente LG, pero la validez del certificado SSL es cuestionable.
        Puerto 7000/tcp: Ejecuta AirTunes rtspd.
        Puerto 7250/tcp: Desconocido.
        Puerto 8183/tcp: Servicio no identificado.
        Puerto 18181/tcp: Servicio no identificado.
        Puerto 25454/tcp: Desconocido.
        Puerto 36866/tcp: Desconocido.
        
## Obtenciòn de CVE para Explotar
A pesar de mis esfuerzos por encontrar vulnerabilidades explotables en las direcciones identificadas como potencialmente vulnerables, no encontré ninguna vulnerabilidad significativa. Los resultados de mis análisis indican que estas direcciones pueden contar con medidas de seguridad apropiadas, aunque no absolutas.

Esto sugiere que los equipos tienen una configuración inicial sólida y han aplicado parches y actualizaciones de seguridad de manera adecuada. Sin embargo, la ausencia de vulnerabilidades identificadas no garantiza la invulnerabilidad absoluta. Para comprometer estos equipos, un atacante potencial tendría que emplear técnicas de penetración más avanzadas.

![captura_001](https://github.com/Jared0307/Home-s-vulns-report/assets/101056540/cab841b6-ea71-4511-8fa8-2b879c1949d9)


## Registro de Actividades

Este repositorio sirve como un registro completo de todas las actividades de escaneo realizadas en nuestra red. Desde la identificación de dispositivos hasta el análisis de puertos y servicios abiertos, cada detalle está documentado de manera concisa y clara para su revisión y referencia.
