# ¿No sabes imprimir en la salita?
## Necesitas:
-	Acceso a una cuenta anakena, si no sabes como, anda a [sistemas](https://sistemas.dcc.uchile.cl) en torre poniente 3er piso para que te ayuden a crear una.

-	Tu pdf favorito

## Manda tu documento a anakena:

-	Descargando el pdf desde el toqui, o
-	Ocupar safe copy (comando scp)

```bash
scp <nombre pdf> <nombre cuenta>@anakena.dcc.uchile.cl:~<directorio>
```

Donde \<nombre pdf> es el nombre de tu pdf favorito, \<nombre cuenta> es el nombre de tu cuenta dcc y <directorio> es la ubicación (directorio en linux) de donde se va copiar el archivo.

Un comando completo se vería asi:

```bash
scp actas.pdf pandita@anakena.dcc.uchile.cl:~/impresiones
```
Esto envía el archivo actas.pdf al directorio ~/impresiones, del usuario pandita.

## Transforma tu pdf a ps (PostScript):

-	Ingresa a anakena mediante ssh.

```bash
ssh <nombre cuenta>@anakena.dcc.uchile.cl
```
-	Ocupa el comando pdf2ps:
```bash
 pdf2ps <nombre pdf> <nombre ps>
```
 Donde \<nombre ps> es el nombre del nuevo documento ps.

## Imprime!

-	Ocupa el siguiente comando:
```
lpr -P hp-335 <nombre ps>.
```

## ¡Oye! Yo quiero imprimir en ambas caras 😔
-	Ocupa el siguiente comando si quieres imprimir por el lado largo:
```
duplex <nombre ps> | lpr -P hp-335
```
-	Ocupa el siguiente comando si quieres imprimir por el lado corto (l de landscape):

```
duplex -l <nombre ps> | lpr -P hp-335
```

### Ojalá haya resultado 😁😁 🙂‍↕️