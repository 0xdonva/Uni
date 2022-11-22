Il suo caso d'uso più comune consiste nel suo impiego all'interno di una classe come _localizzatore di una super[[classe]]_ (se esiste) che abbia un determinato attributo.
Il punto di partenza del processo di localizzazione può essere controllato ma, sempre nei casi più comuni esso è la prima classe dopo `C` nell'[[Ereditarietà#MRO|MRO]] di `C` stesso.
```jupyter
class nonno:
    w = "Attributo della classe nonno"
    def __getattribute__(self,x):
        print("eseguo __getattribute__ della classe nonno")
        return super().__getattribute__(x)
```
