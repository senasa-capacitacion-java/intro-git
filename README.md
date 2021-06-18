# Introduccion a Git
Ejecutamos los pasos basicos para crear un repositorio de git y comenzar a versionar nuestros archivos

## Creación de un repositorio local desde cero

Creá una carpeta nueva "intro-git"
```bash
mkdir intro-git
```

Ingresá en la carpeta intro-git
```bash
cd intro-git/
```

Inicializá un nuevo repositorio git a partir de la carpeta intro-git
```bash
git init
```

Creá un archivo de texto con el mensaje "Hola,Mondu!"
```bash
echo "Hola,Mondu!" > saludo.txt
```

Chequeá el estado de directorio de trabajo
```bash
git status
```

Agregá el archivo "saludo.txt" a stage
```bash
git add saludo.txt
```

Confirmá los cambios generando el primer commit
```bash
git commit -m "se suma el archivo de saludo"
```

Listá los commit del repositorio
```bash
git log
```

Corregí la ortografia del saludo
```bash
echo "Hola, Mundo!" > saludo.txt
```

Visualizá los cambios respecto al archivo en el anterior commit
```bash
git diff
```

Agrergá al stage
```bash
git add saludo.txt
```

Confirmá los cambios creando un nuevo commit
```bash
git commit -m "se corrige ortografia"
```

Visualiza los dos commits
```bash
git log
```

## Subir el repositorio local a uno remoto

En esta sección vamos a subir el repositorio local a un repositorio remoto. Necesitamos tener una cuenta en alguno de los gestores de repositorios en la nube. Para este ejemplo, vamos a usar GitHub (github.com)

El que no tenga una cuenta creada, puede seguir los  pasos de la siguiente guía 

[Guia para registrarse en Github](https://git-scm.com/book/es/v2/GitHub-Creaci%C3%B3n-y-configuraci%C3%B3n-de-la-cuenta)

> Importante: No te olvides de subir tu llave pública a tu perfil de GitHub

### Pasos
1. Creá un repositorio remoto usando la interface visual de GitHub y copia la URL del repositorio

2. En tu máquina local, abrí una consola y ubicáte dentro del directorio intro-git. Ejemplo:
```
cd intro-git/
```

3. Indicá a Git la URL a tu repositorio remoto. Por convención, el nombre de tu repositorio remoto se llamará origin
```
 git remote add origin git@github.com:ortizman/intro-git.git
```

4. Subí todos tus commits del repositorio local al repositorio remoto. La rama por defecto en git es "master".
```
 git push -u origin master
```

## Clonar, modificar y volver a subir

Vamos a simular un ciclo completo de colavoración básica. Vamos a clonar el repositorio remoto, modificar el archivo saludo.txt para convertirlo en una aplicación Java, confirmar los cambios localmente y luego subirlos al repositorio remoto.

Para los siguientes pasos, abrir una terminal

1. Clonar el repositorio remoto en una nueva carpeta.
```
git clone git@github.com:ortizman/intro-git.git
```
> remplazar la url del repositorio, por la url de su repositorio

2. Abrir el proyecto en Visual Studio Code

3. Renombrar el archivo saludo.txt a Saludo.java

4. Remplazar el contenido del archivo por el siguiente contenido

    ```java
    public class App {
        public static void main(String[] args) {
            System.out.println("Hola,mondu");
        }
    }
    ```

5. Agregar los cambios al stage y commitear

6. Chequeá que los cambios **NO** estan en tu repositorio remoto. Solo en tu repositorio local.

7. Subí los cambios a tu respositorio remoto
