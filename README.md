# Instalar Diccionario Español a WPS Office

Cuando uno descarga el diccionario español España para WPS Office desde:

http://wps-community.org/download/dicts

Nota: A esta fecha 23 de Noviembre del 2019 han retirado esa url no se porqué.

no funciona para WPS Office 2019 por estar vacío el contenido de "main.dic"(que no tenía nada) por esta razón he adaptado el paquete "hunspell-es" (el cual es el diccionario de corrección ortográfica español para LibreOffice) desde los repositorios de Ubuntu:

http://archive.ubuntu.com/ubuntu/pool/main/libr/libreoffice-dictionaries/hunspell-es_6.0.3-3_all.deb 

para que funcione como diccionario para WPS Office es necesario copiar la carpeta es_ES a los diccionarios de correción de WPS.

# Instalación en Linux
En mi caso estoy corriendo WPS Office 2019 (v11.1.0.9615) *Manjaro 20.1 Mikah* cuando voy a **Tools>Set language>** unicamente encuentro como lenguajes disponibles *English (United States)* 

![SpellCheck](./spellcheck.png?raw=true)

El directorio donde se encuentran los diccionarios para WPS Office es `/usr/lib/office6/dicts/spellcheck/`, revisamos las unicas carpetas que se encuentran son en-EN, revisamos su contenido:
```bash
ls /usr/lib/office6/dicts/spellcheck/en_US                                                                       
Changelog_en_US.txt  dict.conf	main.aff  main.dic  README_en_US.txt
```
- Clonamos el repo:
```bash
git clone https://github.com/dmunoz166/Dict-es_ES-WPSOffice.git
```
- Copiamos la carpeta `es_ES` al directorio de instalación, por que necesitaremos permisos de super usuario:

```
sudo cp -r ./Dict-es_ES-WPSOffice/es_ES /usr/lib/office6/dicts/spellcheck/
```
- Reiniciamos WPS para verificiar que podemos ver el nuevo dicccionario 

![SpellCheck](./spellcheck1.png?raw=true)


