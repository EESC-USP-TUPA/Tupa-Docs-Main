# Criando Documentação

## Uso do Doxygen
Para nossos projetos nós usamos uma ferramenta chamada Doxygen, capaz de escanear o repositório do nosso código e gerar com base nele uma documentação em html como a que você está vendo.

### Adicionando doxygen ao projeto
Imagine que você queira adicionar doxygen ao seu projeto com a seguinte estrutura

    ├── Projeto
    │   ├── Inc
    │   │   ├── main.hpp
    │   ├── Src
    |   |   ├── main.cpp

Adicionar doxygen ao projeto nem sempre é a coisa mais simples ou direta, visando o tempo que nossos membros gastariam nisso ja montamos um repostitório com o necessário para que pelo menos o basico seja feito. Você pode acessar ele por [aqui](https://github.com/EESC-USP-TUPA/Tupa-Docs-Template)

Deste repósitorio apenas a pasta Docs é realmente necessária para que o doxygen consiga compilar a documentação no seu computador, você poderia colar ela no seu projeto ficando com a seguinte estrutura.

    ├── Projeto
    |   ├── Docs
    |   |   ├── custom-pages
    |   |   |   ├── 1_PaginaInicial.md
    |   |   ├── Doxyfile
    |   |   ├── ...
    │   ├── Inc
    │   │   ├── main.hpp
    │   ├── Src
    |   |   ├── main.cpp

E pronto, agora ao abrir o cmd na pasta do projeto e digitar 

    doxygen Docs/Doxyfile

O doxygen vai automaticamente escanear todas as pastas dentro do seu projeto a procura de arquivos com os quais ele possa montar a documentação

Um passo importante que você provavelmente vai querer seguir antes de compilar é colocar um nome para o seu projeto, para isso você pode ir na Doxyfile e modificar os seguintes campos

    PROJECT_NAME           = Nome do seu projeto
    PROJECT_NUMBER         = Versão do seu projeto

Para acessar a documentação gerada basta que você abra o seguinte arquivo html no seu navegados

    ├── Projeto
    |   ├── Docs
    |   |   ├── html
    |   |   |   ├── index.html

### Colocando notas sobre classes e funções usando comentários
Para deixar a documentação de nossas classes e funções mais rica, podemos comentar o nosso código num formato que o Doxygen consiga entender e assimilar nas páginas dos elementos descritos

para comentar uma parte do código o processo é simples, e muito provavelmente você ja sabe como fazer

```c
//  Comentário em linha

/*
    Comentário em bloco
*/

int main()
{
    return 0;
}
```

O que o doxygen tem de extra são algumas marcações que melhoram nosso controle sobre como a visualização final do comentário vai sair

```c


/*
    @brief Soma dois numeros

    @details A função pede como entrada os inteiros a e b e soma 
    eles usando o operador de soma padrão do c++

    @param a Um dos numeros a se somado
    @param b O outro numero a ser somado

    @return O resultado de a + b
*/
int sum(int a, int b)
{
    return a + b;
}
```

As tags significam:

    @brief
Indica que o que vai ser escrito na proxima linha é uma descrição simples do que a função vai fazer

    @details
Indica que o que vai ser escrito nas próximas linhas é uma descrição detalhada de como a função funciona

    @param
Indica que você vai estar falando sobre um dos parametros da sua função

    @return
Indica que você vai estar falando sobre o que a função retorna

Você pode ver uma descrição um pouco mais detalhada sobre essas tags [aqui](https://www.rosettacommons.org/docs/latest/development_documentation/tutorials/doxygen-tips#common-doxygen-tags_common-source-document-tags)

### Escrita de paginas em markdown
Em certos casos queremos ir um pouco além da descrição de codigo e adicionar um algo a mais á nossa documentação, para isso podemos usar a linguagem de markdown.

Na pasta Docs do seu projeto você vai poder encontrar uma subpasta chamada de custom_pages

    ├── Projeto
    |   ├── Docs
    |   |   ├── custom-pages
    |   |   |   ├── 1_PaginaInicial.md

Nela você vai encontrar um arquivo chamado 1_PaginaInicial.md, esse arquivo é especial no sentido que vai ser o arquivo que vai sair na página inicial da sua documenteção e você pode customiza-lo como quiser

Mas você não é limitado a ele, você pode criar outros arquivos, estes que serão tratados como páginas diferentes. Para ordenar esses arquivos você pode nomea-los com numeros como prefixos.

    ├── Projeto
    |   ├── Docs
    |   |   ├── custom-pages
    |   |   |   ├── 1_PaginaInicial.md
    |   |   |   ├── 2_PaginaDoMeio.md
    |   |   |   ├── 3_PaginaFinal.md

## Upando documentação para o github pages
