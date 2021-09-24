Instalación de maven en Ubuntu

Para instalar maven en nuestro sistema Ubuntu actualizaremos con el comando update y acto seguido procedemos a la instalación del Maven

```
sudo apt update
sudo apt install maven
```
![1](https://user-images.githubusercontent.com/61906112/134667329-b639cdfa-93b6-464e-a67a-e72e8016599d.PNG)


Verificamos que la instalación ha sido correcta preguntando la versión del Maven instalada y deberíamos tener esta salida mostrada en la imagen.
```
mvn -version
```
![2](https://user-images.githubusercontent.com/61906112/134667336-0772ec61-4aea-4c46-a32a-50eb0ea83b7b.PNG)


Instalar una versión concreta de Maven

Para realizar la instalación de una versión concreta usaremos el siguiente comando para descargar el fichero.
```
wget https://www.apache.org/dist/maven/maven-3/3.8.2/binaries/apache-maven-3.8.2-bin.tar.gz -P /tmp
```

Una vez completada la descargar usaremos las siguientes ordenes para descomprimir el fichero y realizar un enlace para el directorio donde instalamos el maven.
```
Sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt
sudo ln s /opt/apache-maven-3.8.2 /opt/maven
```

![3](https://user-images.githubusercontent.com/61906112/134667354-5b17962c-9ed2-4d7c-b06f-9ca7c494d6b2.PNG)

A continuación vamos a añadir las variables de entorno lo realizaremos con el comando nano y añadimos las siguientes lineas de código.
```
sudo nano /etc/profile.d/maven.sh
```
![4](https://user-images.githubusercontent.com/61906112/134667390-52a792a2-b032-4b09-98ac-e4d8af5b4ba2.PNG)

```
export JAVA_HOME=/usr/lib/jvm/IMPORTANTE-RESPETAR-LA-VERSION-DE-JAVA-INSTALADA
 export M2_HOME=/opt/maven
 export MAVEN_HOME=/opt/maven
 export PATH=${M2_HOME}/bin:${PATH}
 ```
 ![5](https://user-images.githubusercontent.com/61906112/134667464-dc4fb6c1-04b7-432e-bf4a-09925c4d1851.PNG)

 
Guardamos y cerramos el archivo. (ctrt+x)


Debemos insertar el siguiente comando para que el archivo anterior sea ejecutable, también usaremos el comando sorce para cargar las variables de entorno.
```
sudo chmod + /etc/profile.d/maven.sh
source /etc/profile.d/maven.sh
```
![6](https://user-images.githubusercontent.com/61906112/134667489-a1823219-7740-4d4a-b8b0-b5811a6be78b.PNG)


Por ultimo comprobaremos la versión de nuestro Maven debería mostrar el mismo resultado que en la imagen.
```
Mvn -version 
```
![7](https://user-images.githubusercontent.com/61906112/134667497-78ebcc0c-6880-498d-95b7-d4db094e42b7.PNG)
