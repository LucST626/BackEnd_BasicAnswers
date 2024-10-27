# BackEnd_BasicAnswers

### Envío de texto plano

Para enviar una cadena de texto plano desde el backend, puedes usar el método res.send(). Esto es útil cuando deseas devolver contenido simple como un mensaje de texto.
Ejemplo:

```

app.get('/texto', (req, res) => {
    res.send('Hola mundo, ejemplo sencillo!');
});
```

Luego, puedes acceder al texto navegando a la URL: http://localhost:3000/texto.

### Envío de objeto JSON

Para enviar datos en formato JSON, se utiliza el método res.json(). El navegador mostrará el JSON de forma cruda o formateada, dependiendo del navegador.
Ejemplo:

```

app.get('/json', (req, res) => {
    res.json({ mensaje: 'Hola, mundo!' });
});
```

Al navegar a http://localhost:3000/json, verás el contenido JSON directamente en el navegador.

### Envío de archivo

Para enviar un archivo (como una imagen o documento), puedes usar res.sendFile(). Este método es útil para enviar cualquier tipo de archivo al cliente.
Ejemplo:

```

const path = require('path');

app.get('/archivo', (req, res) => {
    res.sendFile(path.join(__dirname, 'public', 'gatito.jpg')); 
});
```

Asegúrate de incluir el módulo path para manejar las rutas de archivos correctamente. Al acceder a http://localhost:3000/archivo, el navegador mostrará o descargará el archivo.

### Envío de estado específico

Para enviar una respuesta con un código de estado específico (como un error 404), usa el método res.status() junto con res.send(). Esto permite controlar qué mensaje se muestra según el estado.
Ejemplo:

```

app.get('/error', (req, res) => {
    res.status(404).send('No encontrado');
});
```

Al visitar http://localhost:3000/error, el navegador mostrará un mensaje con el estado 404, indicando que el recurso no fue encontrado.

### Redirección a otra URL

Para redirigir a otra URL desde el servidor, puedes utilizar res.redirect(). Esto le indica al navegador que visite una nueva ruta automáticamente.
Ejemplo:

```

app.get('/redirigir', (req, res) => {
    res.redirect('/otra-ruta');
});
```
```
app.get('/otra-ruta', (req, res) => {
    res.send('Has sido redirigido.');
});
```

Al acceder a http://localhost:3000/redirigir, serás redirigido automáticamente a http://localhost:3000/otra-ruta.


### Envío de HTML

Si deseas enviar código HTML para que el navegador lo renderice, simplemente usa res.send() con una cadena que contenga el HTML.
Ejemplo:

```

app.get('/html', (req, res) => {
    res.send('<h1>Has enviado HTML!</h1>');
});
```

Al acceder a http://localhost:3000/html, el navegador renderizará el contenido HTML, en este caso, un título con el texto "Has enviado HTML!".