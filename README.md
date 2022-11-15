# Sensorer - Bevegelse og berøring

## Step 1@showdialog
micro:biten har et innebygget akselerometer som kan registrere bevegelser og hvilken retning micro:biten peker. 

modellen vi bruker i dag (V2) har også en berørings-sensor på logoen over skjermen.

 ```blocks
 input.onGesture(Gesture.Shake, function () {
	
})
input.onGesture(Gesture.LogoUp function () {
	
})

input.onLogoEvent(TouchButtonEvent.Touched, function () {
    basic.showIcon(IconNames.Heart)
})

```

## Step 2@showdialog
La oss teste at sensoren virker som den skal. Dette programmet endrer bildet på micro:biten når den blir plukket opp eller lagt på bordet.

 ```blocks
input.onGesture(Gesture.LogoUp, function () {
    basic.showIcon(IconNames.Happy)
})
input.onGesture(Gesture.ScreenUp, function () {
    basic.showIcon(IconNames.Asleep)
})

```
## Step 2
Bygg og last ned programmet, og last ned til micro:biten. Hva skjer når du beveger på micro:biten?

(Trykk på lyspæren til høyre for å se bilde av koden.)

 ```blocks
input.onGesture(Gesture.ScreenUp, function () {
    basic.showIcon(IconNames.Asleep)
})
input.onGesture(Gesture.LogoUp, function () {
    basic.showIcon(IconNames.Happy)
})


```

## Step bro@showdialog
Alle verdiene micro:biten måler med sensorene, finnes som rosa blokker. Disse kan kombineres med andre blokker i programmet.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.sqrt(input.acceleration(Dimension.Strength)))
})
basic.forever(function () {
    led.plotBarGraph(
    input.acceleration(Dimension.X),
    1000
    )
})
```

## Step ping 
Endre programmet slik at micro:biten lyser om den merker at den rister. 

"Hvis akselerasjon er større enn 100, så gjør..." (Test ulike verdier for følsomhet og velg den du liker best)

(Trykk på lyspæren for å se fasiten.)

```blocks
basic.forever(function () {
    if (input.acceleration(Dimension.Z) > 100) {
        basic.showLeds(`
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            `)
        basic.pause(1000)
    } else {
        basic.clearScreen()
    }
})
```



## Step 2i3

Godt jobbet! Nå har dere kanskje begynt å få ideer til hvordan smarthuset deres kan reagere på bevegelser.

Trykk "Slutt/Finish" for å avslutte veiledningen.


```template
input.onGesture(Gesture.LogoUp, function () {})
```

