Le __stringhe__ sono sequenze di caratteri racchiuse fra _apici singoli o doppi_.
Questa "flessibilità" consente, in certi casi, di evitare escaping, cioè di dover inserire un carattere di escape prima di un carattere che deve essere interpretato in maniera speciale.
```jupyter
print("l'amor che move il sole e l'altre stelle")
# ma...
print('l\'amor che move il sole e l\'altre stelle')
```


## Tipi di stringhe
### Stringhe formattate
Anche chiamate __f-string__ sono stringhe che ammettono _valutazione_ e _formattazione_.
```jupyter
s = "per me si va"
F=f"{s} nella città dolente\n{s} nell'eterno dolore,\n{s} tra la perduta gente."
print(F)
```

### Stringhe grezze (raw string)
Anche chiamate __r-string__ sono stringhe in cui i caratteri speciali non vengono interpretati.
```jupyter
R = r"Un'espressione regolare contiene sequenze speciali:\n come \b e \d"
print(R)
```

### Stringhe su più righe
Python ammette __stringhe su più righe__, queste stringhe iniziano e terminano con _tre singoli apici_ o _tre doppi apici_.
```jupyter
M = """Questa è una stringa scritta
su più righe. Deve terminare con i tre apici
con cui si è aperta """
print(M)
```
Queste stringhe vengono comunemente usate per _i commenti_, anche se erroneamente, in realtà queste vengono sempre valutate dall'interprete ma il loro valore viene perduto.