
Tema2
Lidia Istrate 342C4


1. Reprezentarea

-> similar cu laboratorul 5
-> atom/regula/intrebare
-> 0: primul element este tipul ATOM pentru atom si intrebare
								OR pentru regula
-> 1: al doilea element este predicate = numele predicatului pentru atom si intrebare si OR pentru regula
-> 2: al treilea element este args pentru atom si intrebare si rule pentru regula, rule este reprezentat ca in lab 7, o clauza horn cu premisele negate si concluzia la final
-> 3: al patrulea element este coeficientul de incredere

Majoritatea functiilor sunt luate din laborator, cele de get si is, cu adaugari + unify, substitute, etc

Pentru procesarea fisierului am 2 functii process_atom si process_rule ce gasesc fiecare element in parte si creeaza atomul, intrebarea sau regula.

Am creat kb = knowledge base-ul prin adaugarea de fapte si reguli.

print_formula din laborator este modificat pentru a suporta si reguli in formatul ales de mine

2. backward_chaining

- mai intai verific daca pot unifica teorema cu vreun fapt din kb, 
daca da, returnez unificarea si CF
- altfel, incerc sa gasesc teorema in concluzia vreunei reguli
- pentru toate concluziile care se potrivesc cu teorema, folosesc dict_var_var pentru a modifica numele variabilelor din concluzie daca este nevoie pentru a fi egali cu cei din teorema si pe fiecare premisa apelez recursiv backward_chaining
- cand o premisa se intoarce cu rezultate, verific daca valorile se potrivesc cu ce a fost gasit pana la momentul actual si elimin ce nu se potriveste din lista de unificari posibile, sau daca unificarile nu contin toate variabilele posibile, verific daca pot adauga noua variabila la vreuna din unificarile existente
- cand termin cu premisele calculez CF al concluziei si adaug in lista de CF-uri pentru a calcula la final CF total



4. Coeficienti de incredere

Calculati dupa regulile din curs:

CF(premisa) = min(CF(premise))
CF(concluzie) = CF(premisa) * CF(regula)
CF(intrebare) = suma(CF[concluzii]) - produs(CF[concluzii])




Pentru apelare:
In main() se modifica fiierul dat ca parametru functiei read_input

