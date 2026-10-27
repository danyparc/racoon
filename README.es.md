# Racoon

> **Un ecosistema completo de producción musical de código abierto.**  
> Una estación de trabajo de audio digital (DAW) enfocada en el arreglo y la composición, acompañada por una suite de 11 plugins de instrumentos y efectos profesionales (formatos VST3, Audio Unit y Standalone).

[English](README.md) | [Español](README.es.md)

[![Compilación macOS](https://img.shields.io/badge/plataforma-macOS%20%7C%20Windows%20%7C%20Linux-blue.svg)](https://github.com)
[![Licencia DAW: GPL v3](https://img.shields.io/badge/Licencia%20DAW-GPLv3-green.svg)](estudio/LICENSE)
[![Licencia Plugins: AGPL v3](https://img.shields.io/badge/Licencia%20Plugins-AGPLv3-yellow.svg)](plugins/LICENSE)
[![Idioma](https://img.shields.io/badge/Idioma-Espa%C3%B1ol%20%7C%20English-orange.svg)](#idioma--language)

<p align="center">
  <img src="docs/images/racoon-studio.jpg" alt="Interfaz de Estudio Racoon DAW" width="100%">
</p>

*Para consultar el registro de cambios histórico y la documentación original sin formato, revisa [`LEEME.txt`](LEEME.txt).*

---

## Índice

- [Descripción General](#descripción-general)
- [La Familia de los 11 Plugins](#la-familia-de-los-11-plugins)
- [Estudio Racoon (El DAW)](#estudio-racoon-el-daw)
- [Funcionalidades Principales](#funcionalidades-principales)
  - [Composición y Arreglo Inteligente](#composición-y-arreglo-inteligente)
  - [De Tarareo a Rola (Voz y Ritmo a Stems)](#de-tarareo-a-rola-voz-y-ritmo-a-stems)
  - [Modo DJ y Mezcla Armónica](#modo-dj-y-mezcla-armónica)
  - [Mezcla y Masterización Automáticas](#mezcla-y-masterización-automáticas)
  - [Separación de Pistas (Stems) sin Conexión](#separación-de-pistas-stems-sin-conexión)
  - [Muestras Racoon y Certificado de Rola Limpia](#muestras-racoon-y-certificado-de-rola-limpia)
- [Instalación y Configuración](#instalación-y-configuración)
  - [macOS (Instalador en un Clic)](#macos-instalador-en-un-clic)
  - [Windows](#windows)
  - [Linux](#linux)
- [Estructura del Repositorio](#estructura-del-repositorio)
- [Procesamiento Digital de Señales (DSP)](#procesamiento-digital-de-señales-dsp)
- [Atribuciones y Licencias](#atribuciones-y-licencias)

---

## Descripción General

**Racoon** es una suite de creación musical integral diseñada para productores, compositores, diseñadores de sonido y músicos en vivo. Consta de tres pilares fundamentales:

1. **Estudio Racoon (`estudio`)**: Un DAW de alto rendimiento centrado en la línea de tiempo y la maqueta, desarrollado con JUCE y Tracktion Engine. Incluye edición de clips, estiramiento temporal (warp), asignación de ruteos de mezcla, separación neuronal de pistas y más de 55 efectos DSP nativos.
2. **Suite de Plugins Racoon (`plugins`)**: 11 instrumentos y procesadores basados en animales, disponibles en VST3, Audio Unit y aplicaciones independientes, listos para trabajar tanto dentro de Racoon como en cualquier DAW externo (Ableton Live, Logic Pro, Reaper, FL Studio, Bitwig, Cubase).
3. **Muestras Racoon (`muestras`)**: Una biblioteca de audio 100% libre de regalías con más de 3,060 golpes reales de batería y percusión, 76 instrumentos cromáticos multi-muestreados en formato SFZ, más de 5,000 formas de onda de ciclo único y tablas de ondas, y 1,210 efectos y transiciones específicas por género.

---

## La Familia de los 11 Plugins

Todos los plugins comparten la misma experiencia de uso: reproducción independiente con demos de fábrica precargados, deshacer/rehacer ilimitado, secuenciador por pasos / piano roll de 1 a 8 compases, entrada por teclado de computadora, automatización fluida por MIDI CC y el botón de transferencia directa **«A la maqueta» / «Devolver al clip»**.

| Plugin | Animal y Rol | Tipo | Capacidades Clave |
| :--- | :--- | :--- | :--- |
| **Racoon - Badger Bass** | Tejón (Bajo Ácido) | Instrumento | Sintetizador de bajo analógico estilo 303 con dos osciladores, sub-oscilador, deriva analógica, saturación con sobremuestreo y secuenciador con slides y acentos. |
| **Racoon - Hamster Drums** | Hámster (Caja de Ritmos) | Instrumento | Caja de ritmos de 16 pistas con salidas individuales, múltiples capas de velocidad, subcapas de grave y transitorios alineados en fase, moldeado ADSR y 42 kits de fábrica. |
| **Racoon - Dormouse Pads** | Lirón (Pads y Atmósferas) | Instrumento | Sintetizador de pads con tablas de ondas, motor granular, unísono con apertura estéreo, osciladores VA con tablas limitadas en banda, deriva analógica, 4 envolventes y 4 LFOs. |
| **Racoon - Squirrel Sampler** | Ardilla (Muestreador Cromático) | Instrumento | Reproductor de instrumentos en formato SFZ, mapas de zonas por velocidad y nota, alternancias round-robin, cortes por transitorios y remuestreo sinc de 32 puntos (-124 dB de ruido). |
| **Racoon - Ferret Guitar** | Hurón (Guitarra Modelada y Grabada) | Instrumento | Modelado físico y 5 guitarras grabadas (Acústicas, Eléctricas limpias y distorsionadas, Nylon), 7 estilos de rasgueo y arpegio, 10 articulaciones (palm mute, armónicos, slides), pedalera de 8 efectos y simulación de amplificadores y gabinetes. |
| **Racoon - Porcupine Choir** | Puercoespín (Coro y Ensamble) | Instrumento | Ensamble vocal y coro SATB con conducción armónica de voces sin saltos, armonizador de melodías, transiciones de vocales y sílabas, posicionamiento en escenario y 8 salidas independientes. |
| **Racoon - Chipmunk Chords** | Ardilla Listada (Teclados y Acordes) | Instrumento / MIDI | Generador de progresiones de acordes, arpegiador inteligente y rasgueo (strum), con 10 instrumentos acústicos y sintetizados (pianos de cola, verticales, FM, clavecín, cuerdas, marimba). Emite MIDI polifónico a otros instrumentos. |
| **Racoon - Mole Rhythm** | Topo (Ritmo y Percusión) | Instrumento / MIDI | Laboratorio de groove con 16 carriles euclidianos o dibujados, probabilidad de disparo, repeticiones (ratchets), micro-tiempos de swing y generador de percusión acústica y sintética. |
| **Racoon - Skunk Sound Design** | Mofeta (Laboratorio de Sonido) | Efecto de Audio | Procesador experimental con captura en tiempo real, síntesis granular, congelamiento espectral, morphing tímbrico, buffer de fallos rítmicos (glitch) y matriz de modulación de 64 destinos. |
| **Racoon - Hedgehog Mastering** | Erizo (Suite de Masterización) | Efecto Máster | Procesador de finalización para el bus máster. Incluye el macro «Partícula» de un solo mando, ecualizador dinámico de 12 bandas, compresor multibanda de 6 bandas, domador de resonancias, match EQ y medidor EBU R128 y de pico real. |
| **Racoon - Chinchilla Vocals** | Chinchilla (Procesador Vocal) | Efecto Vocal | Afinación vocal en tiempo real, editor gráfico de curvas de tono, desplazamiento de formantes, 8 voces de armonización inteligente, duplicador, vocoder, talkbox y picador rítmico (chopper). |

---

## Estudio Racoon (El DAW)

Racoon elimina la complejidad de ventanas flotantes innecesarias y se concentra en la velocidad de producción y composición:

```
+------------------------------------------------------------------------------------+
| Barra Superior: Transporte | BPM | Compás | Rueda Camelot | Armonizar | Exportar   |
+--------------------------+---------------------------------------------------------+
| Navegador / Biblioteca   | Vista de Maqueta y Arreglo                              |
| - 11 Plugins Racoon      | Canal 1: Bombo y Sub  [■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■]  |
| - 55 Efectos Nativos     | Canal 2: Batería      [  ■■■■  ■■■■  ■■■■  ■■■■  ■■■■ ]  |
| - Muestras Racoon        | Canal 3: Línea de Bajo[■■■■■■■■    ■■■■■■■■    ■■■■■■■■]  |
| - Transiciones y FX      | Canal 4: Acordes y Pad[==============================]  |
| - Audios del Proyecto    | Canal 5: Voz Principal[   ~~~~~~       ~~~~~~     ]  |
+--------------------------+---------------------------------------------------------+
| Panel Inferior: [ Piano Roll / Batería ]  [ Tarjetas del Canal y FX ]  [ Mezclador ]|
+------------------------------------------------------------------------------------+
```

- **Interfaz Integrada**: Todo el flujo de trabajo ocurre en una pantalla adaptable con pestañas inferiores (**Piano**, **Canal** y **Máster**).
- **55 Efectos Nativos en Español**: Dinámica (Compresor de bus, Multibanda, Puerta con ratio de expansor, Clipper), Ecualización (EQ de mezcla con curvas suaves, EQ de 8 bandas, Filtro automático), Distorsión analógica (ADAA a 4x en amplificadores, válvulas dinámicas y pedales de saturación), Espacio (Reverb híbrida FDN y Sala Real con respuestas de impulso convolutivas de OpenAIR) y herramientas de análisis.
- **Rueda de Camelot Interactiva**: Modificación de la tonalidad completa del proyecto en tiempo real (`Cmd + Mayús + K`). Los instrumentos, progresiones, notas y loops de audio se transponen al instante respetando las relaciones armónicas de la escala.

---

## Funcionalidades Principales

### Composición y Arreglo Inteligente
- **44 Géneros de Inicio Inmediato**: Crea al instante un bloque de 16 compases en estilos como House, Techno, Trap, Reggaetón, Drum & Bass, Lo-Fi, Synthwave, Afro House o Cumbia. Cada género carga una pieza única con patrones de batería auténticos, bajo, armonía y voces en su tonalidad óptima.
- **Botón ALEATORIA**: Algoritmo generativo y de variación musical no destructivo guiado por reglas de teoría musical (inversiones de acordes, conducción de voces, síncopas, notas de paso y preguntas y respuestas). Permite fijar pistas individuales mediante el botón **FIJAR**.
- **Crear la Rola Completa (`Cmd + Mayús + R`)**: Expande un loop de 16 compases a una estructura musical completa (Intro, Build-up, Drop, Breakdown, Build-up 2, Drop 2 y Outro) con automatizaciones de filtro, silencios de tensión y transiciones calculadas al tempo.

### De Tarareo a Rola (Voz y Ritmo a Stems)
- Graba 4 compases de melodía tarareando o silbando y 2 compases de ritmo con la boca (*"bu"* para bombo, *"pa"* para caja, *"ts"* para charles), o importa un archivo de audio.
- El algoritmo **YIN** analiza la frecuencia fundamental cada 10 ms, ajusta la afinación, detecta la escala y compone la progresión de acordes, instrumentando automáticamente la melodía en Squirrel y Chinchilla, el ritmo en Hamster y la armonía en bajo y teclados.

### Modo DJ y Mezcla Armónica
- Arrastra pistas en cualquier formato (WAV, AIFF, FLAC, MP3) a la ventana de Modo DJ (`Cmd + Opción + J`).
- Racoon calcula el tempo exacto a la centésima (ej. `126.00 BPM`), la clave en la rueda de Camelot (`8A`, `9B`) y el nivel de energía del 1 al 10.
- La función **"Ordenar el set"** organiza las pistas para transiciones armónicas con saltos de tempo inferiores al 6%, exporta listas de reproducción `.m3u` con guías de mezcla y puede generar temas de club de 128 compases específicos para transicionar entre canciones.

### Mezcla y Masterización Automáticas
- Función **Mezclar y masterizar (`Cmd + Opción + M`)**: Exporta internamente la canción, mide el balance espectral, la presencia (2 a 6 kHz), el subgrave y la apertura estéreo, e itera automáticamente aplicando ajustes en canales individuales y buses.
- Deja la mezcla ajustada a los estándares de distribución (-14 LUFS para Spotify/lo-fi/ambient; -10 LUFS para pistas de club, con pico real siempre contenido por debajo de -1 dBTP).

### Separación de Pistas (Stems) sin Conexión
- Integración nativa de la red neuronal **Demucs v4** a través de `demucs.cpp`.
- Al hacer clic derecho en un clip de audio y pulsar **«Separar en stems»**, Racoon aísla localmente y sin conexión las pistas de Voz, Batería, Bajo y Otros en cuatro canales independientes.

### Muestras Racoon y Certificado de Rola Limpia
- **Biblioteca Muestras Racoon**: Sonidos acústicos y electrónicos de alta resolución libres de reclamos de derechos de autor.
- **Certificado de Rola Limpia**: Al exportar tu tema, Racoon audita cada golpe y muestra que efectivamente suena en la canción, genera un reporte en texto con los autores, licencias originales (CC0, CC-BY, Dominio Público) listo para acreditar en plataformas de streaming o YouTube, y calcula la huella digital SHA-256 del máster.

---

## Instalación y Configuración

### macOS (Instalador en un Clic)

Requisitos: macOS 11.0 o superior (compatible de forma nativa con Apple Silicon M1/M2/M3/M4 y procesadores Intel). Se requiere tener instaladas las herramientas de línea de comandos de Xcode (`xcode-select --install`).

1. Clona o descarga el repositorio:
   ```bash
   git clone https://github.com/danyparc/racoon.git
   cd racoon
   ```
2. Haz doble clic en el archivo **`Instalar Racoon.command`** en el Finder, o ejecútalo desde la terminal:
   ```bash
   ./"Instalar Racoon.command"
   ```
3. El script se encargará automáticamente de:
   - Descargar el modelo neuronal de Demucs v4 para la separación de stems.
   - Ensamblar la biblioteca de muestras acústicas completa en `~/Music/Racoon/Muestras Racoon`.
   - Compilar los 11 plugins en formatos VST3 y Audio Unit, ubicándolos en `~/Library/Audio/Plug-Ins/`.
   - Compilar Estudio Racoon e instalarlo en `/Applications`.
   - Generar un archivo instalador universal `.dmg` dentro de la carpeta `Instalador/` listo para compartir.

### Windows

El repositorio incluye un flujo automatizado de GitHub Actions (`.github/workflows/windows.yml`) que compila `Racoon.exe` y los 11 plugins VST3 en servidores de integración continua.

Para compilar localmente con Visual Studio 2022:
```powershell
# 1. Descargar dependencias de audio
bash estudio/scripts/fetch_deps.sh

# 2. Compilar los 11 Plugins VST3
cmake -S plugins -B plugins/build-win -G "Visual Studio 17 2022" -A x64
cmake --build plugins/build-win --config Release --parallel

# 3. Compilar Estudio Racoon
cmake -S estudio -B estudio/build-win -G "Visual Studio 17 2022" -A x64
cmake --build estudio/build-win --config Release --target Racoon --parallel
```
Copia los archivos `.vst3` resultantes a `C:\Program Files\Common Files\VST3\` y la carpeta de muestras a `Documentos\Racoon\Muestras Racoon`.

### Linux

Se admite la compilación y ejecución de pruebas sin servidor gráfico utilizando Ninja:
```bash
git clone --depth 1 --branch 8.0.16-security https://github.com/juce-framework/JUCE.git plugins/JUCE
cmake -S plugins -B plugins/build-linux -G Ninja -DCMAKE_BUILD_TYPE=Release -DRF_TESTS=ON
cmake --build plugins/build-linux
```

---

## Estructura del Repositorio

```
racoon/
├── docs/
│   └── images/
│       └── racoon-studio.jpg   # Captura de pantalla de la interfaz de Estudio Racoon
├── Instalar Racoon.command     # Instalador y compilador automatizado para macOS
├── README.md                   # Documentación principal en inglés
├── README.es.md                # Documentación en español
├── LEEME.txt                   # Histórico de cambios y documentación original detallada
├── .github/
│   └── workflows/windows.yml   # Automatización CI de compilación para Windows
├── plugins/                    # Código fuente de los 11 plugins (C++ / JUCE)
│   ├── Plugins/                # Carpetas individuales de cada plugin:
│   │   ├── Badger/             #   Racoon - Badger Bass
│   │   ├── Chinchilla/         #   Racoon - Chinchilla Vocals
│   │   ├── Chipmunk/           #   Racoon - Chipmunk Chords
│   │   ├── Dormouse/           #   Racoon - Dormouse Pads
│   │   ├── Ferret/             #   Racoon - Ferret Guitar
│   │   ├── Hamster/            #   Racoon - Hamster Drums
│   │   ├── Hedgehog/           #   Racoon - Hedgehog Mastering
│   │   ├── Mole/               #   Racoon - Mole Rhythm
│   │   ├── Porcupine/          #   Racoon - Porcupine Choir
│   │   ├── Skunk/              #   Racoon - Skunk Sound Design
│   │   └── Squirrel/           #   Racoon - Squirrel Sampler
│   ├── Common/                 # Componentes DSP y de interfaz compartidos
│   ├── Shared/                 # Recursos y comunicación entre plugins
│   └── Tests/                  # Pruebas unitarias y contratos de estabilidad
├── estudio/                    # Código fuente del DAW Racoon Studio
│   ├── Source/                 # Motor de audio, secuenciador, mezclador e interfaz
│   ├── Resources/              # Gráficos, iconos y tipografías SIL Open Font
│   ├── ThirdParty/             # Dependencias externas (demucs.cpp, Eigen, etc.)
│   └── scripts/                # Scripts auxiliares de empaquetado y descargas
└── muestras/                   # Biblioteca de muestras de audio libres
    ├── bateria/                # Cajas, bombos y platillos reales y analógicos
    ├── percusion/              # Congas, shakers, bongós y percusión del mundo
    ├── instrumentos/           # Instrumentos cromáticos multi-muestreados en SFZ
    ├── salas/                  # Respuestas de impulso para convolución (OpenAIR)
    ├── ondas/                  # Ondas de ciclo único AKWF y tablas WaveEdit
    ├── efectos/                # Risers, impactos y transiciones acústicas y sintéticas
    ├── catalogo.json           # Índice y taxonomía de categorías
    ├── kits-racoon.json        # 360 recetas precalculadas de kits de batería
    └── CREDITOS.txt            # Relación pormenorizada de autores y licencias
```

---

## Procesamiento Digital de Señales (DSP)

- **Antialiasing por Antiderivada (ADAA)**: Implementación de algoritmos de primer orden (Parker, Zavalishin, Bilbao) en saturadores, pedales de distorsión y etapas de ganancia para suprimir el aliasing armónico sin requerir sobremuestreos excesivos que eleven el consumo de CPU.
- **Filtros TPT (Topology-Preserving Transform)**: Filtros de estado variable con integradores trapezoidales que permiten modulaciones y barridos de resonancia muestra a muestra sin artefactos ni escalonamientos audibles.
- **Osciladores PolyBLEP**: Supresión de aliasing en formas de onda de sierra, pulso y triángulo para emular la calidez de la síntesis analógica clásica.
- **Interpolación Sinc de 32 Puntos**: Remuestreo con ventana Kaiser en samplers y motores de reproducción, logrando una relación señal-ruido de hasta -124 dB.
- **Redes de Retardo con Realimentación (FDN)**: Matrices ortogonales Hadamard de 8 líneas para colas de reverberación densas, homogéneas y sin coloración metálica.
- **Medición Precisa EBU R128**: Algoritmos de volumen perceptual según el estándar ITU-R BS.1770-4 y cálculo riguroso de pico real (True Peak).

---

## Idioma / Language

Racoon cuenta con soporte nativo tanto para **Español** como para **Inglés**:
- Al abrir por primera vez la aplicación, podrás seleccionar tu idioma predilecto.
- Puedes alternarlo en cualquier momento desde el menú del engrane (**Ajustes > Idioma** / **Settings > Language**).
- Los 11 plugins sincronizan automáticamente el idioma seleccionado con el DAW anfitrión.

---

## Atribuciones y Licencias

- **Estudio Racoon (`estudio`)** está licenciado bajo la [Licencia Pública General GNU v3.0](estudio/LICENSE) (GPLv3).
- **Suite de Plugins Racoon (`plugins`)** está licenciada bajo la [Licencia Pública General Reducida Affero de GNU v3.0](plugins/LICENSE) (AGPLv3).
- **Algoritmos DSP y Código Adaptado**:
  - Algoritmos de análisis y procesamiento adaptados de [SoundCraft](https://github.com/storytold/soundcraft) (Licencia MIT).
  - Separación neuronal de fuentes basada en [Demucs](https://github.com/facebookresearch/demucs) y [demucs.cpp](https://github.com/Retrobear/demucs.cpp) (Licencia MIT).
  - Detección de tono YIN (A. de Cheveigné, H. Kawahara).
  - Perfiles de detección tonal Krumhansl-Schmuckler.
  - Respuestas de impulso acústicas provistas por el proyecto OpenAIR de la Universidad de York (CC-BY / Dominio Público).
- **Tipografías**: SIL Open Font License 1.1 (*JetBrains Mono, Alumni Sans, Dela Gothic One, Golos Text*).
- **Muestras de Audio**: Todas las muestras en `muestras` provienen de proyectos abiertos con licencias verificadas CC0, Dominio Público, CC BY o GPL. Consulta [`muestras/CREDITOS.txt`](muestras/CREDITOS.txt) para ver los créditos y orígenes específicos.
