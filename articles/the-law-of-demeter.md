###The Law of Demeter###

##Introdução
The demeter's law é uma heurística de design de software orientado a objetos, diga-se princípio, pouco conhecida - – embora devesse ser bastante utilizado, por ser relativamente simples e ao mesmo tempo pode evitar futuros bugs.
  Esse princípio declara que um módulo ou uma unidade não deveria conhecer o comportamento interno um objeto que o mesmo manipula. 
Transcrevendo em outras palavras, um objeto não deveria expor sua estrutura interna por intermédio dos métodos assessores, pois ao expor sua estrutura interna o seu encapsulamento será invariavelmente quebrado.
Mais precisamente the Law of Demeter declara que um método *M* de uma classe *C* deveria conhecer somente métodos:
- pertencentes a *C*;
- de um objeto *O* criado por *M*;
- de um objeto *O* passado por parâmetro para *M*;
- de um objeto de classe de *C*;
A figura abaixo ilustra esse cenário.

![Um exemplo prático da violação do conceito de The Law of Demeter](http://imagizer.imageshack.us/v2/665x29q90/903/7S5gXP.png)

__Qual é o problema com esse código?__

Bem, há vários problemas:
* O método em que esse trecho de código está escrito sabe que o objeto contexto contém um objeto do tipo Opcoes. Até aí tudo bem, o problema é que dentro de _Opcoes_ há um método nomeado de _getDiretorioOrigem()_ que retorna um objeto do tipo _DiretorioOrigem_, que por sua vez possui um método chamado de _getCaminhoAbsoluto()_ que retorna o caminho absoluto.
* __O problema é que este método possui muito conhecimento.__ Em outras palavras, esse método sabe que dentro do objeto _DiretorioRaiz_ há o caminho absoluto (uma propriedade interna deste objeto).
Desse modo, nesse trecho de código, há muita informação para um único método, e como se não bastasse, o encapsulamento foi quebrado, pois a entidade _Opcoes_ está expondo o _DiretorioOrigem_, e o este último está expondo o seu caminho absoluto (quebra de encapsulamento).
Bem, em apenas uma linha de código foram encontrados vários problemas. 

__Então, como resolvê-los?__


##Referências##
_Clean Code: A Handbook for Software Agile Craftsmanship._
