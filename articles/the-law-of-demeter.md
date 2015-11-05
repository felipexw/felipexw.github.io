###The Law of Demeter###

##Introdução
The demeter's law é uma heurística de design de software orientado a objetos pouco conhecida.
#Objetivo#
Nesse artigo será abordada uma heurística (diga-se princípio) de design orientado a objetos pouco conhecido – embora devesse ser bastante utilizado, por ser relativamente simples e ao mesmo tempo pode evitar futuros bugs.

##O que é The Demeter's Law?##
Esse princípio declara que um módulo ou uma unidade não deveria conhecer o comportamento interno um objeto que o mesmo manipula. Transcrevendo em outras palavras, um objeto não deveria expor sua estrutura interna por intermédio dos métodos assessores, pois ao expor sua estrutura interna o seu encapsulamento será invariavelmente quebrado.
Mais precisamente the Law of Demeter declara que um método *M* de uma classe *C* deveria conhecer somente métodos:
- pertencentes a *C*;
- de um objeto O criado por *M*;
- de um objeto O passado por parâmetro para *M*;
- de um objeto de classe de *C*;
A figura abaixo ilustra esse cenário.
*final String caminhoDiretorio = context.getOpcoes().getDiretorioOrigem().getCaminhoAbsoluto();*
__Qual é o problema com esse código?__
Bem, há vários problemas:
1. Esse “módulo” sabe que o objeto contexto contém opções;
2. Esse “módulo” sabe que dentro do objeto DiretorioRaiz há o caminho absoluto (uma propriedade interna deste objeto).
Desse modo, nesse trecho de código, há muita informação para um único método, e como se não bastasse, o encapsulamento foi quebrado, pois a entidade Opcoes está expondo o DiretorioOrigem, e o este último está expondo o seu caminho absoluto (quebra de encapsulamento).
Bem, em apenas uma linha de código foram encontrados vários problemas. Então, como resolvê-los?
Esse é o assunto do próximo post, onde evidentemente, esse conceito será abordado mais a fundo, bem como a solução para esse problema será proposta.

##Referências##
_Clean Code: A Handbook for Software Agile Craftsmanship._
