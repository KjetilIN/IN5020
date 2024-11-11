What is “the marker- receiveing rule” in the snapshot algorithm?
- A process that has not recorded its state must do so.


What are the use cases of the snapshot algorithm?
- Checkpointing, i.e. making checkpoint that the application can roll back to after failure. Debugging.
Deadlock and termination detection.

What are the requirements of a distributed consensus algorithm?
- Agreement: No two non-fault processes decide on different values.
- Termination: If there are non- faulty processes, at least one of them decides.
- Integrity(validity/non- triviality): If all non- faulty processes start with the same initial value v, then v is the only possible decision value for a non- faulty process.

What are the requirements for a reliable multicast algorithm?

- Termination: Every non-faulty process delivers a message.
- Agreement: No two non-faulty processes deliver different messages
- Validity: no spurious messages
- Integrity: If the sender is non-faulty, it delivers the message it sent

What are the requirements for a mutual exclusion algorithm?
- Safety: At most one process can be in critical section at at a time.
- Liveness(avoid starvation): Each request to entry/exit the critical section eventually succeeds.
- Ordering: Entrance to the CS must observe the “happened- before” relation. (if f -> e then f should get in before e)

Which mutual exclusion algorithms have we gone through?
- Central server
- Ring- based
- Ricart & Agrawala algorithm(based on logical clocks)
- 
Which distributed leader election algorithms have we gone through?
- The bully algorithm
- Ring- based algorithm
- Paxos 

What are the requirements for a distributed leader election algorithm?

- Safety: Max one node will be leader at a time
- Liveness: A leader will be elected.

Explain Ricart and Agrawala algorithm for mutex

Forklar the snapshot algorithm


P skal sende markør:

P lagrer egen lokal state, så sender den en markør gjennom på kanaler før den kan sende vanlige meldinger igjen.

Når Q mottar markør på kanal C1:

Hvis Q ikke har lagret sin lokale state.(dvs. den ikke har motatt markør tidligere):
- Lagre state på inkommende kanal som tom.
- Følg reglene for å sende markør.
Hvis Q allerede har lagret sin state.(den har motatt en markør tidligere):
- Lagre state for C som sekvensen av meldinger motatt langs C1 etter lokal state ble lagret og før Q mottok foreløpig markør.
29
Q

Forklar the bully algorithm


Prosessen som oppdager at coordinator har feilet sender election melding til prosessene som har større identifikator enn seg selv.
Den venter på ANSWER melding:
1. Om ingen svarer, setter prosessen seg selv til leder og sender COORDINATOR melding til alle prosesser med mindre identifikator.
2. Hvis en ANSWER melding blir motatt lar den prosessen som sendte ANSWER ta over og venter på COORDINATOR melding. Hvis ingen melding blir motatt starter den en ny election.

Hvis en prosess mottar en COORDINATOR melding, lagrer den identifikator i meldingen som ny coordinator.

Hvis en prosess mottar en ELECTION melding, sender den tilbake en answer melding og tar over ved å starte ny election.

Når en prosess recovers eller joiner systemet starter den ny election. Hvis den har størst identifikator gjør den seg selv til leder og annonserer det, selv om det allerede finnes en fungerende leder.
