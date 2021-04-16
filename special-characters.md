# Special characters like "ü, á, ô" doesn't work after an "?"

I tried to create a mailto formula on Google Sheets that looked like this:
<br/><br/>
```
=HIPERLINK ("mailto:"&C25&"?subject=Análise de Satisfação&""&body=Olá, "&B25&"!
Como vão as coisas por aí? Sou o Beto, da Empresa Júnior de Computação [...]";"Enviar E-Mail")
```
<br/>

## But when i click on the cell's link, this is what my e-mail look like:
<br/>

>Olá, Beto! Como vão as coisas por aí? Sou o Beto, da Empresa J%C3%BAnior de Computa%C3%A7%C3%A3o [...]

<br/>

## It reads normally until the question mark, so that's how i fixed it:

<br/>

```
=HIPERLINK("mailto:"&C25&"?subject=Análise de Satisfação&""&body=Olá, "&B25&"!
Como vão as coisas por aí%3F Sou o Beto, da Empresa Júnior de Computação[...]";"Enviar E-Mail")
```
I think it reads "?" as a part of the code, so you have to replace it with the equivalent "%3F" in VBA
<br/>
<br/>

## Result:

<br/>

>Olá, Beto! Como vão as coisas por aí? Sou o Beto, da Empresa Júnior de Computação [...]
