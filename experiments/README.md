# Experiments

## Experiment 1
Create 4 files corresponding to 4 steps in compilation.

### Preprocessing
To stop the compiler after the preprocessing step, enter the following command:
```console
$ gcc -E -o main_preprocessed.c main.c
```

### Assembly Code
To generate assembly code from your C source file.
```console
$ gcc -S -o main.s main.c
```

### Machine Code (Object Code)
This would generate the object file that is the output of the assembler. This is specific for each microcontroller/microprocessor.
```console
$ gcc -Wall -c main.c
```

### Executable
Enter this command for generating an executable. Output of the linker.
```console
$ gcc main.c
```

## Experiment 2
Create 4 files corresponding to 4 steps of compilation making use of the file generated in the earlier step.

### Preprocessing
To stop the compiler after the preprocessing step, enter the following command:
```console
$ gcc -E -o main_preprocessed.c main.c
```

### Assembly Code
To generate assembly code from your C source file.
```console
$ gcc -S -o main.s main_preprocessed.c
```

### Machine Code (Object Code)
This would generate the object file that is the output of the assembler. This is specific for each microcontroller/microprocessor.
```console
$ gcc -c main.s
```

### Executable
Enter this command for generating an executable. Output of the linker.
```console
$ gcc main.o -o main
```