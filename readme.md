
# Sorteo de Amigos

Este es un pequeño proyecto en JavaScript que permite agregar nombres a una lista y luego sortear aleatoriamente uno de los nombres almacenados.

## Funcionalidades

- **Agregar amigos**: Permite ingresar nombres en un campo de texto y almacenarlos en un array.
    
- **Mostrar lista de amigos**: Los nombres ingresados aparecen en una lista ordenada.
    
- **Sortear un amigo**: Selecciona aleatoriamente un nombre de la lista y lo muestra en pantalla.
    
- **Validaciones**: Verifica que no se ingresen nombres vacíos y que haya amigos disponibles antes de sortear.
    

## Tecnologías usadas

- **HTML**: Para la estructura de la página.
    
- **CSS (opcional)**: Para mejorar la apariencia (puede añadirse).
    
- **JavaScript**: Para la lógica del proyecto.
    

## Uso del Proyecto

1. Clona este repositorio o copia los archivos.
    
2. Abre el archivo `index.html` en un navegador.
    
3. Agrega nombres en el campo de entrada y presiona el botón "Agregar".
    
4. Cuando tengas una lista de nombres, presiona el botón "Sortear Amigo" para seleccionar uno al azar.
    

## Código principal

### Captura de nombres y actualización de lista

```
let amigos = [];

function agregarAmigo() {
    let input = document.getElementById("nombreInput");
    let nombre = input.value.trim();

    if (nombre === "") {
        alert("Por favor, inserte un nombre.");
        return;
    }

    amigos.push(nombre);
    actualizarLista();
    input.value = "";
}

function actualizarLista() {
    let lista = document.getElementById("listaAmigos");
    lista.innerHTML = "";
    
    for (let amigo of amigos) {
        let li = document.createElement("li");
        li.textContent = amigo;
        lista.appendChild(li);
    }
}
```

### Sorteo de un amigo aleatorio

```
function sortearAmigo() {
    let resultado = document.getElementById("resultado");
    
    if (amigos.length === 0) {
        resultado.innerHTML = "No hay amigos en la lista para sortear.";
        return;
    }

    let indiceAleatorio = Math.floor(Math.random() * amigos.length);
    let amigoSorteado = amigos[indiceAleatorio];

    resultado.innerHTML = `El amigo sorteado es: <strong>${amigoSorteado}</strong>`;
}
```

## Mejoras futuras

- Agregar estilos CSS para mejorar la apariencia.
    
- Permitir eliminar nombres de la lista.
    
- Guardar la lista en el almacenamiento local para que no se pierda al recargar la página.