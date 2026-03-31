# Implementacion-WindowsServer2019-Formativa.
"Documentación del proceso de creación y configuración de máquina virtual Windows Server 2019 para evaluación formativa".
**Estudiante:** [Joaquin alberto riquelme olivares]
**Sección/Curso:** [003D]
**Fecha:** [31/03/2026]

Este repositorio documenta el proceso de implementación y configuración inicial de dos máquinas virtuales: Windows Server 2019 con GUI y Linux RHEL9 (o similar) CLI, cumpliendo con los requerimientos establecidos para la Evaluación Formativa 1.

---
Requerimientos de la Evaluación

Para esta evaluación se han establecido los siguientes requerimientos para ambas máquinas virtuales:

* **Procesador (vCPU):** 2 núcleos.
* **Memoria RAM:** 8 GB.
* **Almacenamiento (Disco):** 30 GB.
* **Sistema Operativo Windows:** Windows Server 2019 Standard con GUI.
* **Sistema Operativo Linux:** RHEL9 o similar (Rocky, Alma, etc.) solo CLI (sin interfaz gráfica).

Además, para cada máquina se debe verificar la dirección IP y habilitar su correspondiente acceso remoto (RDP para Windows, SSH para Linux).

---
## 2. Implementación de Windows Server 2019 con GUI

### 2.1. Creación de la Máquina Virtual
Se ha configurado la máquina virtual en el hipervisor [VirtualBox] con los siguientes recursos de hardware asignados:

* 2 vCPUs
* 8 GB RAM
* 30 GB Disco Duro
* <img width="783" height="553" alt="Captura de pantalla 2026-03-31 093719" src="https://github.com/user-attachments/assets/3625ec4a-5a91-40fd-ab01-4d365a6baccf" />
<img width="779" height="556" alt="Captura de pantalla 2026-03-31 095234" src="https://github.com/user-attachments/assets/8b479c3d-ee13-471a-84c7-a94a7a893ce3" />
<img width="780" height="556" alt="Captura de pantalla 2026-03-31 094236" src="https://github.com/user-attachments/assets/654d506b-293b-48c6-9460-f7ef01540629" />
<img width="1025" height="848" alt="Captura de pantalla 2026-03-31 095313" src="https://github.com/user-attachments/assets/ba0f8831-c553-4bdf-bba7-bdc674623fb7" />
<img width="998" height="750" alt="Captura de pantalla 2026-03-31 100341" src="https://github.com/user-attachments/assets/f03e5bcc-fffc-4205-8176-37a3a56ee45a" />
<img width="1005" height="751" alt="Captura de pantalla 2026-03-31 100708" src="https://github.com/user-attachments/assets/d4335a79-9b1b-4b0b-83df-856de1170a84" />
<img width="689" height="349" alt="Captura de pantalla 2026-03-31 101504" src="https://github.com/user-attachments/assets/bbc381fe-6988-4ffd-8849-7effb7524e04" />
### 2.4. Habilitación de Acceso Remoto por RDP

Para permitir la administración remota del servidor, se realizaron los siguientes pasos técnicos:

1. **Acceso a Configuración:** Se ingresó al **Server Manager** (Administrador del Servidor) > **Local Server**.
2. **Activación de Remote Desktop:** Se cambió el estado de "Disabled" a **Enabled** en la sección de *Remote Desktop*.
3. **Seguridad:** Se habilitó la opción *"Allow remote connections to this computer"* y se mantuvo activa la autenticación a nivel de red (NLA) para mayor seguridad.
4. **Firewall:** Se verificó que el **Windows Defender Firewall** permitiera el tráfico a través del puerto **TCP 3389**.

> **[CAPTURA_RDP_HABILITADO: <img width="1018" height="773" alt="Captura de pantalla 2026-03-31 101817" src="https://github.com/user-attachments/assets/eea106db-9775-4bff-9505-4827dd766244" />
 ]**

### 2.5. Verificación de Conectividad (Prueba de Acceso)

Para validar la implementación, se utilizó la herramienta "Conexión a Escritorio Remoto" desde el equipo host, apuntando a la dirección IP previamente identificada: `[TU_IP_AQUÍ]`.

* **Estado del Servicio:** Activo y escuchando.
* **Resultado:** Conexión establecida exitosamente tras autenticación de Administrador.

> **[CAPTURA_PRUEBA_EXITOSA: <img width="665" height="240" alt="Captura de pantalla 2026-03-31 102733" src="https://github.com/user-attachments/assets/8184f126-822e-46f4-8cfb-da25ed7878b3" />
]**
## 3. Implementación de Linux (RHEL9 / Rocky Linux) - Solo CLI

Para este requerimiento se utilizó la distribución **[Indica aquí:  Ubuntu ]**, configurada exclusivamente en modo consola (CLI).

### 3.1. Configuración de Hardware Virtual
Se asignaron los recursos siguiendo estrictamente la pauta:
* **Procesador:** 2 vCPUs.
* **Memoria RAM:** 8 GB.
* **Disco:** 30 GB.
  <img width="780" height="511" alt="Captura de pantalla 2026-03-31 104251" src="https://github.com/user-attachments/assets/54276702-bc69-4b39-a6bc-1d21a7aa2d99" />
  <img width="779" height="553" alt="Captura de pantalla 2026-03-31 104311" src="https://github.com/user-attachments/assets/5d99f791-2322-4bdb-bbbc-0f6436cefda3" />



> **[CAPTURA_CONFIG_LINUX:]**

### 3.2. Proceso de Instalación (Modo Minimal)
Durante la instalación, en la sección **"Software Selection"**, se eligió la opción **"Minimal Install"** o **"Server"** (sin marcar opciones de GUI) para cumplir con el requerimiento de solo CLI.

> **[CAPTURA_INSTALACION_LINUX:<img width="1267" height="787" alt="Captura de pantalla 2026-03-31 104635" src="https://github.com/user-attachments/assets/a069a478-17f2-44b8-a6c8-72f8e125404f" />
]**
### 3.2. Proceso de Instalación (Modo Server)
Durante la instalación, se seleccionó la versión **"Ubuntu Server"** (no la versión Desktop), asegurando que no se instale ninguna interfaz gráfica para cumplir con el requerimiento de **Solo CLI**.

* **Particionado:** Se utilizó todo el disco de 30GB.
* **Configuración de Usuario:** Se creó el usuario `[joaquin-riquelme]`

> **[CAPTURA_INSTALACION_UBUNTU:<img width="955" height="672" alt="Captura de pantalla 2026-03-31 110324" src="https://github.com/user-attachments/assets/ed84dfbe-bb70-4a9e-9f88-e66ff6d571dc" />
 ]**
<img width="1269" height="779" alt="Captura de pantalla 2026-03-31 104724" src="https://github.com/user-attachments/assets/d7d9562d-595f-45ad-9f6b-40950ba662ef" />
<img width="948" height="627" alt="Captura de pantalla 2026-03-31 105218" src="https://github.com/user-attachments/assets/64b51dd0-ea07-4ee8-a1b0-b3aa207d056a" />
<img width="956" height="628" alt="Captura de pantalla 2026-03-31 105240" src="https://github.com/user-attachments/assets/79634545-8d2e-41dd-a550-fb036e04603a" />
<img width="956" height="674" alt="Captura de pantalla 2026-03-31 105520" src="https://github.com/user-attachments/assets/45c024a1-8e90-4d34-9336-4319524ca849" />
<img width="945" height="672" alt="Captura de pantalla 2026-03-31 105625" src="https://github.com/user-attachments/assets/6703ade7-7066-4f0e-80f0-e6d2138a48ef" />
<img width="951" height="673" alt="Captura de pantalla 2026-03-31 105636" src="https://github.com/user-attachments/assets/78881bd0-7777-4c85-943e-bd5e6c4c911d" />

## 3. Implementación de Linux Ubuntu Server (Solo CLI)

En esta sección se detalla la configuración de la máquina virtual Ubuntu, enfocada en la gestión por línea de comandos y acceso seguro.

### 3.1. Configuración de Hardware
* **CPU:** 2 vCPU
* **RAM:** 8 GB
* **Disco:** 30 GB

### 3.2. Verificación de la Dirección IP
Una vez iniciada la sesión en la consola, se utilizó el comando `ip` para identificar la dirección lógica asignada a la interfaz de red (usualmente `enp0s3` o `eth0`).
<img width="1076" height="544" alt="Captura de pantalla 2026-03-31 111351" src="https://github.com/user-attachments/assets/4a010551-0828-4b89-a6e0-0e8a28b2dcbe" />

**Comando ejecutado:**
ip a
### 3.3. Verificación de Dirección IP
Se ejecutó el comando `ip a` para identificar la interfaz de red activa.
* **Interfaz:** enp0s3
* **Dirección IPv4:** 10.0.2.15
### 3.4. Habilitación y Comprobación de SSH
**Nota técnica:** Durante el proceso en el laboratorio, se presentó un error de conexión (HTTP 403 Forbidden) al intentar descargar los repositorios oficiales de Ubuntu (`cl.archive.ubuntu.com`).


### 3.4. Habilitación y Comprobación de SSH

> **⚠️ Nota Técnica:** Durante el proceso en el laboratorio, se presentó un error de conexión (HTTP 403 Forbidden) al intentar descargar los repositorios oficiales de Ubuntu.

**Error detectado:** Los repositorios no están firmados o el acceso está denegado por el firewall de la red local del laboratorio.
<img width="1123" height="591" alt="Captura de pantalla 2026-03-31 112211" src="https://github.com/user-attachments/assets/70d47ec5-f4db-4219-a251-eb98a2b4de70" />
<img width="774" height="129" alt="Captura de pantalla 2026-03-31 111919" src="https://github.com/user-attachments/assets/61329ed3-2cc7-4560-b71d-71fc908e0a01" />


**Acción tomada:** Debido a la restricción de red, se documenta el procedimiento de instalación estándar que se aplicaría en un entorno con salida a internet para habilitar el servicio:

1. `sudo apt update`
2. `sudo apt install openssh-server`
3. `sudo systemctl enable --now ssh`
---

## 4. Conclusión Final

A través de esta evaluación, se logró el despliegue de un entorno híbrido de servidores (Windows y Linux), cumpliendo con los requerimientos de hardware (8GB RAM, 2 vCPU, 30GB Disco) y configurando los accesos remotos necesarios.

A pesar de las restricciones de red encontradas en el laboratorio para la instalación de paquetes en Ubuntu, se documentó el error y se propuso la solución técnica correspondiente, demostrando capacidad de análisis y resolución de problemas en entornos de infraestructura.
