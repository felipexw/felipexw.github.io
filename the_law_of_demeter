Nesse artigo será abordada uma heurística (diga-se princípio) de design orientado a objetos pouco conhecido – embora devesse ser bastante utilizado -: The Law of Demeter. 
Esse princípio declara que um módulo ou uma unidade não deveria conhecer o comportamento interno um objeto que o mesmo manipula. Transcrevendo em outras palavras, um objeto não deveria expor sua estrutura interna por intermédio dos métodos assessores, pois ao expor sua estrutura interna o seu encapsulamento será invariavelmente quebrado.
Mais precisamente the Demeter law declara que um método M de uma classe C deveria conhecer somente métodos:
- pertencentes a C;
- de um objeto O criado por M;
- de um objeto O passado por parâmetro para M;
- de um objeto de classe de C;
A figura abaixo ilustra esse cenário.
final String caminhoDiretorio = context.getOpcoes().getDiretorioOrigem().getCaminhoAbsoluto();
Qual é o problema com esse código?
Bem, há vários problemas:
1)	Esse “módulo” sabe que o objeto contexto contém opções;
2)	Esse “módulo” sabe que dentro do objeto DiretorioRaiz há o caminho absoluto (uma propriedade interna deste objeto).
Desse modo, nesse trecho de código, há muita informação para um único método, e como se não bastasse, o encapsulamento foi quebrado, pois a entidade Opcoes está expondo o DiretorioOrigem, e o este último está expondo o seu caminho absoluto (quebra de encapsulamento).
Bem, em apenas uma linha de código foram encontrados vários problemas. Então, como resolvê-los?
Esse é o assunto do próximo post, onde evidentemente, esse conceito será abordado mais a fundo, bem como a solução para esse problema será proposta.
