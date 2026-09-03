# Mi primera práctica con Git

Este repositorio fue creado para aprender los fundamentos de Git.

_Isabel Valladolid_

## Git y Control de Versiones

Git es un sistema de control de versiones que sirve para registrar todos los cambios hechos dentro de un proyecto. 

Cuando desarrollamos software el codigo cambia constantemente: se agregan funciones, corrigen errores, etc. Sin una herramienta de control de versiones surgen varios problemas como: perdida de historial, conflictos entre colaboradores, la falta de trazabilidad, entre otros.

Git lleva un registro ordenado de cada cmabio hecho al codigo, permitiendo volver a versiones anteriores, comparar cambios y coordinar el trabajo de varias personas. 
Es una herramienta muy comun utilizada por desarrolladores de software, ya que es muy util para: tener un historial completo lo que permite que cambio queda registrado, permite una colaboración eficiente, reversibilidad; experimentación segura y trabajo distribuido.

Si en lugar de Git se optará por usar copias manuales, por ejemplo carpetas como `proyecto_final`, `proyecto_final_final`, `proyecto_final_ahoraSi` tendríamos varios problemas que Git evita, por ejemplo: las copias manuales ocupan mucho espacio, mientras que Git solo guarda las diferencias entre versiones; en las copias manuales no hay registeo de que cambió exactamente, en Git cada commit describe que cambio y por qué. En Gir, puedes comparar versiones automaticamente, ademas de que se puede volver a cualquier punto del historial con un comando.

Git fue creado por Linus Torvalds, el mismo desarrollador finlandés-estadounidense que creó el kernel de Linux, en el año 2005.

Fue creado específicamente para gestionar el desarrollo del kernel de Linux. Antes de Git, el proyecto usaba un sistema propietario llamado BitKeeper, pero cuando la empresa que lo mantenía retiró la licencia gratuita que usaba la comunidad Linux, Torvalds decidió crear su propia herramienta de control de versiones. La necesidad principal era manejar de forma eficiente las contribuciones de miles de desarrolladores distribuidos por todo el mundo, algo que las herramientas existentes en ese momento no resolvían bien en cuanto a velocidad y manejo de código distribuido a gran escala.

Que Git sea distribuido significa que cada desarrollador tiene una copia completa del repositorio en su propia computadora, incluyendo todo el historial de cambios, no solo los archivos actuales.
Esto se diferencia de los sistemas de control de versiones centralizados (como CVS o Subversion), donde existe un único servidor central que guarda todo el historial, y los usuarios solo tienen una copia de trabajo de la versión más reciente.

Las implicaciones prácticas de este modelo distribuido son:

+ Trabajo sin conexión: puedes hacer commits, ver el historial y crear ramas sin necesidad de estar conectado a un servidor.

+ Mayor velocidad: la mayoría de las operaciones (commit, diff, log, branch) se ejecutan localmente, sin depender de la red.

+ Redundancia y seguridad: como cada copia del repositorio contiene todo el historial, si el servidor central falla o se pierde, cualquier copia local puede restaurarlo por completo.

+ Colaboración flexible: los desarrolladores pueden sincronizar cambios entre sí de múltiples formas (no solo subiendo a un servidor central), por ejemplo directamente entre computadoras.

+ Ramas y experimentación más ágiles: crear y fusionar ramas es rápido y económico, ya que no depende de comunicación constante con un servidor.

## Comandos básicos de Git

| Comando | Qué hace |
|---|---|
| `git add archivo.txt` | Agrega los cambios de un archivo al **área de preparación** (staging area), marcándolos como listos para ser incluidos en el próximo commit. Se puede usar `git add .` para agregar todos los cambios. |
| `git commit -m "mensaje"` | Guarda de forma permanente los cambios que están en el área de preparación, creando un nuevo punto en el historial del repositorio, junto con un mensaje que describe qué se hizo. |
| `git branch` | Muestra la lista de ramas del repositorio. También sirve para crear una nueva rama: `git branch nombre-rama`. |
| `git merge nombre-rama` | Combina los cambios de otra rama con la rama actual, integrando el trabajo hecho en paralelo. |
| `git log` | Muestra el historial de commits del repositorio: quién hizo cada cambio, cuándo y con qué mensaje. |

### Ejemplo de flujo básico

```bash
git add .
git commit -m "Agrega función de inicio de sesión"
git branch nueva-funcionalidad
git checkout nueva-funcionalidad
# se hacen cambios...
git add .
git commit -m "Implementa validación de formulario"
git checkout main
git merge nueva-funcionalidad
git log
```

## Otras plataformas similares a GitHub

Además de GitHub, existen otras plataformas que también permiten alojar repositorios de Git en la nube y ofrecen herramientas de colaboración:

### GitLab

- Ofrece funciones muy similares a GitHub: repositorios, issues, pull requests (llamados *merge requests*), wikis, etc.
- Se destaca por su fuerte integración de **CI/CD** (integración y despliegue continuo) incluida directamente en la plataforma.
- Existe una versión en la nube (gitlab.com) y también se puede **instalar en servidores propios** (self-hosted), lo cual es muy usado por empresas que quieren mantener el control total de su infraestructura.
- Es de código abierto en su edición "Community".

### Bitbucket

- Desarrollado por **Atlassian**, la misma empresa detrás de Jira y Trello.
- Se integra muy bien con otras herramientas de Atlassian, lo que lo hace popular en equipos que ya usan ese ecosistema para gestión de proyectos.
- Ofrece repositorios de Git, pull requests, y pipelines de CI/CD (Bitbucket Pipelines).
- Tiene planes gratuitos para equipos pequeños y planes pagos para equipos más grandes.

Son plataformas que cumplen una función similar, alojan repositorios Git en internet y agregan herramientas de colaboración (issues, revisiones de código, automatización, etc.). La elección entre una u otra suele depender de las necesidades del equipo, el ecosistema de herramientas que ya usan, o si necesitan alojar el código en sus propios servidores en lugar de en la nube.

## Instalación y configuración de Git 
_Datos de mi instalación_

+ Sistema operativo utilizado: MacOs

+ Verión de Git instalada: 2.50.1 (Apple Git-155)

+ Comando para verificarla:
```bash
git config --list
```

## Estados principales de Git 

+ **Working Directory** Archivos que estamos modificando

+ **Staging Area** Cambios que icluiremos en el siguiente commit

+ **Repository** Historial de commits que Git registro

+ `git add` añadir archivos 

+ `git commit` guarda de forma permanente los cambios que están en el staging Area

## Ramas en Git

Una rama (branch) es una línea independiente de desarrollo dentro de un mismo repositorio. En términos simples, es como una copia paralela del proyecto en la que puedes hacer cambios, agregar código o probar cosas nuevas sin afectar el resto del proyecto (por ejemplo, la rama principal, `main`).
Técnicamente, una rama es solo un puntero móvil que apunta a un commit específico. Cuando haces un nuevo commit estando en una rama, el puntero de esa rama avanza automáticamente para apuntar al nuevo commit, mientras que las demás ramas permanecen sin cambios.
Por defecto, todo repositorio tiene una rama principal (históricamente llamada `master`, aunque hoy es más común main), pero se pueden crear tantas ramas adicionales como se necesite.

### ¿Por qué un equipo de desarrollo utilizaría ramas?

Las ramas son fundamentales para el trabajo en equipo porque permiten:
+ **Trabajar en paralelo sin interferir:** cada desarrollador puede crear su propia rama para trabajar en una funcionalidad, corrección de error o experimento, sin afectar el código que están usando sus compañeros.

+ **Mantener estable la rama principal:** mientras se desarrolla una nueva función en una rama separada, la rama principal (main) permanece funcional y lista para producción.

+ **Organizar el trabajo por tareas:** es común crear una rama por cada funcionalidad (`feature/login`), corrección (`fix/error-formulario`) o versión, lo que facilita saber en qué se está trabajando y por quién.

+ **Revisar el código antes de integrarlo:** las ramas permiten abrir pull requests (en GitHub) o merge requests (en GitLab) para que otros miembros del equipo revisen los cambios antes de integrarlos a la rama principal.
Experimentar sin riesgo: si una idea no funciona, simplemente se descarta la rama sin que eso afecte al resto del proyecto.

+ **Facilitar el control de versiones en paralelo:** por ejemplo, se puede mantener una rama para la versión estable en producción y otra para el desarrollo de la siguiente versión.

### ¿Qué hace `git merge`?

`git merge` **combina los cambios de una rama con otra**, integrando el historial de commits de ambas.

Por ejemplo, si estás en la rama `main` y ejecutas:

```bash
git merge nueva-funcionalidad
```

Git tomará todos los cambios (commits) hechos en la rama `nueva-funcionalidad` y los incorporará a la rama `main`, uniendo el trabajo de ambas ramas en una sola línea de desarrollo.

**¿Cómo lo hace internamente?**

- Si la rama principal no tuvo cambios nuevos desde que se creó la otra rama, Git simplemente mueve el puntero hacia adelante (esto se llama **fast-forward**).
- Si ambas ramas tuvieron cambios distintos, Git crea un **commit de fusión** (merge commit) que combina ambos historiales.
- Si los cambios afectan las mismas líneas de un mismo archivo de forma incompatible, ocurre un **conflicto de fusión**, y Git pide que la persona decida manualmente qué versión del código conservar.

En resumen, `git merge` es la herramienta que permite **reunir el trabajo hecho en distintas ramas** en una sola, lo cual es esencial para colaborar en equipo sin perder el trabajo de nadie.