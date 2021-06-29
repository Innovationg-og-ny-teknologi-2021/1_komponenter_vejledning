# 1_komponenter_vejledning
Øvelser 2– components, props, state, eventhandler og ref

### slut resultat
![Screenshot](gif.gif)

# Component
Læs mere om komponenter på https://reactjs.org/docs/components-and-props.html

1. Lav et nyt expo projekt i din projekt mappe med `expo init 1_komponenter`og åben projektet i webstorm

2. Opret en mappe i dit nyoprettet projekt ved navn components 

3.	Lav en komponent ny komponent der indeholder der indeholder et tekst element  
    ![Screenshot](s1.png)

4.	Importer din komponent i App.js og implementer den i App.js’ render() funktion. (Husk at render() kun kan returnere ét element)

5.	Kør appen og se om den viser teksten.
      Props
6.	Send nu en prop til din komponent (title vil blive benyttet som eksempel her). I dit component tag i App.js tilføjer du title inde i dets start-tag. Husk det er ligesom når vi eksempelvis definerer en style til et tag. Du kan kalde den hvad du vil.

7.	Inde i din komponent skal du så slette den tekst der før stod i dit <Text>...</Text> tag og prøve i stedet for at få fat i den prop du sendte fra App.js.

8.	Kør appen og se om den viser teksten, som du har angivet i App.js.

9.	Opret flere instanser af din komponent i App.js’ render() metode og send forskellige tekster til hver af dem, igennem den prop du definerede i opgave 5, her title.
      State & Eventhandler
      Nu skal du prøve at ændre staten af din komponent, når der trykkes på en knap.
10.	Sæt App.js’ ”initial state” ved at definere en state i App-komponenten, dvs et objekt med en given værdi som default value. Eksempelvis state = { boxTitle : ‘Empty box’}

10.	Importer Button komponenten fra ’react-native’ i App.js og tilføj den oven over din komponent i render() funktionen.

11.	En Button skal altid have en title og en onPress prop. Til onPress vil vi smide en reference ind til en funktion du opretter oven over render() funktionen. Opret en funktion ala handleButtonPress = () => {...}.

12.	Giv handleButtonPress som reference til onPress prop for Button komponenten.

13.	Inde i onButtonPress skal du ændre App.js’ state ved brug af setState() funktionen og smide en ny value ind for boxTitle.

14.	Afslutningsvis skal du sørge for at din komponents tag i App.js (f.eks. <Box>) refererer til App.js’ state.boxTitle.

15.	Nu burde din app ændre sig fra at have din komponent til at sige ”empty box” til den nye value du skrev i opgave 13, når du trykker på knappen.
       Ref
       Nu skal du prøve at ændre teksten i din komponent ved at have et inputfelt, hvor man kan skrive noget, og så have en knap, hvor, når man trykker på den, ændrer teksten i din komponent.

16.	I App.js laver du en ref property med React.createRef(). Brug denne som ref i dit component tag. Eksempelvis <Box ref={this.box} />

17.	Importer TextInput elementet fra ’react-native’ i App.js og tilføj den over din Button i render() funktionen.

18.	Find information omkring TextInput i React Native’s API her https://facebook.github.io/react-native/docs/components-and-apis

19.	Her vil du finde alt hvad man kan med et TextInput element. Du skal have fat i den tekst en bruger skriver inde i TextInput. Find den korrekte event (starter med ”on,..”). Den skal indeholde ”den ændrede tekst” (den tekst der bliver skrevet inde i den) som et argument. Giv det et forsøg. Hvis du ikke kan finde den, kan du trykke her.

20.	Giv den også en placeholder, hvor der står ”Indsæt tekst her”.

21.	Når du har fundet den rigtige metode, definerer du den inde i <TextInput> tagget. Opret en funktion ligesom handleButtonPress() der tager imod et argument ’value’. Eksempelvis handleTextChange = (value) => {...}.

22.	Inde i denne ændrer du staten af din property (boxTitle i eksemplet) til at være lig value.

23.	Ændr nu din handleButtonPress til at ændre din komponents titel ved at få fat på dens ref.
       Der er brug for at introducere en state i din komponent, bruge den i render() og lave en setTitle metode som opdaterer komponentens state når den kaldes.
       Kaldet fra handleButtonPress kan f.eks. se se således ud ”this.box.current.setTitle(…”

24.	Appen burde nu give dig mulighed for at skrive en tekst i et tekstfelt, og trykke på en knap, der ændrer din komponents titel til den tekst som du skrev i TextInput feltet.

25.	Brug components til at lave et UI hvor du anvender input, output og en knap f.eks. til at brugeren indtaster en tekst som konfirmeres eller noget helt andet
 


#### Komponent template

```
import React from 'react';
import { StyleSheet, View} from 'react-native';

const App = () => {

    return (
            <View style={styles.container}>
               {/*alt vores content*/}
            </View>
    );
}
export default App;

const styles = StyleSheet.create({
    container: {
        flex: 1,
        backgroundColor: '#fff',
        alignItems: 'center',
        justifyContent: 'center',
    },
});
`


