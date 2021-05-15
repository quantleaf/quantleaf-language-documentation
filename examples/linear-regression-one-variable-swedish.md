This example shows that Quantleaf Language can also be written in swedish

```
"Datan som vi vill anpassa en rät linje till"
x = [1,2,3,4,5,6,7]
y = [3,5,10,5,9,14,18]

"Räta linjens funktion"
f(x,k,m) = x*k + m

"Avståndet från punkterns från linjen som en funktion av k och m"
avstånded från punkterna(k,m) = (f(x,k,m) - y)^2

"Hitta k och m som passar bäst till datan"
resultat = minimera avstånded från punkterna

"Visa resultatet av optimeringen"
skriv ut resultat

"Visualsera datan samt den anpassade linjen"
estimerad k = resultat.parameters.k
estimerad m = resultat.parameters.m

punktdiagram(x,y, titel = Observationer) 
och linjediagram(x,f(x,estimerad k,estimerad m), titel = Anpassad linje)

```