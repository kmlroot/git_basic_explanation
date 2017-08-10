# GIT

[![Git](https://www.git-tower.com/learn/content/01-git/01-ebook/en/01-command-line/04-remote-repositories/01-introduction/basic-remote-workflow.png)](https://git-scm.com/)

En la siguiente guía se explicará y se sugerirá la forma en la que deberíamos trabajar en proyectos colaborativos.

- Si no se cuenta con un repositorio remoto se deberá crear uno en cualquier entorno en la nube (Github, Gitlab, Bitbucket...) y realizar los siguientes pasos
    ```
    git add .
    git commit -S -m "My features"
    git remote add origin https://github.com/user/repo.git
    git push -u origin master
    ``` 


1. Para cada historia de usuario que contenga valor crear una nueva rama
    - Estando en la rama principal (master o la que se haya asignado) y con esta tolamente actualizada procedemos a crear nuestra propia rama
    ```
    git checkout -b my-feature
    ```
    - Ya estando en esta nueva rama puedo empezar a agregar todas las funcionalidades

2. Cada vez que se agregue una nueva funcionalidad dentro de la rama es importante hacer commit (no push) y no esperar hasta el final para hacerlo. Los commits verificados son una muy buena práctica

    ```
    git status
    git add .
    git commit -S -m "Adding some feature"
    ```

- [Commits verificados usando GPG](https://help.github.com/articles/signing-commits-using-gpg/)

3. Después de finalizar las tareas en esta rama se deberá proceder a subir los cambios al repositorio remoto.

    ````
    git status
    git add .
    git commit -S -m "Commit for my last change"
    git push origin my-feature
    ````
    
4. Esto nos generará una nueva rama en nuestro repositorio remoto y ahí podrémos crear un nuevo pull request con tan solo algunos clicks, esto es una muy buena practica ya que tenemos la aprobación de todo el equipo de desarrollo, estos se encargarán de revisar y probar todo el pull request

5. Para aprobar un pull request se deberá comentar en este con unos de estos dos símbolos 👍   🚢 cuando todos los miembros del equipo hayan aprobado el pull request se deberá hacer el respectivo merge, de lo contrario el solicitante del pull request deberá proceder a realizar los cambios sugeridos y repetir todo el proceso anteriomente mencionado

- Para bajar ramas que están en el repositorio remoto basta con hacer
  ```
  git fetch
  ```
    
6. Si se hizo merge **TODOS** los miembros del equipo deberán pasarse a la rama prinicpal y actualizarla, para actualizarla basta con entrar a dicha rama y hacer
    ````
    git pull
    ````

7. En caso de estar trabajando en una rama local y el repositorio en la nube en su rama principal sufrío cambios también se deberá actualizar la rama propia haciendo un git rebase

- Nos cambiamos a nuestra rama después de realizar el pull en la rama prinicpal.
    ````
    git rebase master
    ````
    
- NOTA: Esto puede generar algunos conflictos, se deberán solucionar dichos conflictos antes de continuar trabajando en nuestra rama





