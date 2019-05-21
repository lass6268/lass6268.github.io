---
layout: post
title: LiveData og ViewModel
subtitle: Kladde underoverskrift
tags: [uge 21, appudvikling, kotlin]
---

Her kommer en forsinket tekst om LiveData og ViewMode.
- LiveDate er en observable klasse der holder på data.
- ViewModel klassen er designet til at gemme og håndtere brugerfladerelateret data.

LiveData placeres i en ViewModel og activityen, eller fragmentet, indeholder en/flere observer, der holder øje med ændringer i datasættet i Viewmodel

![](/img/vm.png)

## LiveData
LiveData fungerer som en wrapper. Du indpakker dit data i et LiveData-objekt. Når du bruger LiveDatas funktioner, vil den sørge for at sende beskeder videre til de steder i koden som vil kende til ændringerne.

En eller flere observer holder øjne med ændringer i datasættet. Når der sker ændringer, sørger observeren for at de ønskede handlinger sker. Det kunne eksempelvis være en ændring af teksten/farven/udseenet i brugerfladen. 

LiveData implementerer hvad der svarer til observer design pattern. Selve LiveData er subjektet hvis tilstand der kan observes.

## ViewModel
En ViewModel indeholder det data der skal præsenteres i viewet. Der kan også være diverse metoder til at håndtere dette data. Eksempelvis en metode til at hente data fra Repository.

### Eksempel

> ViewModel der indeholder LiveData
```kotlin
class ExampleViewModel(val app: Application) : AndroidViewModel(app) {
  val fragmentTitle = MutableLiveData<String>()
  
  init {
    fragmentTitle.value = "Overskrift til denne skærm"
  }
  
  fun changeFragmentTitle(newTitle: String) {
  fragmentTitle.value = newTitle
  }
}
```

> Activity der bruger ovenstående ViewModel og observer på LiveData
```kotlin
class MyActivity : AppCompatActivity() {
    private lateinit var exampleViewModel: ExampleViewModel
    private val newTitleFromActivity = "Ny overskrift"
    
    override fun onCreate(savedInstanceState: Bundle?) {
    // Opretter en instans af vores ViewModel
        exampleViewModel = ViewModelProviders.of(this).get(ExampleViewModel::class.java)
        
    // Starter en observer, der holder øje med ændringer på fragmentTitle    
        exampleViewModel.fragmentTitle.observe(this, Observer { 
        // logikken der håndterer ændringer
          activity?.title = it
        })
    }
    
    fun onClick() {
      exampleViewmodel?.changeFragmentTitle(newTitleFromActivity)
    }
}

```

# Refleksioner
Det er altid smart at kunne vise data, også når det ændres på den ene eller anden måde, og på det punkt er det smart med LiveData. Når man bruger ViewModel hjælper det også på overblikket, da man kan fjerne en masse kode fra Activityen ned i viewmodel. Activityen har så kun ansvar for at lytte til ændringer og håndtere disse. På denne måde bliver det forskellige ansvar delt ud til nogle mere logiske steder:
 - viewmodel klargør data til viewet og videresender arbejde hvis der skal bearbejdes noget
 - viewet håndterer kun hvad brugeren ser

Jeg syntes dog at der stadig kræves en del boilerplate kode, hvilket er en betragtning jeg generelt har om appudvikling.

> Det kunne være spændende at kigge nærmere på [Androids Data Binding Library](https://developer.android.com/topic/libraries/data-binding/), desværre tillader tiden det ikke i denne omgang.

### Kilder
- Android developer: [LiveData](https://developer.android.com/topic/libraries/architecture/livedata)
- Android developer: [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel)
