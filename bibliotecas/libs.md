# Criando bibliotecas

Se você tiver vários arquivos que contenham apenas funções, poderá transformar esses codigos fonte em bibliotecas que podem ser usadas estaticamente ou dinamicamente por programas. Isso é bom para modularidade de programa e reutilização de código. Escreva uma vez, use muitos.

Uma biblioteca é basicamente apenas um arquivo de arquivos de objetos.

## Criando Bibliotecas :: Configuração da Biblioteca Estática

Se você tiver vários arquivos que contenham apenas funções, poderá transformar esses códigos fonte em bibliotecas que podem ser usadas estaticamente ou dinamicamente por programas. Isso é bom para modularidade de programa e reutilização de código. Escreva uma vez, use muitos.

Uma biblioteca é basicamente apenas um arquivo de arquivos de objetos.

### Criando Bibliotecas :: Configuração da Biblioteca Estática

A primeira coisa que você deve fazer é criar seus codigos fonte em C contendo quaisquer funções que serão usadas. Sua biblioteca pode conter vários arquivos de objeto.

Depois de criar os arquivos de origem C, compile os arquivos em arquivos objeto. Para criar uma biblioteca:

    ar rc libmylib.a objfile1.o objfile2.o objfile3.o

Isso criará uma biblioteca estática chamada `libname.a`. Renomeie a parte "mylib" da biblioteca para o que você quiser. 

Próximo:
   
    ranlib libmylib.a

Isso cria um índice dentro da biblioteca. Deve ser isso! Se você planeja copiar a biblioteca, lembre-se de usar a opção `-p` com `cp` para preservar as permissões.

### Criando Bibliotecas :: Uso da Biblioteca Estática

Lembre-se de prototipar suas chamadas de função de biblioteca para que você não receba erros implícitos de declaração.

Ao vincular seu programa às bibliotecas, especifique onde a biblioteca pode ser encontrada:

    gcc -o foo -L. -lmylib foo.o

O `-L.` diz ao gcc para procurar no diretório atual, além dos outros diretórios da biblioteca, para encontrar o libmylib.a.

Você pode facilmente integrar isso no seu Makefile (até mesmo na parte da Configuração da Biblioteca Estática)!

### Criando Bibliotecas :: Configuração da Biblioteca Compartilhada

Criar bibliotecas compartilhadas ou dinâmicas é simples também. Usando o exemplo anterior, para criar uma biblioteca compartilhada:

    gcc -fPIC -c objfile1.c
    gcc -fPIC -c objfile2.c
    gcc -fPIC -c objfile3.c
    gcc -shared -o libmylib.so objfile1.o objfile2.o objfile3.o

- A opção `-fPIC` diz ao compilador para criar o Position Independent Code (criar bibliotecas usando endereços relativos em vez de endereços absolutos, pois essas bibliotecas podem ser carregadas várias vezes). 
- A opção `-shared` especifica que uma biblioteca compartilhada dependente da arquitetura onde está sendo criada. No entanto, nem todas as plataformas suportam esse sinalizador.

Agora temos que compilar o programa atual usando as bibliotecas:

    gcc -o foo -L. -lmylib foo.o

Observe que é exatamente o mesmo que criar uma biblioteca estática. Embora seja compilado da mesma maneira, nenhum código da biblioteca real é inserido no executável, portanto, uma biblioteca dinâmica/compartilhada.

Nota: Você pode automatizar este processo usando Makefiles!

### Criando Bibliotecas :: Uso Compartilhado da Biblioteca

Como os programas que usam bibliotecas estáticas já possuem o código da biblioteca compilado no programa, ele pode ser executado por conta própria. As bibliotecas compartilhadas acessam dinamicamente as bibliotecas em tempo de execução, portanto, o programa precisa saber onde a biblioteca compartilhada está armazenada. Qual é a vantagem de criar executáveis ​​usando bibliotecas dinâmicas? O executável é muito menor que com bibliotecas estáticas. Se é uma biblioteca padrão que pode ser instalada, não há necessidade de compilá-la no executável em tempo de compilação!

A chave para fazer seu programa funcionar com bibliotecas dinâmicas é através da variável de ambiente `LD_LIBRARY_PATH`. Para exibir essa variável, em um shell:

    echo $LD_LIBRARY_PATH

Irá exibir esta variável se já estiver definida. Se não estiver, você pode criar um script para o seu programa para definir essa variável em tempo de execução. Dependendo do seu shell, simplesmente use os comandos `setenv` (tcsh, csh) ou `export` (bash, sh, etc). Se você já tiver o parâmetro LD_LIBRARY_PATH definido, certifique-se de **anexar** à variável e não sobrescrevê-la! Por exemplo:

    setenv LD_LIBRARY_PATH /path/to/library:${LD_LIBRARY_PATH}

seria o comando que você usaria se tivesse o `tcsh/csh` e já tivesse um `LD_LIBRARY_PATH` existente. Se você ainda não definiu, basta remover tudo no lado direito de `:`. Um exemplo com shells bash:

    export LD_LIBRARY_PATH=/path/to/library:${LD_LIBRARY_PATH}

Novamente, remova tudo a direita de `:` e o símbolo `:` se você ainda não tiver um LD_LIBRARY_PATH existente.

Se você tiver direitos administrativos em seu computador, poderá instalar a biblioteca específica no diretório `/usr/local/lib` e adicionar permanentemente um `LD_LIBRARY_PATH` ao arquivo `.tcshrc`, `.cshrc`, `.bashrc`, etc.

https://helloacm.com/how-to-link-static-library-in-cc-using-gcc-compiler/

https://www.quora.com/How-can-I-use-some-C-library-so-in-my-C-code

https://www.quora.com/How-can-I-use-some-C-library-so-in-my-C-code

https://cmake.org/pipermail/cmake/2016-March/062927.html

https://www.cs.swarthmore.edu/~newhall/unixhelp/howto_C_libraries.html

https://downloads.haskell.org/~ghc/7.0.1/docs/html/users_guide/using-shared-libs.html

https://www.ardanlabs.com/blog/2013/08/using-c-dynamic-libraries-in-go-programs.html

http://www.learncpp.com/cpp-tutorial/a1-static-and-dynamic-libraries/

https://en.wikipedia.org/wiki/Static_library

http://www.microhowto.info/howto/build_a_shared_library_using_gcc.html

http://snowsyn.net/2016/09/11/creating-shared-libraries-in-go/

https://wiki.qt.io/How_to_create_a_library_with_Qt_and_use_it_in_an_application

https://stackoverflow.com/questions/17511496/how-to-create-a-shared-library-with-cmake

https://stackoverflow.com/questions/17601949/building-a-shared-library-using-gcc-on-linux-and-mingw-on-windows

http://gernotklingler.com/blog/creating-using-shared-libraries-different-compilers-different-operating-systems/

https://www.fayewilliams.com/2015/07/07/creating-a-shared-library/

https://www.geeksforgeeks.org/working-with-shared-libraries-set-2/

https://medium.com/meatandmachines/shared-dynamic-libraries-in-the-c-programming-language-8c2c03311756

https://www.cprogramming.com/tutorial/shared-libraries-linux-gcc.html

https://www.vivaolinux.com.br/dica/Como-criar-bibliotecas-dinamicas-em-C-C++

https://digitandocodigos.wordpress.com/2011/02/18/criando-uma-dll-em-c/

http://www.unidev.com.br/index.php?/topic/54737-criar-lib/

https://samuca.wordpress.com/2008/10/17/criando-bibliotecas-dinamicas-em-c/

https://www.scriptbrasil.com.br/forum/topic/162535-duvida-implementar-biblioteca/

https://www.klebermota.eti.br/2016/11/24/criando-bibliotecas-estaticas-no-linux-usando-cc/

http://diegorubin.com/2011/04/30/criacao-de-bibliotecas-dinamicas-em-c

https://pt.stackoverflow.com/questions/3690/criando-o-seu-pr%C3%B3prio-header-file

https://www.clubedohardware.com.br/forums/topic/876444-cria%C3%A7%C3%A3o-de-bibliotecas-nopara-dev-c/

