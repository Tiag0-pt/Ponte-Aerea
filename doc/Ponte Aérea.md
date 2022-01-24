# Ponte Aérea

---

Neste trabalho queremos simular o transporte de N passageiros entre as cidades de _Origin_ e _Target_ usando uma ponte aérea de 1 avião.

Na acção temos 3 intervenientes sendo cada um, processos independente

- Piloto

- Hospedeira

- N Passageiros

Para desenvolver esta simulação iremos partir do código fonte em **semaphore_airlift.tgz** onde a sincronização dos processos será feita por **semáforos e memória partilhada**

Os ficheiro a editar são:

- semSharedMemPilot.c

- semSharedMemPassenger.c

- semSharedMemHostess.c

Todos os processo são criados a partir do ficheiro **probSemSharedAirLift**

Os processos devem estar activos apenas quando for necessário devendo estar bloqueados sempre que têm que esperar por algum evento.

Os resultados esperados podem ser obtidos executando o comando **make all_bin** seguido pelo comando **./probSemSharedMemAirLift.**

## Informações:

----

O Avião começa na cidade de Origin

\*sh é um ponteiro para a memória partilhada

**Hospedeira**

- Informa o piloto que o embarque está concluído

- Dá permissão aos passageiros na fila de espera para embarcarem

**Piloto**

- Informa a **Hospedeira** que o avião está pronto para o processo de embarque

- Inicia o voo de regresso apenas quando todos os passageiros tiverem saído

- Inicia o voo de ida perante as seguintes condições :
  
  - Se o avião já estiver cheio
  
  - Todos o passageiros tiverem embarcado
  
  - Já tem o numero mínimo de passageiros e a fila de espera está vazia

**Passageiros**

- Chegam em tempos aleatórios ( segundo uma distribuição uniforme)

- Ao chegar ao aeroporto entram numa lista de espera , até serem atendidos

- Ao chegar ao destino entram numa lista de espera, até poderem sair

# 

## Úteis

---

Após um teste temos que dar clean á memória partilha, podemos fazer isso manualmente verificando a **key** da memória partilhada e substituindo no **clean.sh**

Os ficheiros \*\_bin estão a funcionar, pelo que para abordar o trabalho podemos fazer trabalhar processo a processo e depois dar o **make @argv** onde **@argv** pode ser:

- all : testar todos os processos que fizemos

- pt : testar piloto

- ht : testar hospedeira

- pg : testar passageiros

- pg_ht : testar passageiros e hospedeira

- all_bin : ver resultados previstos

# Shared memória

Na memória partilha temos os seguintes dados e estruturas:

- FULL\_STAT fSt

- int mutex

- int passengersInQueue

- int passengersWaitInQueue

- int passengersWaitInFlight

- int readyForBoarding

- int readyToFlight

- int idShown

- int planeEmpty