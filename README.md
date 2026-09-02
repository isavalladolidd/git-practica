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

