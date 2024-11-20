# PetMOOD
Importaciones y Configuración Inicial
Este código usa React y React Native para crear una aplicación móvil. Se importan diversos componentes y módulos necesarios para gestionar estados, animaciones, vistas, y otras funcionalidades.

React y Hooks: Se usan los hooks useState, useRef y useEffect:

useState permite gestionar el estado de los datos, en este caso, las huellas.
useRef se usa para crear referencias a valores animados que no deberían reiniciarse en cada render.
useEffect se usa para ejecutar funciones secundarias como las animaciones justo después de que el componente se ha montado.
Componentes de React Native:

View: Es un contenedor para otros componentes, similar a un div en HTML.
Text: Para mostrar texto en la pantalla.
TouchableOpacity: Un botón que tiene una respuesta visual al ser presionado, en este caso, el botón de la cámara.
Dimensions: Se usa para obtener el ancho y la altura de la pantalla del dispositivo, lo cual es útil para colocar elementos aleatoriamente.
Animated y Easing: Se utilizan para manejar animaciones, haciendo que ciertos elementos se muevan o cambien su forma con suavidad.
Obtención de las Dimensiones de la Pantalla
Se obtienen las dimensiones de la pantalla del dispositivo usando Dimensions.get('window'). Con esto, se obtiene el ancho (width) y la altura (height), que se usarán más adelante para posicionar las huellas en ubicaciones aleatorias.

Función para Generar Huellas
Hay una función llamada generateFootprints que genera una lista de 80 huellas con posiciones aleatorias en la pantalla:

Se crea un arreglo footprints que contendrá los datos de cada huella.
Para cada huella:
Se genera una posición aleatoria para las propiedades left (horizontal) y top (vertical).
Se define un tamaño aleatorio entre 20 y 50 para dar variación visual.
También se define una opacidad aleatoria entre 0.6 y 0.75, para que las huellas tengan una apariencia sutil.
Componente Principal (App)
Este es el componente principal de la aplicación, que gestiona todo el diseño y comportamiento de la interfaz.

Estados y Referencias
useState(generateFootprints()): Se usa para inicializar el estado con las huellas generadas aleatoriamente.
useRef se utiliza para crear referencias para los valores animados:
animatedValues: Crea un valor animado para cada huella (80 en total). Inicialmente, todos estos valores están en 0.
iconBounce: Se usa para animar el movimiento de rebote del ícono del perro.
scaleAnim: Se usa para manejar la animación del botón, haciendo que se agrande o se reduzca cuando se presiona.
Hook useEffect para Animaciones
Este hook se usa para iniciar las animaciones después de que el componente se haya montado.

Animación de Huellas:

Se anima cada huella usando animatedValues. Las huellas se animan subiendo y bajando lentamente para crear un efecto visual de movimiento. La animación es continua gracias a Animated.loop.
Cada huella tiene una duración de animación aleatoria, haciendo que las huellas se muevan a ritmos diferentes, creando un efecto más orgánico.
Animación del Ícono del Perro:

Se anima el ícono del perro para que rebote suavemente hacia arriba y hacia abajo, dando la sensación de que el ícono está "saltando". Esta animación también se repite de forma continua.
Animaciones del Botón (Métodos onPressIn y onPressOut)
El botón de la cámara tiene una animación de escala cuando se presiona, dándole al usuario una respuesta táctil visual.

onPressIn: Cuando el botón se presiona, se reduce su tamaño un poco (0.95 de su tamaño original) usando una animación de resorte.
onPressOut: Cuando se deja de presionar el botón, vuelve a su tamaño original (1) con una animación de resorte que tiene cierta fricción, haciendo que el botón parezca "rebotar" ligeramente.
Renderizado del Componente
El componente principal App se encarga de renderizar los elementos en pantalla:

Renderizado de las Huellas
Se usa .map() para recorrer todas las huellas y dibujarlas en la pantalla.
Cada huella es un componente Animated.Text que muestra el emoji 🐾.
Las propiedades de cada huella, como left, top, fontSize y opacity, se aplican según los valores generados aleatoriamente.
Transformaciones Animadas:
Se usan las transformaciones translateX y translateY para que las huellas se muevan de forma suave en diferentes direcciones, creando un efecto visual dinámico.
Renderizado del Frame Principal
Dentro del frame principal se encuentran los siguientes elementos:

Título (PETMOOD): Se muestra sin animación, pero con un estilo que incluye una sombra para darle más énfasis.
Eslogan: El eslogan tiene un estilo con una sombra más pronunciada para mejorar su visibilidad y hacer que destaque.
Ícono del Perro: Se anima usando iconBounce para que parezca que el perro está saltando suavemente.
Botón de Cámara: Cuando se presiona, el botón tiene una animación de escala para dar la sensación de ser interactivo.
Aviso de Privacidad y Derechos Reservados: En la parte inferior se muestra un aviso de privacidad y un mensaje de derechos reservados.
Estilos (StyleSheet)
Se utiliza StyleSheet.create() para definir todos los estilos utilizados en la aplicación.

container: Contenedor principal, con un fondo blanco y los elementos alineados al centro de la pantalla.
footprint: Define el estilo de cada huella, posicionándola con position: 'absolute' y asignándole un color azul oscuro.
frame: Es el contenedor principal de los elementos, con un fondo translúcido para diferenciarlo del fondo blanco de la aplicación. Tiene un borde redondeado para una apariencia más amigable.
title y subtitle: Define los estilos del título (PETMOOD) y del eslogan. Ambos tienen una sombra aplicada para darles más visibilidad.
iconContainer y icon: El ícono del perro se coloca dentro de un contenedor circular que tiene un borde de color azul claro. El ícono del perro tiene un tamaño considerable para ser el foco visual principal.
button y buttonText: Define el estilo del botón de la cámara y su texto. El botón es de color amarillo, con un borde redondeado para una mejor experiencia visual y táctil.
footerContainer, privacyNotice, y footer: Define los estilos para el aviso de privacidad y los derechos reservados. Se alinean al centro y se utiliza un subrayado en el aviso de privacidad para indicar que es importante
