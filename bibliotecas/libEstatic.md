# Criando biblioteca estática

Arquivos necessários:

```C
// libstatic.c
#include <stdio.h>

//soma
int somaNum(int a, int b)
{
    return a + b;
}

//quadrado
long int quadradoNum(int n)
{
    return n * n;
}

//imprime
void imprimeOla()
{
    printf("Ola!");

}
```

```C
// programa.c
#include <stdio.h>

int main()
{
    printf("%d\n", somaNum(2, 2));
    printf("%li\n", quadradoNum(6));

    imprimeOla();


  return 0;
}
```

Comandos para criar a biblioteca estática:

    gcc -c libstatic.c
    ar crv libstatic.a libstatic.o

Linkando com o programa e criando o executável:


    gcc programa.c libstatic.a
    gcc libstatic.a programa.c 

Segundo modo:

    gcc -c programa.c
    gcc programa.o libstatic.a
    gcc -o programa.exe programa.o libstatic.a

No code blocks: 

- Criar o arquivo do programa e compilar com `F9` da erros de referências indefinidas
- Linkando: Settings > Compiler > Linker settings > Add
    - E adicionar o cominho da biblioteca `.a`: `C:\...\StaticLib\libstatic.a`
    - E então compilaria com `F9`

# Bibliotecas dinamicas

- Bibliotecas compartilhadas (shared libraries) ou bibliotecas dinâmicas:
    - Windows: .dll's 
    - Em Linux: .so, e 
    - Em Mac: .dylib.

- Arquivos pré-compilados:
    - Pode ser usado por diferentes programas;
    - Pode-se ter diferentes implementações;
    - Otimização sem recompilar o programa principal;
    - 

> Vantagem: Substituir uma biblioteca ligada dinamicamente por outra mais eficiente do mesmo código (voce a substitui e o programa principal não precisa ser recompilado - a biblioteca carrega juntamente com o programa no momento da execução)

```C
// helloworld.c
#include <stdio.h>

void printHelloWorld(void)
{
    printf("Hello world"\n");
}
```

```C
// helloworld.h
void printHelloWorld(void);
```

```C
// main.c
#include "helloworld.h"

int main(int argc, char **argv)
{
    printHelloWorld();
}
```

Criando a biblioteca dinâmica `libhello.dylib` (no mac) na pasta `\lib` localizada no diretório do programa

    gcc -dynamiclib -o lib/libhello.dylib helloworld.c

Compilando o programa principal:

    gcc main.c -Llib -lhello -o main
    ./main
    Hello world

Agora vamos modificar a biblioteca e criar uma nova biblioteca dinâmica:

```C
// helloworld.c
#include <stdio.h>

void printHelloWorld(void)
{
    printf("Olá mundo"\n");
}
```

- Mover `libhello.dylib` para uma pasta chamada `en-us`
- Compilar: `gcc -dynamiclib -o lib/libhello.dylib helloworld.c`
- Executando sem recompilar o main conseguimos usar a outra função: `./main`
- Saida: Olá mundo

Podemos melhor a biblioteca em varias versões sem ter que recompilar o programa:

```C
// helloworld.c
#include <stdio.h>

void printHelloWorld(void)
{
    printf("Olá mundo!!!"\n");
}
```

    gcc -dynamiclib -o lib/libhello.dylib helloworld.c
    ./main
    Olá mundo!!!

# Gerenciamento das bibliotecas compartilhadas

https://www.youtube.com/watch?v=1gzrq0q2X5w

- Comando `ldd`: exibe as bibliotecas compartilhadas requeridas pelos programas (retorna nome da biblioteca e o local onde ela está)


```
ldd [caminho_completo_programa_com_espaços]
ldd --version # versão
ldd -v [programa] # modo verbose
ldd -v /bin/ls <enter>
```

- Vincunlando as bibliotevas compartilhadas: `ld.so`
- 