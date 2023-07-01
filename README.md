## DEBER REPLICAS
#### Integrantes:
- Juan Falconi
- Juan Gualotuña
- Heyer Tinoco

  LINK DE YOUTUBE: https://www.youtube.com/watch?v=kwAoLjbFRiY

Utilizando conexiones remotas crear un video detallado de la elaboración de los esquemas propuestos, utilizando web scraping  en páginas de una misma temática, por ejemplo, computadoras, juegos, deportes, ect. Almacenar dicha información en CouchDB.

* Generar una función de consulta
``` python
import requests
from bs4 import BeautifulSoup

def web_scraping(url):
    # Realizar la solicitud GET a la URL especificada
    response = requests.get(url)

    # Verificar si la solicitud fue exitosa (código de estado 200)
    if response.status_code == 200:
        # Crear el objeto BeautifulSoup con el contenido HTML de la página
        soup = BeautifulSoup(response.text, 'html.parser')

        # Realizar aquí la extracción de datos que necesites
links = soup.find_all('a')
data = []
for link in links:
	href = link.get('href')
	text = link.text
	data.append({'href': href,'text': text,'autor':'Juan Gualotuña'})

# Ejemplo de uso de la función
url = "https://edu.gcfglobal.org/es/informatica-basica/que-es-un-computador/1/"
web_scraping(url)

```


* El JSOn conformado para almacenarlo en CouchDB debe tener dos campos adicionales, uno con su nombre y otro con su apellido.

![[Pasted image 20230630233527.png]]
![Texto alternativo](Pasted%20image%2020230630233540.png)

![Texto alternativo](Pasted%20image%2020230630233540.png)

- Debe ingresar al menos 10K documentos.
![Texto alternativo](Pasted%20image%2020230630233855.png)

### REPLICAS

Se crearon tres bases de datos la primera base de datos llamada **target** y **source1**, **source2** 

* Base de datos **target**
![Texto alternativo](Pasted%20image%2020230630234209.png)
* Base de datos **source1**
![Texto alternativo](Pasted%20image%2020230630234234.png)
* Base de datos **source2**
![Texto alternativo](Pasted%20image%2020230630234334.png)
* Modelo de replicas
![Texto alternativo](Pasted%20image%2020230630234433.png)
![Texto alternativo](Pasted%20image%2020230630234727.png)
![Texto alternativo](Pasted%20image%2020230630234737.png)
![Texto alternativo](Pasted%20image%2020230630234746.png)

* Hamachi
![Texto alternativo](Pasted%20image%2020230630234836.png)
