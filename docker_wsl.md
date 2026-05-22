Docker + WSL + LDAP
Introducción

En esta actividad se implementó un entorno utilizando Docker sobre WSL (Windows Subsystem for Linux) para desplegar servicios relacionados con LDAP.
El objetivo fue crear un entorno aislado, portable y fácil de administrar mediante contenedores, permitiendo ejecutar servicios como Apache, PHP y OpenLDAP sin afectar directamente el sistema operativo principal.

Arquitectura

La arquitectura del proyecto está basada en contenedores Docker conectados mediante una red interna.

Componentes utilizados
WSL Ubuntu
Subsistema Linux utilizado sobre Windows.
Permite ejecutar Docker de manera más estable y eficiente.
Docker
Plataforma de virtualización por contenedores.
Apache + PHP
Servidor web encargado de ejecutar la aplicación.
OpenLDAP
Servicio de autenticación y directorio.
Docker Compose
Herramienta para administrar múltiples contenedores desde un solo archivo.
Diagrama de Arquitectura
┌──────────────────────┐
│      Windows         │
│                      │
│   ┌──────────────┐   │
│   │     WSL      │   │
│   │   Ubuntu     │   │
│   └──────┬───────┘   │
│          │           │
│      Docker Engine   │
│          │           │
│  ┌───────┴────────┐  │
│  │ Docker Network │  │
│  └───────┬────────┘  │
│          │           │
│   ┌──────┴──────┐    │
│   │ Apache/PHP  │    │
│   └──────┬──────┘    │
│          │           │
│   ┌──────┴──────┐    │
│   │  OpenLDAP   │    │
│   └─────────────┘    │
└──────────────────────┘
