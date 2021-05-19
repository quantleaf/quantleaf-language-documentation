This example shows that Quantleaf Language can also be written in swedish


[Run this example](https://quantleaf.com/?q=%22Datan%20som%20vi%20vill%20anpassa%20en%20r%C3%A4t%20linje%20till%22%0Ax%20%3D%20%5B1,2,3,4,5,6,7%5D%0Ay%20%3D%20%5B3,5,10,5,9,14,18%5D%0A%0A%22R%C3%A4ta%20linjens%20funktion%22%0Af(x,k,m)%20%3D%20x*k%20%2B%20m%0A%0A%22Avst%C3%A5ndet%20fr%C3%A5n%20punktens%20fr%C3%A5n%20linjen%20som%20en%20funktion%20av%20k%20och%20m%22%0Aavst%C3%A5nded%20fr%C3%A5n%20punkterna(k,m)%20%3D%20(f(x,k,m)%20-%20y)%5E2%0A%0A%22Hitta%20k%20och%20m%20som%20passar%20b%C3%A4st%20till%20datan%22%0Aresultat%20%3D%20minimera%20avst%C3%A5nded%20fr%C3%A5n%20punkterna%0A%0A%22Visa%20resultatet%20av%20optimeringen%22%0Askriv%20ut%20resultat%0A%0A%22Visualsera%20datan%20samt%20den%20anpassade%20linjen%22%0Aestimerad%20k%20%3D%20resultat.parameters.k%0Aestimerad%20m%20%3D%20resultat.parameters.m%0A%0Apunktdiagram(x,y,%20titel%20%3D%20Observationer)%20%0Aoch%20linjediagram(x,f(x,estimerad%20k,estimerad%20m),%20titel%20%3D%20Anpassad%20linje)&t=code)


```
"Datan som vi vill anpassa en rät linje till"
x = [1,2,3,4,5,6,7]
y = [3,5,10,5,9,14,18]

"Räta linjens funktion"
f(x,k,m) = x*k + m

"Avståndet från punktens från linjen som en funktion av k och m"
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
