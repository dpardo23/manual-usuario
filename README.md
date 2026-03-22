# Plantilla de Manual de Usuario - Estándar ISO/IEC/IEEE 26514:2022

## Logo
![Logo Byte Busters](assets/img/bytebusters/logo_horizontal.png)

## Insignias
[![LaTeX](https://img.shields.io/badge/LaTeX-Project-008080.svg?style=flat&logo=latex&logoColor=white)](https://www.latex-project.org/)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![Standard: ISO 26514](https://img.shields.io/badge/Standard-ISO/IEC/IEEE_26514-blue)](https://www.iso.org/standard/79555.html)

## Perfil de Github - Introducción
Este repositorio proporciona una infraestructura técnica en **LaTeX** diseñada para generar manuales de usuario profesionales que cumplan estrictamente con el estándar internacional **ISO/IEC/IEEE 26514:2022**. Está optimizado para la empresa **Byte Busters S.R.L.** en el marco de la Facultad de Ciencias y Tecnología de la UMSS.

## Características
* **Cumplimiento Normativo:** Implementa la estructura de contenido jerárquica obligatoria por la norma ISO.
* **Identidad Visual:** Tipografías corporativas preconfiguradas (Helvetica para títulos, Times para cuerpo y Courier para código).
* **Diseño de Layout:** Márgenes exactos de 3cm (interno) y 2cm (externo) con interlineado de 1.5.
* **Componentes de Usabilidad:** Macros visuales para avisos de seguridad y consejos de productividad.
* **Gestión de Compilación:** Redirección automática de archivos auxiliares a la carpeta `/build` para mantener el directorio limpio.

## Tecnología
* **Lenguaje de Marcado:** LaTeX.
* **Motor de Compilación:** `pdflatex` con soporte para `minted` mediante `-shell-escape`.
* **Automatización:** `latexmk` para gestión de dependencias y `Makefile` para atajos de terminal.
* **Editor:** Visual Studio Code con extensión *LaTeX Workshop*.

## Perfil de Github - Habilidades
* **Software Documentation:** ISO/IEC/IEEE 26514.
* **Typesetting:** LaTeX, BibTeX.
* **Project Management:** Estructura organizada para Taller de Ingeniería de Software (TIS).

## Instalación
Para utilizar esta plantilla localmente, clona el repositorio y asegúrate de tener una distribución de LaTeX instalada (TeX Live o MiKTeX):

```bash
git clone [https://github.com/dpardo23/manual-usuario.git](https://github.com/dpardo23/manual-usuario.git)
cd manual-usuario
```

## Corre Localmente
Utiliza el `Makefile` o `latexmk` incluido para gestionar el ciclo de vida del documento:

```bash
# Compilar el manual completo
latexmk -pdf -outdir=build main.tex 

# Limpiar archivos temporales y la carpeta build
make clean
```

## Ejecutando Pruebas
Para validar que el entorno está correctamente configurado (especialmente el paquete `minted` y el motor `pdflatex`), ejecute:
1. `make clean`
2. `make all`
3. Verifique la existencia del PDF en `build/main.pdf`.

## Uso/Ejemplos
La plantilla incluye componentes especiales diseñados para captar la atención del usuario según el nivel de riesgo o importancia:

```latex
\begin{AvisoNota}
Consejo de productividad o información adicional de valor.
\end{AvisoNota}

\begin{AvisoPrecaucion}
Instrucción crítica para evitar errores operacionales menores.
\end{AvisoPrecaucion}

\begin{AvisoAdvertencia}
Advertencia de seguridad para prevenir pérdida de datos o daños graves.
\end{AvisoAdvertencia}
```

## Variables de Entorno
La configuración del flujo de trabajo se define en `.latexmkrc`:
* `$out_dir = 'build'`: Todos los binarios y archivos temporales se guardan aquí.
* `$pdf_mode = 1`: Fuerza la generación de salida en formato PDF.

## Capturas de Pantalla
El diseño final respeta los siguientes estándares de identidad corporativa:
* **Encabezados:** Logo de Byte Busters S.R.L. a la izquierda y versión del sistema a la derecha.
* **Pie de Página:** Fecha de actualización, paginación dinámica y correo de soporte técnico.
* **Colores:** Cyan (#080852) para elementos primarios y Verde (#4CAF50) para resultados de éxito.

## Documentación
El documento maestro (`main.tex`) está dividido en las secciones obligatorias del estándar:
* **Portada:** Datos institucionales y de la empresa.
* **Tabla de Contenidos:** Índice jerárquico con enlaces digitales.
* **Introducción:** Alcance y convenciones tipográficas.
* **Información General:** Requisitos y descripción funcional.
* **Instrucciones de Uso:** Procedimientos paso a paso.
* **Resolución de Problemas:** Diagnóstico y soluciones.
* **Apéndices:** Información complementaria y soporte.

## Hoja de Ruta
* [ ] Implementación de Glosario automatizado.
* [ ] Integración de tablas de Requisitos Previos estandarizadas.
* [ ] Soporte para marcas de agua de "Confidencial" con opacidad inferior al 10%.

## Optimizaciones
* **SyncTeX:** Habilitado para navegación bidireccional entre el código fuente y el PDF generado.
* **Shell Escape:** Configurado para permitir la inyección de código fuente resaltado mediante Python Pygments.

## Relacionado
* Sitio Oficial de la Empresa TIS
* Guía de Estilo ISO/IEC/IEEE 26514:2022

## FAQ

**¿Por qué recibo un error al compilar código fuente?**
Asegúrese de tener instalado Python y la librería `pygments`, ya que el paquete `minted` los requiere mediante el comando `-shell-escape`.

**¿Cómo cambio el nombre del PDF de salida?**
Modifique la variable `DOCNAME` en el archivo `Makefile`.

## Lecciones
Durante el desarrollo de esta plantilla se priorizó la separación de intereses, moviendo toda la lógica de diseño a la carpeta `/config` para que el autor solo deba preocuparse por el contenido en `/sections`.

## Autores
* **Razón Social:** Byte Busters S.R.L.
* **Representante Legal:** Juan Diego Pardo Pozo
* **Consultor TIS:** Corina Justina Flores Villarroel

## Feedback y Apoyo
Para reportar errores o solicitar soporte técnico, escriba a: contacto.bytebusters@gmail.com.

## Licencia
Este proyecto se distribuye bajo la licencia CC0 1.0 Universal (Public Domain Dedication). Puedes copiar, modificar y distribuir el trabajo, incluso con fines comerciales, sin pedir permiso.
