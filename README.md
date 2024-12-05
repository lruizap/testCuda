# README: Verificar Instalación de CUDA

Este README guía paso a paso cómo comprobar que CUDA está correctamente instalado y funcionando en tu sistema, después de haber seguido los pasos de instalación.

---

## **Pasos Previos**
Para instalar CUDA y las bibliotecas necesarias, sigue estos pasos:

1. **Descargar y actualizar dependencias de la gráfica**
   - Asegúrate de tener los drivers de la gráfica actualizados. Puedes descargarlos desde los siguientes enlaces:
     - [Descargar CUDA](https://developer.nvidia.com/cuda-downloads)
     - [Descargar cuDNN](https://developer.nvidia.com/cudnn-downloads)

2. **Instalar PyTorch con soporte CUDA**
   - Sigue la guía oficial de instalación de PyTorch:
     - [Guía de instalación de PyTorch](https://pytorch.org/get-started/locally/#windows-pip)

---

## **Prueba de CUDA**
Una vez completada la instalación, verifica que CUDA esté funcionando correctamente con el siguiente script:

1. **Abrir un entorno Python**
   Si usas un entorno virtual, actívalo primero:
   ```bash
   source .venv/bin/activate    # Linux/Mac
   .venv\Scripts\activate      # Windows
   ```

2. **Ejecutar el siguiente código en Python:**
   ```python
   import torch

   # Verifica si CUDA está disponible
   print("¿CUDA está disponible?:", torch.cuda.is_available())

   # Obtén el nombre de la GPU si está disponible
   if torch.cuda.is_available():
       print("Nombre de la GPU:", torch.cuda.get_device_name(0))
   else:
       print("CUDA no está disponible. Revisa la instalación.")
   ```

3. **Salida esperada:**
   Si CUDA está configurado correctamente, deberías obtener una salida como esta:
   ```
   ¿CUDA está disponible?: True
   Nombre de la GPU: NVIDIA GeForce RTX 3060
   ```

---

## **Resolución de Problemas**
Si el script indica que CUDA no está disponible:
1. Revisa si los drivers de la GPU están actualizados.
2. Asegúrate de que las versiones de CUDA, cuDNN y PyTorch sean compatibles entre sí.
3. Consulta la documentación oficial de NVIDIA o PyTorch para solucionar problemas específicos:
   - [NVIDIA CUDA Documentation](https://docs.nvidia.com/cuda/)
   - [PyTorch Troubleshooting](https://pytorch.org/docs/stable/troubleshooting.html)

---

Este README está diseñado para confirmar que la instalación de CUDA es exitosa antes de proceder con otros proyectos.
