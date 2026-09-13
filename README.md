# YAWARA! — Traducción al castellano

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Traducción al **español de España** de *YaWaRa! A Fashionable Judo Girl!* para **PC Engine CD**, a partir de la edición japonesa.

Se distribuye únicamente un **parche xdelta**. Necesitas tu propia copia del juego; no se incluyen imágenes de disco ni BIOS.

## Descarga y estado

**[v0.4-dev — Versión de desarrollo](https://github.com/johanderohan/yawara-traduccion-es/releases/tag/v0.4-dev)** · [Todas las descargas](https://github.com/johanderohan/yawara-traduccion-es/releases)

**La traducción todavía no está terminada.** Esta publicación permite probar el trabajo actual y está marcada como *prerelease*.

| Parte | Estado |
|---|---|
| Guion y menús extraídos | 21 bancos revisados y 2510 cadenas válidas reinsertadas, incluidas cadenas de control y dos bancos alternativos |
| Sistema | 81 textos traducidos |
| Créditos | 87 referencias integradas, incluidas líneas vacías; un nombre conserva su escritura japonesa por lectura no resuelta |
| Subtítulos adicionales | 185 llamadas para 184 recursos; borradores experimentales pendientes de revisión de audio, escena y ritmo |
| Criterios lingüísticos | Castellano de España, biblia de traducción y glosario de 153 entradas utilizados durante el trabajo |
| Texto dibujado en imágenes | Título, Nueva partida/Continuar, graduación, rótulos de Jigoro, periódico de felicitación, bibliotecas y aeropuerto traducidos; otros textos ambientales se conservan cuando la escena o el castellano los explican |

Las voces originales se mantienen en japonés. Quedan **13 lecturas vocales dudosas** sin integrar, además de recursos cuya habla o asociación todavía no está confirmada. Los recuentos anteriores no equivalen a un porcentaje global del juego.

## Comprobaciones

- Parche aplicado a la pista original y resultado idéntico, byte a byte, a la imagen probada; 498 sectores modificados con cabeceras y EDC/ECC verificados.
- Recorrido desde cero de la imagen publicada: 1.087.395 fotogramas, 2.407 aceptaciones de menú, capítulos principales hasta el final y regreso al guion inicial, sin error nativo registrado.
- Rótulos del aeropuerto comprobados en una partida nueva, guardado y carga dentro del juego y continuación a escenas posteriores.
- Guardar, cerrar RetroArch, abrir de nuevo, cargar la primera ranura y avanzar se comprobó en macOS con una construcción anterior identificada. No certifica todas las ranuras.
- Se mantiene la corrección del bloqueo anterior al subtítulo 1319 y el audio original del CD.

**No es una versión definitiva:** quedan ramas de contenido sin acreditar y revisión audiovisual de los subtítulos experimentales. El recorrido principal y las pruebas gráficas no sustituyen la revisión completa. Los textos japoneses de fondo conservados por contexto no se contabilizan como traducidos.

## Cómo aplicar el parche

El parche modifica **solo la pista 2** de la edición japonesa con siete archivos BIN y un CUE. No se aplica al CUE, a una imagen CHD ni a una copia ya traducida.

1. Descarga `yawara-es-0.4-dev.xdelta` de **[Releases](https://github.com/johanderohan/yawara-traduccion-es/releases/tag/v0.4-dev)**.
2. Comprueba la pista original antes de aplicar el parche:

   | Dato | Valor |
   |---|---|
   | Archivo | `YaWaRa! A Fashionable Judo Girl! (Japan) (Track 2).bin` |
   | Tamaño | 311.146.080 bytes |
   | SHA-256 original | `e6f5dcf08a0fcac4a682cba6f193bbc353e42a4a0340954771750eb9d1bd00b9` |

   En Linux: `sha256sum 'nombre del archivo.bin'`. En macOS: `shasum -a 256 'nombre del archivo.bin'`. En Windows: `CertUtil -hashfile "nombre del archivo.bin" SHA256`.

3. Crea una carpeta nueva, por ejemplo `Juego-ES`, y copia allí el **CUE y las pistas 1, 3, 4, 5, 6 y 7**, conservando sus nombres. Guarda los originales aparte.
4. Aplica el parche con xdelta3. Desde la carpeta que contiene la pista 2 original, el parche y `Juego-ES`:

   ```sh
   xdelta3 -d -s 'YaWaRa! A Fashionable Judo Girl! (Japan) (Track 2).bin' 'yawara-es-0.4-dev.xdelta' 'Juego-ES/YaWaRa! A Fashionable Judo Girl! (Japan) (Track 2).bin'
   ```

   El archivo de salida es la nueva pista 2, dentro de `Juego-ES`, con el nombre que espera el CUE.
5. Comprueba el SHA-256 de la pista resultante:

   ```text
   2f660930bcd5ddae9b6839e1617c39c4e0dcb72f8e920822d9776a3f9791a375
   ```

6. Abre el **CUE de `Juego-ES`** en tu emulador de PC Engine CD. La carpeta debe contener las siete pistas; abrir un BIN aislado puede dejar fuera las pistas de audio.

Para copiar el juego a otro dispositivo, conserva la carpeta completa y configura por separado tu BIOS `syscard3.pce`. Arranca desde cero, sin cargar estados rápidos de versiones anteriores.

SHA-256 del parche:

```text
74bdf1c56af7956318b25dcb7933b2af053cf263c209380ebc864bae5e9f6934
```

## Aviso

Proyecto de traducción hecho por afición, sin afiliación con los titulares del juego. Se conservan los derechos y créditos de sus autores. Aquí se publica solo el parche; no se distribuyen el juego, sus pistas de audio ni la BIOS.

Puedes comunicar errores mediante [Issues](https://github.com/johanderohan/yawara-traduccion-es/issues), indicando versión, emulador, escena y pasos para reproducirlos.
