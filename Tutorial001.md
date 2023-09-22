### @activities true

```template

let robotKrabbe: Sprite = null
tiles.setTilemap(tiles.createTilemap(hex`2000200000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000010101010101010100000000000000000000000000000000000000000000010101010101010101010100000000000000000000000000000000000000000101010101010101010101010000000000000000000000000000000000000001010101010101010101010101010000000000000000000000000000000000000101010101010101010101010101000000000000000000000000000000000000010101010101010101010101010100000000000000000000000000000000000000010101010101010101010101010100000000000000000000000000000000000001010101010101010101010101010100000000000000000000000000000000000101010101010101010101010101010101000000000000000000000000000000000101010101010101010101010101010100000000000000000000000000000000010101010101010101010101010101010000000000000000000000000000000000010101010101010101010101010101000000000000000000000000000000000000010101010101010101010101010100000000000000000000000000000000000001010101010101010101010101010000000000000000000000000000000000010101010101010101010101010100000000000000000000000000000000000001010101010101010101010101010000000000000000000000000000000000000001010101010101010101010100000000000000000000000000000000000000000000000001010101010100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`, img`
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
`, [myTiles.transparency16, sprites.castle.tilePath5], TileScale.Sixteen))
scene.setBackgroundColor(9)
let minRobot = sprites.create(img`
    . . . . . f f f f . . . . . 
    . . . f f 5 5 5 5 f f . . . 
    . . f 5 5 5 5 5 5 5 5 f . . 
    . f 5 5 5 5 5 5 5 5 5 5 f . 
    . f 5 5 5 d b b d 5 5 5 f . 
    f 5 5 5 b 4 4 4 4 b 5 5 5 f 
    f 5 5 c c 4 4 4 4 c c 5 5 f 
    f b b f b f 4 4 f b f b b f 
    f b b 4 1 f d d f 1 4 b b f 
    . f b f d d d d d d f b f . 
    . f e f e 4 4 4 4 e f e f . 
    . e 4 f 6 9 9 9 9 6 f 4 e . 
    . 4 d c 9 9 9 9 9 9 c d 4 . 
    . 4 f b 3 b 3 b 3 b b f 4 . 
    . . f f 3 b 3 b 3 3 f f . . 
    . . . . f f b b f f . . . . 
    `, SpriteKind.Player)
tiles.placeOnRandomTile(minRobot, sprites.castle.tilePath5)
controller.moveSprite(minRobot)
for (let index = 0; index < 4; index++) {
    robotKrabbe = sprites.create(img`
        . . . . . . . . . . . c c . . . 
        . . . . . . . c c c c 6 3 c . . 
        . . . . . . c 6 3 3 3 3 6 c . . 
        . . c c . c 6 c c 3 3 3 3 3 c . 
        . b 5 5 c 6 c 5 5 c 3 3 3 3 3 c 
        . f f 5 c 6 c 5 f f 3 3 3 3 3 c 
        . f f 5 c 6 c 5 f f 6 3 3 3 c c 
        . b 5 5 3 c 3 5 5 c 6 6 6 6 c c 
        . . b 5 5 3 5 5 c 3 3 3 3 3 3 c 
        . c c 5 5 5 5 4 c c 3 3 3 3 3 c 
        c 5 5 4 5 5 4 c 5 5 c 3 3 3 c . 
        b 5 4 b 4 4 4 c 5 5 5 b c c . . 
        c 4 5 5 b 4 4 c 5 5 5 c b b . . 
        c 5 5 5 c 4 c 5 5 5 5 c c 5 b . 
        c 5 5 5 5 c 4 c c c c c c 5 c . 
        . c c c c c c . . . . . c c c . 
        `, SpriteKind.Enemy)
    tiles.placeOnRandomTile(robotKrabbe, assets.tile`transparency16`)
    robotKrabbe.setVelocity(randint(-50, 50), randint(-50, 50))
    robotKrabbe.setBounceOnWall(true)
}

```

# Lag et krabberobotspill
## intro
### intro @unplugged

Robotkrabbene forsøker å overta verden! Du må stoppe dem! Vi har begynt å lage spillet for deg, men det er langt fra ferdig! Test spillet før du lærer hvordan du kan stoppe robotkrabbene.
I dette spillet møter du ordet ``||sprites:sprite||`` ganske ofte. En sprite er et bilde som brukes som en spillfigur i enkle spill.

### Angreknapp, flytting og sletting av blokker @unplugged

Om du gjør noe feil, eller angrer på at du la ut en blokk, finnes det en angreknapp nederst i høyre hjørne på skjermen.
Du kan også slette en blokk ved å trykke på den så den blir gul og så trykke "delete" på tastaturet.
Om du vil flytte en enkelt blokk inne i koden din, må du holde inne Ctrl på tastaturet mens du klikker og drar blokken dit du vil ha den.
Om du drar en blokk over menyen i midten og slipper den, sletter du blokken.
Husk at angreknappen finnes dersom du gjør noe du angrer på!

### Steg 1
Som du ser forsvinner roboten din ut av bildet om du går for langt nedover eller til høyre.
Hent blokken ``||scene:camera follow sprite mySprite||`` og sett den inn i koden under blokken ``||controller:move minRobot with buttons||``.
Klikk på feltet ``||variables:mySprite||`` på blokken og endre ``||variables:mySprite||`` til ``||variables:minRobot|`` ved å klikke på valget ``||variables:minRobot||``.
Nå holder roboten seg i midten av bildet helt til den treffer kanten av spillområdet.
Klikk på lyspæra under forklaringene for å se hvordan koden din skal se ut.
Klikk på "Next" for å gå videre.

```blocks
let robotKrabbe: Sprite = null
tiles.setCurrentTilemap(tilemap`level1`)
scene.setBackgroundColor(7)
let minRobot = sprites.create(img`
    . . . . . f f f f . . . . . 
    . . . f f 5 5 5 5 f f . . . 
    . . f 5 5 5 5 5 5 5 5 f . . 
    . f 5 5 5 5 5 5 5 5 5 5 f . 
    . f 5 5 5 d b b d 5 5 5 f . 
    f 5 5 5 b 4 4 4 4 b 5 5 5 f 
    f 5 5 c c 4 4 4 4 c c 5 5 f 
    f b b f b f 4 4 f b f b b f 
    f b b 4 1 f d d f 1 4 b b f 
    . f b f d d d d d d f b f . 
    . f e f e 4 4 4 4 e f e f . 
    . e 4 f 6 9 9 9 9 6 f 4 e . 
    . 4 d c 9 9 9 9 9 9 c d 4 . 
    . 4 f b 3 b 3 b 3 b b f 4 . 
    . . f f 3 b 3 b 3 3 f f . . 
    . . . . f f b b f f . . . . 
    `, SpriteKind.Player)
controller.moveSprite(minRobot)
// @highlight
scene.cameraFollowSprite(minRobot)
for (let index = 0; index < 4; index++) {
    robotKrabbe = sprites.create(img`
        . . . . . . . . . . . c c . . . 
        . . . . . . . c c c c 6 3 c . . 
        . . . . . . c 6 3 3 3 3 6 c . . 
        . . c c . c 6 c c 3 3 3 3 3 c . 
        . b 5 5 c 6 c 5 5 c 3 3 3 3 3 c 
        . f f 5 c 6 c 5 f f 3 3 3 3 3 c 
        . f f 5 c 6 c 5 f f 6 3 3 3 c c 
        . b 5 5 3 c 3 5 5 c 6 6 6 6 c c 
        . . b 5 5 3 5 5 c 3 3 3 3 3 3 c 
        . c c 5 5 5 5 4 c c 3 3 3 3 3 c 
        c 5 5 4 5 5 4 c 5 5 c 3 3 3 c . 
        b 5 4 b 4 4 4 c 5 5 5 b c c . . 
        c 4 5 5 b 4 4 c 5 5 5 c b b . . 
        c 5 5 5 c 4 c 5 5 5 5 c c 5 b . 
        c 5 5 5 5 c 4 c c c c c c 5 c . 
        . c c c c c c . . . . . c c c . 
        `, SpriteKind.Enemy)
    tiles.placeOnRandomTile(robotKrabbe, assets.tile`transparency16`)
    robotKrabbe.setVelocity(randint(-50, 50), randint(-50, 50)))
    robotKrabbe.setBounceOnWall(true)
}
```

### Steg 2
Du skal fange robotkrabbene. For å få til det trenger du blokken ``||Sprites:on sprite of kind Player overlaps otherSprite of kind Player||``. Hent den fra ``||sprites:Sprites||``-kategorien og legg den ved siden av resten av koden din.
Denne blokken skal ligge for seg selv.

```blocks
let robotKrabbe: Sprite = null
tiles.setCurrentTilemap(tilemap`level1`)
scene.setBackgroundColor(7)
let minRobot = sprites.create(img`
    . . . . . f f f f . . . . . 
    . . . f f 5 5 5 5 f f . . . 
    . . f 5 5 5 5 5 5 5 5 f . . 
    . f 5 5 5 5 5 5 5 5 5 5 f . 
    . f 5 5 5 d b b d 5 5 5 f . 
    f 5 5 5 b 4 4 4 4 b 5 5 5 f 
    f 5 5 c c 4 4 4 4 c c 5 5 f 
    f b b f b f 4 4 f b f b b f 
    f b b 4 1 f d d f 1 4 b b f 
    . f b f d d d d d d f b f . 
    . f e f e 4 4 4 4 e f e f . 
    . e 4 f 6 9 9 9 9 6 f 4 e . 
    . 4 d c 9 9 9 9 9 9 c d 4 . 
    . 4 f b 3 b 3 b 3 b b f 4 . 
    . . f f 3 b 3 b 3 3 f f . . 
    . . . . f f b b f f . . . . 
    `, SpriteKind.Player)
controller.moveSprite(minRobot)
scene.cameraFollowSprite(minRobot)
for (let index = 0; index < 4; index++) {
    robotKrabbe = sprites.create(img`
        . . . . . . . . . . . c c . . . 
        . . . . . . . c c c c 6 3 c . . 
        . . . . . . c 6 3 3 3 3 6 c . . 
        . . c c . c 6 c c 3 3 3 3 3 c . 
        . b 5 5 c 6 c 5 5 c 3 3 3 3 3 c 
        . f f 5 c 6 c 5 f f 3 3 3 3 3 c 
        . f f 5 c 6 c 5 f f 6 3 3 3 c c 
        . b 5 5 3 c 3 5 5 c 6 6 6 6 c c 
        . . b 5 5 3 5 5 c 3 3 3 3 3 3 c 
        . c c 5 5 5 5 4 c c 3 3 3 3 3 c 
        c 5 5 4 5 5 4 c 5 5 c 3 3 3 c . 
        b 5 4 b 4 4 4 c 5 5 5 b c c . . 
        c 4 5 5 b 4 4 c 5 5 5 c b b . . 
        c 5 5 5 c 4 c 5 5 5 5 c c 5 b . 
        c 5 5 5 5 c 4 c c c c c c 5 c . 
        . c c c c c c . . . . . c c c . 
        `, SpriteKind.Enemy)
    tiles.placeOnRandomTile(robotKrabbe, assets.tile`transparency16`)
    robotKrabbe.setVelocity(randint(-50, 50), randint(-50, 50))
    robotKrabbe.setBounceOnWall(true)
}
// @highlight
sprites.onOverlap(SpriteKind.Player, SpriteKind.Player, function (sprite, otherSprite) {
	
})
```

### Steg 3
Nå kommer det noen steg som er viktige, men som kan være litt vanskelige å huske.
Roboten din er en ``||sprites:sprite||`` av typen ``||sprites:player||``. "Kind" betyr "type" i programmeringsspråket
Robotkrabbene er ``||sprites:sprites||`` av typen ``||sprites:enemy||``. 
I blokken ``||Sprites:on sprite of kind Player overlaps otherSprite of kind Player||`` må du endre det siste feltet slik at det står ``||Sprites:on sprite of kind Player overlaps otherSprite of kind Enemy||``.
Klikk på ordet ``||sprites:Player||`` og velg ``||sprites:Enemy||`` fra menyen som dukker opp.

```blocks
// @highlight
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
	
})
```

### Steg 4
Den nye blokken gjør at du kan få noe til å skje når roboten din kolliderer med en robotkrabbe.
Det som skal skje koder du inni denne blokken.
For å få krabbene til å bli borte når du tar dem, trenger du en ``||sprites:destroy mySprite||``-blokk.
Hent en fra ``||sprites:Sprites||``-menyen og legg den inni  ``||Sprites:on sprite of kind Player overlaps otherSprite of kind Enemy||``-blokken.

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    let mySprite: Sprite = null
    // @highlight
    sprites.destroy(mySprite)
})
```

### Steg 5
Om du tester spillet nå, skjer det ingenting når du klarer å ta igjen en robotkrabbe.
For at spillet skal forstå at du vil fjerne krabben, må du dra det ovale feltet der det stå ``||variables:otherSprite||`` i blokken ``||Sprites:on sprite of kind Player overlaps otherSprite of kind Enemy||`` ned til feltet der det står ``||variables:mySprite||`` i blokken ``||sprites:destroy mySprite||``.
Nå kan du teste spillet igjen. Ser du at robotkrabbene blir borte når du klarer å ta dem?

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    let mySprite: Sprite = null
    // @highlight
    sprites.destroy(otherSprite)
})
```
### Steg 6
Siden dette er et spill, må du jo få poeng for hver robotkrabbe du fanger.
Da trenger du en poengblokk. den finner du i ``||info:Info||``-menyen.
Hent blokken ``||info:change score by 1||`` fra ``||info:Info||``-menyen, og plasser den inni ``||Sprites:on sprite of kind Player overlaps otherSprite of kind Enemy||``-blokken sammen med ``||sprites:destroy otherSprite||``-blokken.
Test spillet igjen. Ser du at du får poeng?

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    sprites.destroy(otherSprite)
    // @highlight
    info.changeScoreBy(1)
})
```

### Steg 7
Det er fortsatt et par ting som gjenstår. Slik spillet er nå, klarer du alltid å fange alle robotene.
Du kan gjøre spillet vanskeligere ved å lage en nedtelling.
Hent en ``||info:start countdown||``-blokk fra ``||info:Info||``-menyen og plasser den nederst i ``||loops:on start||``-blokka.
Om du synes 10 sekunder er for liten tid, kan du endre tallet i det hvite feltet til noe annet.

```blocks
let robotKrabbe: Sprite = null
tiles.setCurrentTilemap(tilemap`level1`)
scene.setBackgroundColor(7)
let minRobot = sprites.create(img`
    . . . . . f f f f . . . . . 
    . . . f f 5 5 5 5 f f . . . 
    . . f 5 5 5 5 5 5 5 5 f . . 
    . f 5 5 5 5 5 5 5 5 5 5 f . 
    . f 5 5 5 d b b d 5 5 5 f . 
    f 5 5 5 b 4 4 4 4 b 5 5 5 f 
    f 5 5 c c 4 4 4 4 c c 5 5 f 
    f b b f b f 4 4 f b f b b f 
    f b b 4 1 f d d f 1 4 b b f 
    . f b f d d d d d d f b f . 
    . f e f e 4 4 4 4 e f e f . 
    . e 4 f 6 9 9 9 9 6 f 4 e . 
    . 4 d c 9 9 9 9 9 9 c d 4 . 
    . 4 f b 3 b 3 b 3 b b f 4 . 
    . . f f 3 b 3 b 3 3 f f . . 
    . . . . f f b b f f . . . . 
    `, SpriteKind.Player)
controller.moveSprite(minRobot)
scene.cameraFollowSprite(minRobot)
for (let index = 0; index < 4; index++) {
    robotKrabbe = sprites.create(img`
        . . . . . . . . . . . c c . . . 
        . . . . . . . c c c c 6 3 c . . 
        . . . . . . c 6 3 3 3 3 6 c . . 
        . . c c . c 6 c c 3 3 3 3 3 c . 
        . b 5 5 c 6 c 5 5 c 3 3 3 3 3 c 
        . f f 5 c 6 c 5 f f 3 3 3 3 3 c 
        . f f 5 c 6 c 5 f f 6 3 3 3 c c 
        . b 5 5 3 c 3 5 5 c 6 6 6 6 c c 
        . . b 5 5 3 5 5 c 3 3 3 3 3 3 c 
        . c c 5 5 5 5 4 c c 3 3 3 3 3 c 
        c 5 5 4 5 5 4 c 5 5 c 3 3 3 c . 
        b 5 4 b 4 4 4 c 5 5 5 b c c . . 
        c 4 5 5 b 4 4 c 5 5 5 c b b . . 
        c 5 5 5 c 4 c 5 5 5 5 c c 5 b . 
        c 5 5 5 5 c 4 c c c c c c 5 c . 
        . c c c c c c . . . . . c c c . 
        `, SpriteKind.Enemy)
    tiles.placeOnRandomTile(robotKrabbe, assets.tile`transparency16`)
    robotKrabbe.setVelocity(randint(-50, 50), randint(-50, 50))
    robotKrabbe.setBounceOnWall(true)
}
// @highlight
info.startCountdown(10)
```

### Steg 8
Om du vil gjøre spillet enda vanskeligere, kan du lage flere robotkrabber. Spillet lager bare 4 robotkrabber akkurat nå.
Om du endrer tallet 4 øverst i ``||loops:repeat 4 times||``-blokka til et større tall, får du flerer robotkrabber.
Klarer du å fange 20 på 10 sekunder?

```blocks
let robotKrabbe: Sprite = null
tiles.setCurrentTilemap(tilemap`level1`)
scene.setBackgroundColor(7)
let minRobot = sprites.create(img`
    . . . . . f f f f . . . . . 
    . . . f f 5 5 5 5 f f . . . 
    . . f 5 5 5 5 5 5 5 5 f . . 
    . f 5 5 5 5 5 5 5 5 5 5 f . 
    . f 5 5 5 d b b d 5 5 5 f . 
    f 5 5 5 b 4 4 4 4 b 5 5 5 f 
    f 5 5 c c 4 4 4 4 c c 5 5 f 
    f b b f b f 4 4 f b f b b f 
    f b b 4 1 f d d f 1 4 b b f 
    . f b f d d d d d d f b f . 
    . f e f e 4 4 4 4 e f e f . 
    . e 4 f 6 9 9 9 9 6 f 4 e . 
    . 4 d c 9 9 9 9 9 9 c d 4 . 
    . 4 f b 3 b 3 b 3 b b f 4 . 
    . . f f 3 b 3 b 3 3 f f . . 
    . . . . f f b b f f . . . . 
    `, SpriteKind.Player)
controller.moveSprite(minRobot)
scene.cameraFollowSprite(minRobot)
// @highlight
for (let index = 0; index < 20; index++) {
    robotKrabbe = sprites.create(img`
        . . . . . . . . . . . c c . . . 
        . . . . . . . c c c c 6 3 c . . 
        . . . . . . c 6 3 3 3 3 6 c . . 
        . . c c . c 6 c c 3 3 3 3 3 c . 
        . b 5 5 c 6 c 5 5 c 3 3 3 3 3 c 
        . f f 5 c 6 c 5 f f 3 3 3 3 3 c 
        . f f 5 c 6 c 5 f f 6 3 3 3 c c 
        . b 5 5 3 c 3 5 5 c 6 6 6 6 c c 
        . . b 5 5 3 5 5 c 3 3 3 3 3 3 c 
        . c c 5 5 5 5 4 c c 3 3 3 3 3 c 
        c 5 5 4 5 5 4 c 5 5 c 3 3 3 c . 
        b 5 4 b 4 4 4 c 5 5 5 b c c . . 
        c 4 5 5 b 4 4 c 5 5 5 c b b . . 
        c 5 5 5 c 4 c 5 5 5 5 c c 5 b . 
        c 5 5 5 5 c 4 c c c c c c 5 c . 
        . c c c c c c . . . . . c c c . 
        `, SpriteKind.Enemy)
    tiles.placeOnRandomTile(robotKrabbe, assets.tile`transparency16`)
    robotKrabbe.setVelocity(randint(-50, 50), randint(-50, 50))
    robotKrabbe.setBounceOnWall(true)
}
info.startCountdown(10)
```

### Steg 9
Nå er spillet ditt ferdig! Når du klikker på "Done" får du spørsmål om du vil dele spillet ditt med andre.
Det velger du selv om du vil gjøre. Du kan også bare krysse ut spørsmålsvinduet og gå videre.
Etter det kommer du tilbake til spillet ditt, men nå har du tilgang på mange flere kodeblokker!
Kanskje du har lyst til å legge til mer i spillet?
Du kan legge til lyder og musikk, eller du kan legge til et bakgrunnsbilde i spillet ditt.
Husk at om du gjør noe du angrer på, kan du alltid trykke på angreknappen nede i høyre hjørne av skjermen.
Lykke til!
