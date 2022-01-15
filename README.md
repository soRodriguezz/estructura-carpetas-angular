# Estructura de carpetas Angular
Repositorio para tener de estandar de directorios en Angular

### Comandos tipo @schematics de Angular CLI
* ng generate
    * app-shell
    * application
    * class
    * component
    * directive
    * enum
    * guard
    * interceptor
    * interface
    * library
    * module
    * pipe
    * resolver
    * service
    * service-worker
    * web-worker
* ng new
* ng serve
* ng build
* ng test
* ng lint
* ng e2e

Dentro de la carpeta APP podemos ver 4 sub-carpetas que están al mismo nivel:

### **AUTH**
Esta carpeta contendrá todo lo relacionado a la autenticación de usuarios, componentes de tipo login, resetear contraseñas, recuperar contraseñas, etc. La idea es separar lógicas y tener bien dividida las tareas de cada uno.

Dentro de ella tenemos las siguientes subcarpetas:

**class**: Acá irán todos los archivos de tipo clase que podrás ocupar dentro de la carpeta AUTH, la cual te ayudarán a encapsular lógicas para luego poder ocuparlas, estos archivos deben tener estricta relación a la carpeta padre, en este caso AUTH.

**helpers**: Acá irán todos los servicios en donde solo deben contener funciones estáticas o variables para su uso puntual dentro de la SPA, estos archivos deben tener estricta relación a la carpeta padre, en este caso AUTH.

**models**: Acá irán todos las interfaces que tengan relación solo a la carpeta padre, en este caso AUTH

**pipes**: Acá irán todos pipes que serán utilizadas dentro de la carpeta padre, en este caso AUTH, recordemos que los pipes permiten transformar visualmente la información dentro del DOM.

**services**: Acá irán todas las clases de tipo service que encapsularán la lógica de modelos de datos, el formato de datos y las peticiones al servicios, estos serán inyectables en los componentes relacionados a la carpeta padre, en este caso AUTH.

### **CORE**
Esta carpeta contendrá todo lo relacionado a cosas transversales que podrás ocupar dentro del proyecto. La idea es separar lógicas y tener bien dividida las tareas de cada uno.

Dentro de ella tenemos las siguientes subcarpetas:

**interceptors**: Acá irán todas las clases de tipo interceptor que podrás utilizar para modificar las peticiones que salen o vienen a nuestra aplicación.

**services**: Acá irán todas las clases de tipo service que encapsularán la lógica de modelos de datos, el formato de datos y las peticiones al servicios, estos serán inyectables en los componentes relacionados a la carpeta padre, en este caso CORE.

### **SHARED**
Esta carpeta contendrá todo lo relacionado a cosas que se usaran de forma global y serán reutilizadas y compartidas dentro de la app. La idea es separar lógicas y tener bien dividida las tareas de cada uno.

Dentro de ella tenemos las siguientes subcarpetas:

**class**: Acá irán todos los archivos de tipo clase que podrás ocupar dentro de la carpeta SHARED, la cual te ayudarán a encapsular lógicas para luego poder ocuparlas, estos archivos deben tener estricta relación a la carpeta padre, en este caso SHARED.

**components**: Acá irán todos los componentes que tengan estricta relación a la carpeta padre, en este caso SHARED.

**helpers**: Acá irán todos los servicios en donde solo deben contener funciones estáticas o variables para su uso puntual dentro de la SPA, estos archivos deben tener estricta relación a la carpeta padre, en este caso SHARED.

**models**: Acá irán todos las interfaces que tengan relación solo a la carpeta padre, en este caso SHARED.

**pipes**: Acá irán todos pipes que serán utilizadas dentro de la carpeta padre, en este caso SHARED, recordemos que los pipes permiten transformar visualmente la información dentro del DOM.

**services**: Acá irán todas las clases de tipo service que encapsularán la lógica de modelos de datos, el formato de datos y las peticiones al servicios, estos serán inyectables en los componentes relacionados a la carpeta padre, en este caso SHARED.

### **VIEWS** 
Esta carpeta contendrá todo lo relacionado a componentes de tipo vistas. La idea es separar lógicas y tener bien dividida las tareas de cada uno.

Dentro de ella tenemos las siguientes subcarpetas:

**class**: Acá irán todos los archivos de tipo clase que podrás ocupar dentro de la carpeta VIEWS, la cual te ayudarán a encapsular lógicas para luego poder ocuparlas, estos archivos deben tener estricta relación a la carpeta padre, en este caso VIEWS.

**components**: Acá irán todos los componentes que tengan estricta relación a la carpeta padre, en este caso VIEWS.

**helpers**: Acá irán todos los servicios en donde solo deben contener funciones estáticas o variables para su uso puntual dentro de la SPA, estos archivos deben tener estricta relación a la carpeta padre, en este caso VIEWS.

**models**: Acá irán todos las interfaces que tengan relación solo a la carpeta padre, en este caso VIEWS.

**pipes**: Acá irán todos pipes que serán utilizadas dentro de la carpeta padre, en este caso VIEWS, recordemos que los pipes permiten transformar visualmente la información dentro del DOM.

**services**: Acá irán todas las clases de tipo service que encapsularán la lógica de modelos de datos, el formato de datos y las peticiones al servicios, estos serán inyectables en los componentes relacionados a la carpeta padre, en este caso VIEWS.

Cabe resaltar que dividiendo de esta manera los módulos beneficiará la carga de los componentes y estos podrán cargarse en el browser mucho mas rápido, claro esto también ayuda al LAZY LOADING al momento de mostrar el contenido en pantalla.

![](https://i.imgur.com/juF4vjC.png)

También es importante mencionar la estructura de un componente, acá tienes 2 opciones que debes manejar: componentes ruteables y componentes no ruteables.

**RUTEABLES**: Si deduces que estos componentes deben ser ruteables, o sea, llamados desde otro componente, inmediatamente tienes que pensar que deben tener su propio routing y su propio modulo cargando así sus propias dependencias, quedando de la siguiente manera.

![](https://i.imgur.com/1sD8RBo.png)

El archivo routing te ayudara a que los componentes tengan su propio alias al momento de renombrar su ruta, también te ayudara a manejar de mejor manera la carga de tu SPA.

![](https://i.imgur.com/2VqzIA1.png)

**NO RUTEABLES**: Este caso se da siempre cuando es un componente de tipo **CHILDREN** ósea un componente HIJO, Si deduces que estos componentes no serán ruteables y son children, o sea, no serán llamados desde otro componente sino cargados de forma asyncrona por el componente padre, inmediatamente tienes que pensar que no deben tener su propio routing ni su propio modulo, ya que estos módulos serán importados desde el modulo del padre, quedando de la siguiente manera.

![](https://i.imgur.com/Bpkv15I.png)
