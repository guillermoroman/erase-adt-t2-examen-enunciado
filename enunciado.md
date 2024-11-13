
### Distribución de la nota
- 1p: git (4 commits)
- 2p: loadBooksFromJsonFile
- 2p: saveBooksToJsonFile
- 2p: printReportFromAuthor
- 1.5p: saveBooksToBinaryFile
- 1.5p: loadBooksFromBinaryFile

### Pruebas unitarias
Se han proporcionado test unitarios que evalúan cada uno de los métodos implementados en la clase `BookManager`. Superar cada uno de estos test significa una nota completa en el apartado correspondiente. En caso de no superar alguno, se atenderá al código para observar qué nota merece una implementación parcial si existe.

### Introducción
Queremos crear un sistema de gestión de una biblioteca que almacene información sobre sus libros, imprima informes sobre un autor, y gestione la persistencia en un archivo en formato JSON y en formato binario. Persistiremos objetos de una sola clase: `Book`.

### `Book`
Atributos:
- `title` (String)
- `author` (String)
- `year` (int)
Métodos: Necesitaremos todos los métodos que permitan a nuestros parseadores y serializadores persistir estos objetos.

### `BookManager`
La lógica de nuestro programa se encontrará en la clase `BookManager`.
Atributos:
- `books`: Contiene un ArrayList de objetos `Book`.
métodos
- `printReportFromAuthor`: Método que imprime una lista de los libros de un autor que recibe como argumento. No hace falta dar un formato especial; el toString que podemos crear por defecto es suficiente. Observar más abajo un ejemplo de archivo de salida.

### `Main`
Contendrá una serie de operaciones que nos ayudarán a visualizar y comprobar que nuestro programa se está ejecutando de forma adecuada. No tiene peso en la evaluación; para eso se utilizarán los test. Se incluye para comodidad del alumno; para tener una forma adicional de comprobar el funcionamiento más allá de las pruebas unitarias.

### Dependencias
Todas las dependencias necesarias figuran ya en el `pom.xml`.

### Archivos
`books.json`
```json
[ {  
  "titulo" : "Dune",  
  "autor" : "Frank Herbert",  
  "anio" : 1965  
}, {  
  "titulo" : "Neuromancer",  
  "autor" : "William Gibson",  
  "anio" : 1984  
}, {  
  "titulo" : "Foundation",  
  "autor" : "Isaac Asimov",  
  "anio" : 1951  
} ]
```

`books.json` tras añadir nuevos libros
```json
[ {  
  "titulo" : "Dune",  
  "autor" : "Frank Herbert",  
  "anio" : 1965  
}, {  
  "titulo" : "Neuromancer",  
  "autor" : "William Gibson",  
  "anio" : 1984  
}, {  
  "titulo" : "Foundation",  
  "autor" : "Isaac Asimov",  
  "anio" : 1951  
}, {  
  "titulo" : "Dune Messiah",  
  "autor" : "Frank Herbert",  
  "anio" : 1969  
}, {  
  "titulo" : "Children of Dune",  
  "autor" : "Frank Herbert",  
  "anio" : 1976  
} ]
```

```Frank_Herbert_Report.txt```
```txt
Book{title='Dune', author='Frank Herbert', year=1965}  
Book{title='Dune Messiah', author='Frank Herbert', year=1969}  
Book{title='Children of Dune', author='Frank Herbert', year=1976}
```

Ejemplo de salida por consola con el main proporcionado
```txt
Cargando libros desde books.json...
Libros cargados:
Book{title='Dune', author='Frank Herbert', year=1965}
Book{title='Neuromancer', author='William Gibson', year=1984}
Book{title='Foundation', author='Isaac Asimov', year=1951}
Book{title='Dune Messiah', author='Frank Herbert', year=1969}
Book{title='Children of Dune', author='Frank Herbert', year=1976}
Informe guardado en Frank_Herbert_report.txt
Libros guardados en formato binario en books.bin
Cargando libros desde el archivo binario...
Libros cargados desde el archivo binario books.bin
Libros cargados desde el archivo binario:
Book{title='Dune', author='Frank Herbert', year=1965}
Book{title='Neuromancer', author='William Gibson', year=1984}
Book{title='Foundation', author='Isaac Asimov', year=1951}
Book{title='Dune Messiah', author='Frank Herbert', year=1969}
Book{title='Children of Dune', author='Frank Herbert', year=1976}
Book{title='Dune Messiah', author='Frank Herbert', year=1969}
Book{title='Children of Dune', author='Frank Herbert', year=1976}

Process finished with exit code 0
```
