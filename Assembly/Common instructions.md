# mov`
The `mov` instruction makes a copy from source to destination. 
Format:
```asm
mov   destination, source
```

It can be used as:
```asm
mov   register, immediate value
mov   register, memory
mov   memory, register
```

Illegal:
```asm
mov   memory, memory
```