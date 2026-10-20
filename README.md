# Compresor de Imágenes

Versión web de `CompresorImagenes`: comprime carpetas completas de imágenes desde el navegador.

**Abrir:** https://suz4ngg.github.io/compresor-imagenes/

Todo se procesa en tu navegador. Las imágenes no se suben a ningún servidor.

## Cómo se usa

1. **Carga las imágenes.** Arrastra una carpeta a la página o usa *Elegir carpeta* / *Elegir imágenes*. Acepta JPG, PNG y WebP, incluidas las subcarpetas, e ignora los demás archivos.
2. **Ajusta la compresión.**
   - **Calidad** de 1 a 100 (75 por defecto).
   - **Ancho máximo** en píxeles (1920 por defecto): solo se reducen las imágenes más anchas y la altura se ajusta en proporción.
   - **Formato de salida:** JPG o WebP.
   - **Nombres de salida:**
     - *Una sola carpeta*: `carpeta_nombre.jpg`, con los espacios cambiados por `_`, igual que el binario `CompresorImagenes`.
     - *Conservar subcarpetas*: mantiene la estructura original.
   - Opción para conservar el original cuando la versión comprimida pesa más.
3. **Comprime y revisa.** Cada imagen muestra el peso antes y después y el porcentaje de ahorro. Toca una miniatura para abrir el comparador antes/después, con opción de verla a tamaño real.
4. **Descarga.**
   - *Descargar ZIP* genera `<carpeta>-compressed.zip`.
   - *Guardar en carpeta…* escribe `<carpeta>-compressed` directo en la carpeta que elijas. Funciona en Chrome y Edge.

## Equivalente en terminal

La página muestra el comando del binario original con los mismos ajustes:

```bash
./CompresorImagenes "<origen>" "<origen>-compressed" 75 1920
```

El binario solo genera JPG en una sola carpeta y no está incluido en este repo.

## Detalles

- Es un solo archivo, `index.html`, sin dependencias ni proceso de build. También funciona abriéndolo localmente.
- Para que las fotos no se vean pixeladas, la reducción se hace en pasos sucesivos a la mitad.
- Al convertir a JPG, las partes transparentes de los PNG quedan con fondo blanco.
- Los pesos pueden variar un poco respecto al binario, porque se usa el codificador JPG del navegador y no ImageSharp.
