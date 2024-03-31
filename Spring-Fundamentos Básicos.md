## Agregar Dependencia Thymeleaf:

![image](https://github.com/Pierohc/GTICS/assets/133154904/4f057399-3d36-4ef2-99fa-75dc22646b70)

## Estructura Básica de un Controller:

![image](https://github.com/Pierohc/GTICS/assets/133154904/7dc33501-adfd-4e93-955f-d486fe1ea850)

![image](https://github.com/Pierohc/GTICS/assets/133154904/435feb47-2b48-4310-9fc0-2d7787c2cf80)


## Ruteo:

![image](https://github.com/Pierohc/GTICS/assets/133154904/a2e69cb3-5570-4d67-811f-6b3973a49a4d)

------------------------------------

![image](https://github.com/Pierohc/GTICS/assets/133154904/3982e2bd-60e7-4d55-8557-f3a00fca633f)

### Ejemplo con método GET: 

![image](https://github.com/Pierohc/GTICS/assets/133154904/aaae6463-12ee-4524-a556-b02410b891fd)


![image](https://github.com/Pierohc/GTICS/assets/133154904/6a5a192a-9aff-4197-adee-f5aefd9f2058)

## Recepción de parámetros por GET y POST:

En Spring existen dos formas de recibir parámetros en la URL:
@RequestParam
@PathVariable

## Recibir por get especificando que no es obligatorio que esten los parametros en la url, esto para poder acceder a main sin parámetros(main?email=...)

![image](https://github.com/Pierohc/GTICS/assets/133154904/2218293a-5129-4211-94e5-4a5d14a4c751)

## POST:

La ubicacion del metodo Post o de cualquiera, no importa, puede estar arriba o debajo del metodo get que mande a esa pagina donde está el formulario POST.


![image](https://github.com/Pierohc/GTICS/assets/133154904/eae83eb4-755e-4b8d-8e98-1f9cbacdef5e)

![image](https://github.com/Pierohc/GTICS/assets/133154904/f5cd61c8-7983-44b8-9e23-271ba4f48bb4)


Si tenemos un formulario sin required(HTML), algunos parametros no serán obligatoriamente enviados, lo cual puede causar un error al dar clic en el boton submit. Para evitar ello es necesario especificar en el post Mapping que no es requerido dicho parametro, es decir, no es obligatorio al envio del POST: 


![image](https://github.com/Pierohc/GTICS/assets/133154904/27687925-47f6-4bfd-b3d4-ab6471ac963e)


---------------------------------------

## Envio de informacion del controlador a la vista con el Objeto Model:

![image](https://github.com/Pierohc/GTICS/assets/133154904/a8fd5e65-27d0-475b-87f0-7fd051f22d0f)

![image](https://github.com/Pierohc/GTICS/assets/133154904/60368b91-5f62-4da8-9c1d-e79d5538b8c3)

![image](https://github.com/Pierohc/GTICS/assets/133154904/686393df-4f60-47b5-a995-3c75d43e3d33)

![image](https://github.com/Pierohc/GTICS/assets/133154904/81396b32-0178-405b-be19-1766e454b8e2)

![image](https://github.com/Pierohc/GTICS/assets/133154904/724ddc30-fde5-4744-bfd3-d881f966137f)

![image](https://github.com/Pierohc/GTICS/assets/133154904/92caa164-8d3c-4fe1-bcb5-25e3048aa7a5)

![image](https://github.com/Pierohc/GTICS/assets/133154904/cf10af54-d4bf-452f-83c9-432d1f47cc18)

## Enviar un Arraylist y verlo en una tabla:

![image](https://github.com/Pierohc/GTICS/assets/133154904/70275850-114e-42d2-8218-c6dcd639f3f8)

![image](https://github.com/Pierohc/GTICS/assets/133154904/327e497a-0c81-44b9-832c-6239750981b8)









