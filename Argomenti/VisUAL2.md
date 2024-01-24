[[18. Processore ARM, Architettura e Set di Istruzioni]]
_Instructions_:
```arm-asm
1. MOV r0, #3
2. MOV r1, #7
3. loop
4. ADD r2, r0, r1
5. ;SUB r2, r2, #20
6. b loop
7. end
```
> [PDF con i Comandi](https://www.dmi.unict.it/santoro/teaching/arch/slides/ARM-Instruction-Set.pdf)

### Salto condizionato - Bcond
	B{cond} target

![[Pasted image 20231106122044.png]]

**Ciclo FOR in VisUAL2**
```asm-arm
;for(inti = 0; i < 10; i++){} come implementarlo?
MOV r0, #0
loop
		CMP r0, #10
		BGE end_loop   ;branch greaterthanor equal
	;corpo del for
		ADD r0, r0, #1 ;incremento i++
		B loop
end_loop
		END
```

**Moltiplicare due numeri**
```asm-amr
;Moltiplicare due numeri
MOV r0, #4
MOV r1, #7
MOV r2, #0
mul_loop
		CMP r1, #0
		BEQ end_mul
		ADD r2, r2, r0
		SUB r1, r1, #1
		B mul_loop
end_mul
		END
```

**Dividere due numeri**
```asm-amr
;Dividere due numeri
MOV r0, #100
MOV r1, #6
MOV r2, #0
div_loop
		CMP r0, r1
		BLT end_div
		SUB r0, r0, r1
		ADD r2, r2, #1
		B div_loop
end_div
		END
```

## Accesso alla memoria: LOAD
1. l'istruzione preleva una word dall'indirizzo di memoria indicato e la trasferisce ad un registro di destinazione;
2. L'indirizzo è e può essere indicato da un registra (puntatore) più un eventuale offset **immediato** o *registro*
![[Pasted image 20231113111822.png]]
![[Pasted image 20231113111846.png]]

## Bit masking
	Effettuare un operazione logica che ha l'obiettivo di
	isolare il bit che interessa

R3 = b7, ..., b0

```asm-arm

```