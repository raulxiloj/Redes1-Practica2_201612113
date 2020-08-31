# Redes 1 - Practica 2

El proposito de esta practica es configurar y administrar los dispositivos de una red pequeña y desarrollar una capacidad de analisis y diseño de topologias de red.
Se deben configurar dispositivos de una empresa que tiene operando 6 máquinas las cuales están distribuidas de la siguiente manera:


<p align="center">
<img src="https://user-images.githubusercontent.com/30850990/91695667-bd48b000-eb2b-11ea-9d45-9b9074308841.png" height="120px"/>
</p>

## Topologia

La topologia consta de 1 Router, 2 switches, 5 VPCS y 1 maquina virtual. Toda la informacion se detalla en el enunciado de la practica

<p align="center">
    <img src="https://user-images.githubusercontent.com/30850990/91695017-bf5e3f00-eb2a-11ea-8dbd-54784c4fb202.JPG" height="450px">
</p>

## Configuracion

Para proceder a configurar las vpcs y el router, los iniciamos y damos doble click sobre su icono, esto nos abrira una consola (PuTTY) que ya viene instalada en GNS3.

Comandos a utilizar para configurar las VPCs:

* Para configurar la ip <br/>
  ``` ip <dir_ip> <mask> <gateway> ```
* Para ver la configuracion y cercionarnos que la ip fue asignada <br/>
  ``` sh ip ```
* Para guardar los cambios y que no se borren cuando se apague la maquina <br/> 
 ``` save ```                

### **PC1**

Ingresar la ip que se desea asignar a la VPC: <br/>
``` ip 192.168.12.11 255.255.255.192 192.168.12.1 ```
<p>
    <img src="https://user-images.githubusercontent.com/30850990/91694934-963dae80-eb2a-11ea-9f3b-416e4235fbf2.JPG" width="400px">
</p>

Verificar que la configuracion fue realizada exitosamente: <br/>
 ``` sh ip ```
<p>
    <img src="https://user-images.githubusercontent.com/30850990/91694936-976edb80-eb2a-11ea-908f-a5259aa6a181.JPG" width="400px">
</p>

Guardar: <br/>
``` save ```
<p>
    <img src="https://user-images.githubusercontent.com/30850990/91694939-98077200-eb2a-11ea-86f9-d640fb13f706.JPG" width="400px">
</p>

Procederemos a hacer lo mismo con las siguientes VPCS

### **PC2**
<br/>
<p>
    <img src="https://user-images.githubusercontent.com/30850990/91697077-c044a000-eb2d-11ea-880b-266231826402.JPG" width="400px">
</p>


### **PC3**
<br/>
<p>
    <img src="https://user-images.githubusercontent.com/30850990/91697081-c175cd00-eb2d-11ea-9faa-a59b34ee15ed.JPG" width="400px">
</p>

### **PC4**
<br/>
<p>
    <img src="https://user-images.githubusercontent.com/30850990/91697086-c2a6fa00-eb2d-11ea-9b06-fa5ebf8dcb39.JPG" width="400px">
</p>

### **PC5**
<br/>
<p>
    <img src="https://user-images.githubusercontent.com/30850990/91697088-c3d82700-eb2d-11ea-96c9-3e4fe39ca8ec.JPG" width="400px">
</p>

### **VM**
Para la maquina virtual el proceso es un poco diferente pero nada complicado, cuando la encendamos tendremos la siguiente interfaz:

<p>
    <img src="https://user-images.githubusercontent.com/30850990/90328966-fbf03f00-df5d-11ea-9956-e8bbc7f60f37.JPG" width="400px" >
</p>

En el menu de abajo buscaremos el panel de control

<p>
    <img src="https://user-images.githubusercontent.com/30850990/90329446-2f34cd00-df62-11ea-9051-d9fe8782c9a3.JPG" width="400px" >
</p>

Presionaremos la opcion de 'Network'
<p>
    <img src="https://user-images.githubusercontent.com/30850990/90329460-52f81300-df62-11ea-947c-6d78e7576e52.JPG" width="400px" >
</p>

Y en el menu que nos abra, ingresaremos la ip que deseamos asignar y presionamos'apply'

<p>
    <img src="https://user-images.githubusercontent.com/30850990/91697287-187ba200-eb2e-11ea-85e5-ddcd0b95877a.JPG" height="350px">
</p>

*Nota: La configuracion de la maquina virtual no se puede guardar asi que este proceso se tiene que realizar cada vez que se inicie. Cabe resaltar que no toma mas de 2 minutos.*

### **Router**

De la misma manera que con las vpcs, ya iniciado el router, damos doble click sobre su icono y esto nos abrira una consola. 

Comandos a utilizar para configurar el router:
* Entra al menu de configuracion del router <br/>
  ```conf t (configure terminal)```
* Entra a la configuracion de la interfaz establecida <br/>
  ```int f<n>/<n>```
* Asigna una ip a la interfaz <br/>
  ```ip address <ip> <mask>```
* Regresar al menu anterior <br/>
  ```exit```
* Muestra un resumen de las interfaces <br/>
  ```sh ip int brief (show ip interface brief)```
* Salir de todas las configuraciones <br/>
  ```end```
* Comando para guardar <br/>
  ```wr (write)```

Iniciamos con el comnado  ```sh ip int brief``` para mostrar el estado actual de las interfaces. <br/>
<p>
<img src="https://user-images.githubusercontent.com/30850990/91697350-347f4380-eb2e-11ea-8d9f-c7a5fdaa22bf.JPG" width="500px">
</p>

Proseguimos con el comando ```conf t``` para entrar al menu de configuracion del router. Seleccionamos una interfaz con el comando
```int f<n>/<n>```  y procedemos a establecerle una ip con el comando ```ip address <ip> <mask> ```
<br/>
<p>
<img src="https://user-images.githubusercontent.com/30850990/91697352-3517da00-eb2e-11ea-8e8f-c74397f92937.JPG" width="500px">
</p>

Volvemos a usar el comando ```sh ip int brief``` para mostrar el estado de las interfaces luego de la configuracion. <br/>
<p>
<img src="https://user-images.githubusercontent.com/30850990/91697354-3517da00-eb2e-11ea-85e5-44427a3de5a1.JPG" width="500px">
</p>


El procedimiento anterior se realiza con las otras dos interfaces y el resultado obtenido es el siguiente (Recordar usar el comando ```wr``` para guardar los cambios en el router) <br/>
<p>
<img src="https://user-images.githubusercontent.com/30850990/91697355-3517da00-eb2e-11ea-9b88-cde05b4b75ec.JPG" width="500px">
</p>

<br/>

Para comprobar que la configuracion realizada este correcta haremos ping de unas vpcs a otras y tambien a la maquina virtual. 

- Pincg de la PC1 a PC2 | PC3 | VM <br/>
![ping-pc1](https://user-images.githubusercontent.com/30850990/91698481-069afe80-eb30-11ea-9180-0f6043d2507f.JPG)

- Ping de la PC4 a PC1 | PC5 | VM <br/>
![ping-pc4](https://user-images.githubusercontent.com/30850990/91698478-0569d180-eb30-11ea-8e10-c78e83852f20.JPG)

- Ping de la VM a PC1 <br/>
![ping-vm-pc1](https://user-images.githubusercontent.com/30850990/91698479-06026800-eb30-11ea-84c8-0d90bf7c11f7.JPG)

- Ping de la VM a PC5 <br/>
![ping-vm-pc5](https://user-images.githubusercontent.com/30850990/91698480-069afe80-eb30-11ea-9d3b-b2f39068a60f.JPG)

## Dominios de colision y dominios de broadcast

``` 
Switch:  n dominios de colision (n = numero puertos conectados) 
         1 dominio de broadcast
             
Router:  1 dominio de colision
         1 dominio de broadcast
         Nota: Por cada interfaz conectada
```
Dada la topologia utilizada el numero de dominios de colision y de broadcast seria el siguiente:
<p align="center">
    <img src="https://user-images.githubusercontent.com/30850990/91776443-9c736f80-ebaa-11ea-92ec-58ff9118159a.png" height="450px"/>
</p>

## Captura de paquetes
![CapturePackages](https://user-images.githubusercontent.com/30850990/91699725-f71cb500-eb31-11ea-85cd-83523a4f416a.JPG)

# Herramientas utlizadas
* [GNS3](https://www.gns3.com/)
* [VMWare](https://www.vmware.com/latam/products/workstation-pro.html)
* [Tiny-Linux](http://tinycorelinux.net/)

# Autor
Raul Xiloj
