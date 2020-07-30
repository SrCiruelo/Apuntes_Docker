# Arquitectura de Docker
```
╔═══════════════════════════════════════════════════════════════════════════════════╗
║                                Docker HOST( MI PC)                                ║
╠═══════════════════════════════════════════════════════════════════════════════════╣
║                                                                                   ║
║           ╔═════════════════════════════════════════════════════════╗             ║
║           ║                    Cliente (Terminal)                   ║             ║
║           ╚═════════════════════════════════════════════════════════╝             ║
║                                        ║                                          ║
║                                        ║ Cliente se comunica con el Server        ║
║                                        ║ a través la Rest API                     ║
║           ╔═════════════════════════════════════════════════════════╗             ║
║           ║                        Rest API                         ║             ║
║           ╚═════════════════════════════════════════════════════════╝             ║
║                                        ║                                          ║
║                                        ║ El Server se comunica con el Cliente     ║
║                                        ║ a través del REST API                    ║
║           ╔═════════════════════════════════════════════════════════╗             ║
║           ║             Docker Daemon - Server(Docker Service)      ║             ║
║           ╚═════════════════════════════════════════════════════════╝             ║
║                                                                                   ║
╚═══════════════════════════════════════════════════════════════════════════════════╝
```

## Qúe es una imagen Docker

Es un paquete de datos que contiene todo lo necesario para que el servicio funcione.

Un paquete se divide en capas y no hay un límite de capas.
```
╔═══════════════════════════════════════════════════════════════════════════════════╗
║                                Imagen Docker                                      ║
╠═══════════════════════════════════════════════════════════════════════════════════╣
║                                                                                   ║
║           ╔═════════════════════════════════════════════════════════╗             ║
║           ║           CAPA 3(CMD) - Comandos de inicio del proceso  ║             ║
║           ╚═════════════════════════════════════════════════════════╝             ║
║                                        ║ Es muy importante que el proceso que     ║
║                                        ║ se inicie en la CAPA 3 ocupe la consola, ║
║                                        ║ esté en primer plano si la imagen morirá ║
║           ╔═════════════════════════════════════════════════════════╗             ║
║           ║         CAPA 2(RUN) - Comandos de instalación           ║             ║
║           ╚═════════════════════════════════════════════════════════╝             ║
║                                        ║                                          ║
║                                        ║                                          ║
║                                        ║                                          ║
║           ╔═════════════════════════════════════════════════════════╗             ║
║           ║           CAPA 1(FROM) - Sistema Operativo              ║             ║
║           ╚═════════════════════════════════════════════════════════╝             ║
║                                                                                   ║
╚═══════════════════════════════════════════════════════════════════════════════════╝
ESTAS TRES PRIMERAS CAPAS SON RO( Read-Only) 
```


## Qúe es un Contenedor

Un contenedor es una capa adicional, que se encarga de la ejecución de lo que está definido
en una imagen, los contenedores no son persistentes, es decir, pueden desaparecer y la información
que poseen con ellos, por eso no es buena idea cambiar configuración en el contenedor.
```
╔═══════════════════════════════════════════════════════════════════════════════════╗
║                                 Contenedor Docker                                 ║
╠═══════════════════════════════════════════════════════════════════════════════════╣
║                                                                                   ║
║           ╔═════════════════════════════════════════════════════════╗             ║
║           ║                         Imagen                          ║             ║
║           ╚═════════════════════════════════════════════════════════╝             ║
║                                        ║                                          ║
║                                        ║                                          ║
║                                        ║                                          ║
║           ╔═════════════════════════════════════════════════════════╗             ║
║           ║                        Volúmenes                        ║             ║
║           ╚═════════════════════════════════════════════════════════╝             ║
║                                        ║ Los volúmenes son usados para            ║
║                                        ║ persistencia de datos aunque             ║
║                                        ║ el contenedor se elimine.                ║
║           ╔═════════════════════════════════════════════════════════╗             ║
║           ║                          Redes                          ║             ║
║           ╚═════════════════════════════════════════════════════════╝             ║
║                                                                                   ║
╚═══════════════════════════════════════════════════════════════════════════════════╝
SOBRE UN CONTENEDOR SE PUEDE ESCRIBIR LIBREMENTE
```
