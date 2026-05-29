# git practica 2
Taller GIT. Práctica 2.
Guarda los comandos realizados, así como los resultados(capturas), integrarlo dentro del mismo repositorio

## Trabajar con un proyecto HTML y un repositorio local.
- Crea una carpeta practica-taller-git en tu pc.
- Inicializa el repositorio. 
 ```bash
 git init
 ```
- Crea el fichero index.html con un html simple.
- Comprueba que el repositorio a detectado el cambio. 
```bash
git status
```
- Añade el fichero al stage. 
```bash
git add index.html.
```
- Confirma los cambios. 
```bash
git commit -m “added index file”
```
- Añade un fichero description.html y edita index.html.
- Comprueba que ha detectado el nuevo fichero y la modificación de index.
```bash
git status
git diff
```
- Crea un fichero TODO.txt de tareas pendientes.
- Comprueba que git ha detectado el nuevo fichero. 
```bash
git status
```
- Ignora el fichero TODO.txt ya que es donde anotaremos nuestras tareas personales y no debe formar parte del proyecto. Para ello crea un fichero .gitignore con la linea TODO.txt.
- Comprueba que ya no detecta el nuevo fichero TODO.txt (si que detectara el .gitignore claro). 
```bash
git status
```
- Añade y confirma el .gitignore.
- Puedes continuar añadiendo ficheros html, css e imágenes para probar el repositorio.


## Haz un fork del repositorio creado para la práctica del taller:
- Entra en https://github.com/
- Accede a tu cuenta.
- Accede al repositorio del profesor https://github.com/lalobarri/git-practica-2.git
- Pulsa el botón fork (parte superior derecha) para crearte una copia del mismo en tu cuenta.
- Clona el repositorio en tu equipo *en otra carpeta diferente que la llamaremos 'git-practica-2'*. Quedará algo parecido a lo siguiente:
```bash
git clone https://github.com/[tu-nombre-de-usuario]/git-practica-2.git
```
- Crea un nuevo fichero en el proyecto que se llame [tu-nombre-de-usuario].html
- Edita el fichero añadiendo como título tu nombre, algún texto y lo que desees en el.
- Añade el fichero al repositorio.
- Súbelo al repositorio remoto (github). 
```bash
git push
```
- Crea una rama develop y cámbiate a ella.
```bash
git checkout -b develop
```
- Realiza cambios en el proyecto, confírmalos y súbelos al repositorio remoto.
```bash
git status
git add *
git commit -m "Mensaje del commit..."
git push origin
```
- Desde github crea un pull request de la rama develop a main.
- Fusiona la rama develop con en main. No deberías de tener ningún conflicto.
- Haz nuevos cambios en el proyecto siguiendo el flujo de trabajo git flow.


## Preguntas
Crea un nuevo fichero respuestas.md, contesta las siguientes preguntas y súbelo a tu repositorio remoto de github:

 1. ¿Qué sucede cuando hacemos un git add?
 2. ¿Qué sucede cuando hacemos un git commit? ¿Dónde está ese commit? 
 3. ¿Por qué al hacer git commit todavía no está disponible ese commit en el repositorio remoto?
 4. ¿Qué hay que hacer para que veamos este commit en nuestro repositorio remoto de github?
 5. ¿Qué diferencia hay entre hacer un fork o crear una nueva rama?
 6. ¿Qué comando se utiliza para crear una nueva rama sin cambiarte a ella?
 7. ¿Cuál es la diferencia entre los comandos git switch y git checkout al trabajar con ramas?
 8. ¿Qué es una rama por defecto (como main o master) y por qué es importante?
 9. ¿Qué comando te permite ver la lista de todas las ramas locales de tu repositorio?
 10. En el contexto de Git, explica con tus propias palabras qué es una rama (branch) y cuál es su beneficio principal al trabajar en un proyecto de software
 11. ¿Qué ha pasado con el contenido de la carpeta practica-taller-git? ¿Por qué no la podemos ver en nuestro repositorio remoto de github?


*Utilice un formato que permita distinguir entre sus preguntas y respuestas*

# Respuestas - Taller Git Práctica 2

**Alumno:** Miguel Angel Alvarez Ibarra  
**Grupo:** GIDS6082  
**Materia:** Ingeniería de Software — UTNG

---

## Preguntas y Respuestas

---

### 1. ¿Qué sucede cuando hacemos un `git add`?

**Respuesta:**  
Cuando ejecutamos `git add`, le indicamos a Git qué archivos (o cambios específicos) queremos incluir en el próximo commit. Este comando mueve los cambios del **área de trabajo (working directory)** al **área de preparación (staging area o index)**. En este punto, los archivos todavía no han sido guardados de forma permanente en el historial del repositorio; simplemente están "listos" o "preparados" para ser confirmados. Es como preparar los ingredientes antes de cocinar: los tienes listos, pero el platillo aún no está hecho.

---

### 2. ¿Qué sucede cuando hacemos un `git commit`? ¿Dónde está ese commit?

**Respuesta:**  
Al ejecutar `git commit`, Git toma todos los cambios que estaban en el **staging area** y los guarda de forma permanente como una nueva instantánea (snapshot) en el **historial del repositorio local**. Cada commit tiene un identificador único (hash SHA-1), un mensaje descriptivo, la fecha y el autor. Ese commit existe únicamente en el **repositorio local** de nuestra máquina, dentro de la carpeta `.git/`. Aún no ha salido de nuestra computadora.

---

### 3. ¿Por qué al hacer `git commit` todavía no está disponible ese commit en el repositorio remoto?

**Respuesta:**  
Porque `git commit` solo guarda los cambios en el **repositorio local**. Git es un sistema de control de versiones **distribuido**, lo que significa que cada desarrollador tiene una copia completa del historial en su propia máquina. El repositorio remoto (como GitHub) es un servidor independiente y no se entera de nuestros commits locales a menos que se lo enviemos de forma explícita. El commit vive en nuestra máquina hasta que decidamos sincronizarlo con el servidor remoto.

---

### 4. ¿Qué hay que hacer para que veamos este commit en nuestro repositorio remoto de GitHub?

**Respuesta:**  
Debemos ejecutar el comando `git push` para enviar los commits locales al repositorio remoto. Por ejemplo:

```bash
git push origin main
```

Este comando sube los commits de nuestra rama local (`main`) al servidor remoto llamado `origin` (que apunta a nuestro repositorio en GitHub). Una vez ejecutado, los cambios serán visibles en GitHub para cualquier persona con acceso al repositorio.

---

### 5. ¿Qué diferencia hay entre hacer un fork o crear una nueva rama?

**Respuesta:**  
- **Fork:** Es una **copia completa e independiente** de un repositorio en nuestra cuenta de GitHub. Se usa principalmente cuando queremos contribuir a un proyecto que no es nuestro o cuando queremos experimentar sin afectar el repositorio original. El fork es un repositorio separado en la nube, con su propia URL.
  
- **Nueva rama (branch):** Es una **línea de desarrollo paralela** dentro del mismo repositorio. Permite trabajar en nuevas funcionalidades o correcciones de forma aislada sin afectar la rama principal (`main`), pero todo sigue siendo parte del mismo repositorio. Las ramas se crean y gestionan localmente (y pueden subirse al remoto).

**En resumen:** el fork crea un repositorio nuevo en otra cuenta; la rama crea un camino alternativo dentro del mismo repositorio.

---

### 6. ¿Qué comando se utiliza para crear una nueva rama sin cambiarte a ella?

**Respuesta:**  
Se utiliza el comando:

```bash
git branch nombre-de-la-rama
```

Este comando crea la rama pero nos deja situados en la rama en la que estábamos. Si quisiéramos crear la rama y cambiar a ella al mismo tiempo, usaríamos `git checkout -b nombre-de-la-rama` o `git switch -c nombre-de-la-rama`.

---

### 7. ¿Cuál es la diferencia entre los comandos `git switch` y `git checkout` al trabajar con ramas?

**Respuesta:**  
Ambos permiten cambiar de rama, pero tienen diferencias importantes:

- **`git checkout`:** Es un comando más antiguo y **multipropósito**. Además de cambiar de rama, también puede restaurar archivos a un estado anterior, crear ramas (`-b`), entre otras funciones. Por ser tan versátil, puede resultar confuso.

- **`git switch`:** Fue introducido en Git 2.23 con el propósito de ser un comando **más claro y específico** para cambiar de rama. También puede crear ramas con el flag `-c`. Al tener una sola responsabilidad, su uso es más intuitivo y menos propenso a errores.

**Ejemplo equivalente:**
```bash
git checkout develop        # Cambiar a rama develop (forma antigua)
git switch develop          # Cambiar a rama develop (forma moderna)

git checkout -b feature     # Crear y cambiar de rama (forma antigua)
git switch -c feature       # Crear y cambiar de rama (forma moderna)
```

---

### 8. ¿Qué es una rama por defecto (como `main` o `master`) y por qué es importante?

**Respuesta:**  
La rama por defecto es la **rama principal del repositorio**, que se crea automáticamente al inicializar un repositorio con `git init` o al clonar uno. Históricamente se llamaba `master`, pero la convención actual (adoptada por GitHub desde 2020) es llamarla `main`.

Es importante porque:
- Representa el **código estable y en producción** del proyecto.
- Es el punto de referencia desde el cual se ramifica el nuevo desarrollo.
- Es la rama que los demás colaboradores ven primero al acceder al repositorio.
- Las integraciones continuas (CI/CD) suelen ejecutarse sobre esta rama.

Por ello, los cambios deben llegar a `main` solo cuando están probados y aprobados, generalmente a través de pull requests.

---

### 9. ¿Qué comando te permite ver la lista de todas las ramas locales de tu repositorio?

**Respuesta:**  
El comando es:

```bash
git branch
```

Muestra todas las ramas locales y resalta con un asterisco (`*`) la rama en la que nos encontramos actualmente. Si también queremos ver las ramas remotas, usamos:

```bash
git branch -a     # Muestra ramas locales y remotas
git branch -r     # Muestra solo las ramas remotas
```

---

### 10. En el contexto de Git, explica con tus propias palabras qué es una rama (branch) y cuál es su beneficio principal al trabajar en un proyecto de software

**Respuesta:**  
Una rama en Git es como un **camino alternativo dentro del historial del proyecto**. Imaginemos que el historial de commits es una línea de tiempo: al crear una rama, estamos bifurcando esa línea para poder trabajar de forma independiente sin tocar el código principal.

El beneficio principal es el **aislamiento del trabajo**. Cada desarrollador (o cada funcionalidad) puede tener su propia rama, lo que significa que:
- Se pueden desarrollar nuevas características sin romper el código que ya funciona.
- Varios desarrolladores pueden trabajar al mismo tiempo sin pisarse el trabajo.
- Si algo sale mal en una rama, simplemente no se fusiona con `main` y el proyecto principal queda intacto.
- Facilita la revisión de código a través de pull requests antes de integrar cambios.

En resumen, las ramas hacen que el trabajo en equipo sea más seguro, organizado y eficiente.

---

### 11. ¿Qué ha pasado con el contenido de la carpeta `practica-taller-git`? ¿Por qué no la podemos ver en nuestro repositorio remoto de GitHub?

**Respuesta:**  
La carpeta `practica-taller-git` fue creada y trabajada como un **repositorio Git local independiente** (con `git init` dentro de esa carpeta). Nunca se conectó a un repositorio remoto en GitHub, es decir, nunca se configuró un `remote origin` ni se realizó ningún `git push`.

Por eso no aparece en GitHub: todo el historial, commits y archivos de esa carpeta existen únicamente en nuestra máquina local. Para hacerla visible en GitHub habría que:
1. Crear un nuevo repositorio en GitHub.
2. Vincularlo como remoto: `git remote add origin <URL>`.
3. Subir el contenido: `git push -u origin main`.

En cambio, el repositorio `git-practica-2` fue clonado desde GitHub (ya tenía remoto configurado), por eso los cambios realizados ahí sí pudieron subirse con `git push`.

---

*Archivo generado como parte del Taller GIT - Práctica 2*  
*Universidad Tecnológica del Norte de Guanajuato (UTNG)*


---

## Capturas y Evidencias

---

<img width="1050" height="904" alt="image" src="https://github.com/user-attachments/assets/56650776-bed6-40d1-98bf-79e2dd266396" />

<img width="1050" height="710" alt="image" src="https://github.com/user-attachments/assets/283f323c-a079-43d8-86e2-ed01a4efd08a" />

<img width="1050" height="506" alt="image" src="https://github.com/user-attachments/assets/6bc0ff5d-d54b-4ad6-aadb-e5bd3e38b8ec" />

<img width="1050" height="547" alt="image" src="https://github.com/user-attachments/assets/77493ca0-9b8a-4bba-a98d-259d927ba526" />

<img width="1050" height="549" alt="image" src="https://github.com/user-attachments/assets/64acf5be-b22e-489b-ba27-6a9d205d25ce" />

<img width="1050" height="476" alt="image" src="https://github.com/user-attachments/assets/d4a57c25-c3ab-478b-94e5-ae02b00122ca" />

<img width="1919" height="835" alt="image" src="https://github.com/user-attachments/assets/f6987036-cb1d-4b2e-b4b2-826eaf96eaa7" />
