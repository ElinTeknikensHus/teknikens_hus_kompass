# IFC2023 kompass
## Kompass (med full tutorial) @unplugged
<div style="display: flex; justify-content: space-around;">
  <img src="https://github.com/ElinTeknikensHus/esero_test/blob/master/logotyp%20esero-sweden_svart.png?raw=true" alt="DampVibrations" width="300"/>
  <img src="https://github.com/ElinTeknikensHus/esero_test/blob/master/TH-logo-liggande-svart%403x.png?raw=true" alt="DampVibrations" width="300"/>
</div>

## Räkna grader-variablen
Skapa en variabel, som du kallar `||variables:grader||`. Sätt variabelns värde till `||input:kompassriktning||` och dra in i `||basic:för alltid||` -loopen
 
 ```blocks
basic.forever(function(){
    let grader = input.compassHeading()
})
 ```

## Kompassen kräver logik!
`||logic:Om||` `||variables:grader||` är `||logic:mindre än||` 45, så pekar kompassen mest mot norr (av de fyra väderstrecken). `||basic:Visa||` N på micro:biten.

```blocks
basic.forever(function(){
    let grader = input.compassHeading()
    if(grader < 45){
        basic.showString("N")
    }
})
 ```

 ## Fortsätt med väderstrecket öster/ostlig riktning
`||logic:Om||` `||variables:grader||` är `||logic:mindre än||` 135, så pekar kompassen mest mot öster. `||basic:Visa||` O på micro:biten.

```blocks
basic.forever(function(){
    let grader = input.compassHeading()
    if(grader < 45){
        basic.showString("N")
    }
    else if (grader < 135) {
        basic.showString("O")
    }
})
 ```

## Testa! 
Prova din kompass (Norr eller Ost) genom att dra i micro:bit-loggan i simulatorn.

## Fortsätt med väderstrecket söder 
`||logic:Om||` `||variables:grader||` är `||logic:mindre än||` 225, så pekar kompassen mest mot söder. `||basic:Visa||` S på micro:biten.

```blocks
basic.forever(function(){
    let grader = input.compassHeading()
    if(grader < 45){
        basic.showString("N")
    }
    else if (grader < 135) {
        basic.showString("O")
    }
    else if (grader < 225) {
        basic.showString("S")
    }
})
 ```

 ## ...och så väster 
`||logic:Om||` `||variables:grader||` är `||logic:mindre än||` 315, så pekar kompassen mest mot väster. `||basic:Visa||` V på micro:biten.

```blocks
basic.forever(function(){
    let grader = input.compassHeading()
    if(grader < 45){
        basic.showString("N")
    }
    else if (grader < 135) {
        basic.showString("O")
    }
    else if (grader < 225) {
        basic.showString("S")
    }
    else if (grader < 315) {
        basic.showString("V")
    }
})
 ```

 ## Avsluta koden 
`||logic:Om||` inget av villkoren är uppfyllt måste micro:biten peka mot norr (fast till vänster om rakt mot norr).  på micro:biten.

```blocks
basic.forever(function(){
    let grader = input.compassHeading()
    if(grader < 45){
        basic.showString("N")
    }
    else if (grader < 135) {
        basic.showString("O")
    }
    else if (grader < 225) {
        basic.showString("S")
    }
    else if (grader < 315) {
        basic.showString("V")
    }
    else {
        basic.showString("N")
    }
})
 
```


 ## Ladda ner och testa!

