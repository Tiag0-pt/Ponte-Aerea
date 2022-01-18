# Ponte Aérea

---

Neste trabalho queremos simular o transporte de N passageiros entre as cidades de _Origin_ e _Target_ usando uma ponte aérea de 1 avião.

Na acção temos 3 intervenientes sendo cada um, um processo independente

- Piloto

- Hospedeira

- Passageiros

Para desenvolver esta simulação  iremos partir do código fonte em **semaphore_airlift.tgz** onde a sincronização  dos processos será feita por **semáforos e memória partilhada**

Todos os processo são criados a partir do ficheiro **probSemSharedAirLift**

Os processos devem estar activos apenas quando for necessário devendo estar bloqueados sempre que têm que esperar por algum evento.

Os resultados esperados podem ser obtidos executando o comando **make all_bin** seguido pelo comando **./probSemSharedMemAirLift.**



## Informações:



O Avião começa na cidade de Origin



**Hospedeira**

- Informa o piloto que o embarque está concluído

- Dá permissão aos passageiros na fila de espera para embarcarem

- Dá permissão aos passageiros para saírem

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



---






