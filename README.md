# Proyecto final: Dudas

Te dejo por aqui la mas o menos la infraestructura que imagine en relacion a los lineamientos del primer proyecto. Me surgen diferentes dudas que te dejo por aqui. 

![infraestructura-proyecto](https://github.com/Ale-source-prog/proyecto-final/assets/125092085/6c23738f-7355-49ff-803a-64331f5a3adc)

#### ------------------------

Segun la clase que vimos entiendo que la estructura de kubernetes en produccion seria mas o menos esta. 

Mi idea es aprovisionar la infraestrctura con terraform, creando 1 balanceador que mueva las conexiones entre 2 "EC2" en AWS, estas dentro tendra el 1 cluster de kubernete en local usando MiniKube. 

Luego, definimos el Front en un Pod, defimos el back en otro Pod e imagine un pod para las herramientas de monitoreo
Luego se me ocurrio crear un reverse proxy con nginx para agregarle una capa de seguridad, este forma parte del front.


-¿Realmente estaria bien ubicar la monitorizacion dentro de un pod o este deberia ir fuera del cluster de kubernetes? ya que entiendo que estas herramientas de monitoreo deben poder tener coenctividad con los otros pods para recopilar informacion, pero tambien deberia monitorizar componentes como el balanceador y las maquinas "EC2". 

-¿En esta infraestructura que se expone al "cliente" estaria bien especificar como se aprovisiona dicha infraestructura? , en mi caso dividi las secciones, diferenciando entre la infraestrucura aprovisionada por terraform y el cluster de kubernetes. 

-¿Tambien es una buena practica mostrar la conexion que tendra el cliente? , en la imgen puse el "server" "user" como el usuario administrador que se encargará de acceder al monitorieo y al cluster de kubernetes. 

-Estuve pensando en aprovisionar un redis para la API, pero, ¿Es realmente viable, tendria algun beneficio? 
