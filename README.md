# Guide till Godot för 2D-spelutveckling

## Introduktion
Godot är en kraftfull och öppen källkod spelmotor som stöder både 2D och 3D-spelutveckling. Den erbjuder en flexibel nodbaserad arkitektur, inbyggt GDScript-programmeringsspråk och ett lättanvänt gränssnitt.

## Installation
1. Ladda ner Godot från [Godots officiella webbplats](https://godotengine.org/).
2. Installera och öppna programmet.
3. Skapa ett nytt projekt och välj en katalog för ditt spel.

## Grundläggande koncept
### Noder och Scener
- **Allt i Godot bygger på noder.**
- En scen kan innehålla flera noder.
- Exempel på vanliga noder:
  - `Node2D` - Grundläggande nod för 2D-spel
  - `Sprite2D` - Hanterar bilder och texturer i 2D

### GDScript
- Ett lättviktigt, Python-liknande skriptspråk som används för att programmera logik.
- Exempel på ett enkelt skript:

```gdscript
extends Node2D

func _ready():
    print("Spelet startar!")
```

## 2D-Spelutveckling
### Skapa en spelkaraktär
1. Lägg till en `Node2D` som root-nod.
2. Lägg till en `Sprite2D` och ladda en textur.
3. Lägg till en `CollisionShape2D` för kollisioner.
4. Lägg till en `KinematicBody2D` för rörelse.

### Enkel rörelse
```gdscript
extends KinematicBody2D

var speed = 200
var velocity = Vector2.ZERO

func _process(delta):
    velocity = Vector2.ZERO
    if Input.is_action_pressed("ui_right"):
        velocity.x += speed
    if Input.is_action_pressed("ui_left"):
        velocity.x -= speed
    move_and_slide(velocity)
```

## Viktiga aspekter
- **Signals och Events:** Använd `signals` för att hantera händelser.
- **Scenhantering:** Återanvänd scener för bättre struktur.
- **Fysikmotor:** Godot har inbyggd fysik för både 2D och 3D.
- **Export:** Exportera spel till Windows, Linux, macOS, Android och HTML5.

## Slutsats
Godot är en kraftfull och flexibel spelmotor som erbjuder verktyg för både 2D och 3D-utveckling. Genom att förstå nodbaserad arkitektur, GDScript och fysikmotorn kan du snabbt skapa spel av hög kvalitet.

## Tutorial: Första 2D Spel
Gå igenom tutorialen ditt första 2D spel: [https://docs.godotengine.org/en/stable/getting_started/first_2d_game/index.html](https://docs.godotengine.org/en/stable/getting_started/first_2d_game/index.html)

För att först få en bekantskap med Godot.

Föredrar man video-tutorials är den här serien fantastisk för 2D spel med Godot:

[https://www.youtube.com/playlist?list=PL4cUxeGkcC9iHCXBpxbdsOByZ55Ez4bgF](https://www.youtube.com/playlist?list=PL4cUxeGkcC9iHCXBpxbdsOByZ55Ez4bgF)


## Kravuppfyllelse på 2D spelet
Ni får återskapa ett känt spel om ni vill, men inte hämta klar kod från nätet.
Eller så väljer ni hitta på ett eget spel. Efter ni har gått igenom tutorialen och vi har byggt ett enkelt spel tillsammans kan man börja planera spelet steg 0.
### 0. Planering
Planera spelet, skapa ett dokument med beskrivning och skiss hur ni vill att spelet ska fungera och se ut. 
Få godkännande från läraren. Resten är saker som spelet måste uppfylla.
### 1. Grundläggande spelmekanik
Spelarens rörelse – Piltangenter, WASD eller touch-input för rörelse.
Kollisionsdetektion – Säkerställa att objekt interagerar korrekt (t.ex. spelaren krockar med väggar).
Grundläggande mål – Ett enkelt mål som att nå en mållinje, samla föremål eller undvika hinder.
Vinst-/förlustvillkor – Ett sätt att avgöra om spelaren vinner eller förlorar.
### 2. Enkel grafik
Sprites – Enkla 2D-bilder för spelaren, fiender och bakgrund.
Tileset (valfritt) – Om spelet använder en tile-baserad miljö.
Minimala animationer – Åtminstone en enkel stillastående/rörelseanimation.
### 3. Grundläggande användargränssnitt (UI)
Startskärm – En enkel titelskärm med en "Starta"-knapp.
Game over-skärm – Ett meddelande när spelaren vinner eller förlorar.
HUD (valfritt) – Poängräknare, timer eller hälsovisning.
### 4. Enkla ljudeffekter och musik
Ljud för hopp, insamling eller kollisioner.
Bakgrundsmusik (slinga eller enkel låt).
### 5. Enkel AI eller spelelement (valfritt)
Grundläggande fienderörelse – Fiender rör sig vänster/höger eller jagar spelaren.
Samlarföremål – Mynt, stjärnor eller andra objekt.
Enkel fysik – Hopp/gravitationssystem om nödvändigt.
### 6. Scen- och nivåhantering
Enkla scenövergångar – Växla mellan nivåer eller starta om spelet.
Respawn eller återställning av spelet vid behov.
### 7. Byggas och distribueras
Byggas och distribueras som en .exe fil för andra att kunna testa spelet.

