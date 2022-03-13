# Inicio

## Porque criar documentação?

Imagine a seguinte função no seu código

```c
int soma(int a, int b)
{
    return a + b;
}
```

Apenas pelo nome da função podemos ter uma boa ideia de o que ela faz e o que ela retorna.
Mas imaginando o seguinte exemplo

```c
hadc* ler_hadc(ADC alvo) 
{
    return alvo.hadc;
}
```

O que é hadc? Que tipo de parametro é uma ADC? O que significa o parametro alvo?

Nem sempre um bom nome de função nos dá informação suficiente para saber o que ela faz, e no nosso caso (mexendo com programação de embarcados) as coisas fazem menos sentido ainda.

Pensando nesses casos nós tivemos a ideia da documentação do software onde motamos um recurso para que nossos membros consigam tirar melhor proveito do código que escrevemos.

Feita do software para o software

## Projetos
- [TAL](https://andreycortez.github.io/TAL/)