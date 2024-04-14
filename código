iniciar :- hipotese(Automoveis),
      write('Eu acho que o veiculo é: '),
      write(Automoveis),
      nl,
      undo.
      

/* hipóteses a serem testadas */
hipotese(sedan)       :- sedan, !.
hipotese(suv)         :- suv, !.
hipotese(minivan)     :- minivan, !.
hipotese(hatchback)   :- hatchback, !.
hipotese(caminhonete) :- caminhonete, !.
hipotese(carro_de_rally)     :- carro_de_rally, !.
hipotese(carro_de_formula1)  :- carro_de_formula1, !.
hipotese(kart)         :- kart, !.
hipotese(aviao)        :- aviao, !.
hipotese(helicoptero)  :- helicoptero, !.
hipotese(bicicleta)   :- bicicleta, !.
hipotese(moto)         :- moto, !.
hipotese(desconhecido). /* sem diagnóstico */

/* Regras de identificação dos carros */
sedan :- tem_quatro_portas, estilo_tradicional.
suv :- tem_quatro_portas, estilo_robusto, altura_elevada.
minivan :- tem_quatro_portas, estilo_familiar, espaco_interno_ampliado.
hatchback :- tem_duas_portas, estilo_compacto.
caminhonete :- tem_duas_portas, caca_traseira.
bicicleta :- duas_rodas, pedal.
moto :- duas_rodas, estilo_esportivo.
carro_de_rally :-  tem_duas_portas,estilo_robusto, tracao_integral.
carro_de_formula1 :- estilo_aerodinamico, alta_potencia, baixo_peso.
kart :- estilo_compacto, alta_potencia, baixo_peso.
aviao :- asas, motor_aeronautico.
helicoptero :- rotor, motor_aeronautico.

/* regras de classificação */
tem_quatro_portas :- verificar(tem_quatro_portas).
tem_duas_portas :- verificar(tem_duas_portas).
duas_rodas :- verificar(duas_rodas).
pedal :- verificar(pedal).
estilo_esportivo :- verificar(estilo_esportivo).
estilo_tradicional :- verificar(estilo_tradicional).
estilo_robusto :- verificar(estilo_robusto).
estilo_compacto :- verificar(estilo_compacto).
estilo_familiar :- verificar(estilo_familiar).
altura_elevada :- verificar(altura_elevada).
espaco_interno_ampliado :- verificar(espaco_interno_ampliado).
caca_traseira :- verificar(caca_traseira).
alta_potencia :- verificar(alta_potencia).
tracao_integral :- verificar(tracao_integral).
estilo_aerodinamico :- verificar(estilo_aerodinamico).
asas :- verificar(asas).
rotor :- verificar(rotor).
motor_aeronautico :- verificar(motor_aeronautico).
baixo_peso :- verificar(baixo_peso).

/* Como fazer perguntas */
perguntar(Questão) :-
    write('O veículo tem o seguinte atributo: '),
    write(Questão),
    write(' (s|n) ? '),
    read(Resposta),
    nl,
    ( (Resposta == sim ; Resposta == s)
      ->
       assert(yes(Questão)) ;
       assert(no(Questão)), fail).

:- dynamic yes/1,no/1.

/* Como verificar algo */
verificar(S) :-
   (yes(S)
    ->
    true ;
    (no(S)
     ->
     fail ;
     perguntar(S))).

/* Desfaz todas as afirmações sim / não */
undo :- retract(yes(_)),fail.
undo :- retract(no(_)),fail.
undo.
