# MuralApp

**[MuralApp.me](https://muralapp.me)** permite que o usuário realize buscas no banco de imagens [Pexels](https://www.pexels.com) e salve as imagens desejadas numa lista para análise e escolha do conjunto final. Ideal para designers que precisam pesquisar diversas fotos em bancos de imagens para criar uma seleção e, assim, escolher as imagens desejadas entre uma lista de selecionadas.

Este projeto foi desenvolvido com o objetivo de desenvolver e praticar meus conhecimentos recentes de Angular 9.

## API e HTTP Method
O Web App utiliza a [API da Pexels](https://www.pexels.com/api/documentation/#photos-search) para obter as imagens através de uma *GET Request*.

## Como funciona
Ao obter os resultados através da *GET Request*, o algoritmo constroi uma lista de imagens onde cada imagem segue o modelo construído no arquivo ```src/app/models/imagem.model.ts```. Enquanto o usuário aguarda pelos resultados, uma grid vazia preenche o espaço dos resultados para indicar ao usuário que a busca está sendo realizada.

Na lista de resultados de busca, o usuário tem a opção de adicionar quantas imagens desejar ao seu Mural; no Mural, o usuário tem as opções de abrir a imagem numa nova janela ou remover a imagem de sua lista.

![Busca e Mural](https://hugobrancowb.github.io/assets/img/buscamural.jpg)

Visando facilitar a experiência do usuário, o app utiliza a ID das imagens obtidas na busca para comparar com a lista de imagens selecionadas e destaca com uma borda verde aquelas imagens que já foram adicionadas ao Mural. O Mural fica salvo em _cookie_ por até 7 dias.

![Destaque para imagens já adicionadas ao Mural](https://hugobrancowb.github.io/assets/img/destaque.jpg)

## Compartilhe seu Mural
A nova funcionalidade implementada na versão 1.0.2 permite ao usuário que seu mural seja compartilhado com outros usuários através de um link. Ao escolher a opção de *Compartilhar Mural*, uma *POST Request* é realizada para salvar a lista em questão na database do servidor da **[MuralApp.me](https://muralapp.me)** e retorna ao usuário o link para compartilhamento.

Através do uso da *Angular RouterModule*, é possível obter o código do Mural compartilhado através do parâmetro encontrado no final da URL. O código é enviado ao servidor através de uma *GET Request* para obter a *array* de imagens desejada como resposta.

Utilize um dos links a seguir para experimentar o compartilhamento por links ou crie seu próprio Mural.

Exemplo 1: [muralapp.me/mural/asdfg](https://muralapp.me/mural/asdfg)<br/>
Exemplo 2: [muralapp.me/mural/670105b0](https://muralapp.me/mural/670105b0)<br/>
Exemplo 3: [muralapp.me/mural/a7addc60](https://muralapp.me/mural/a7addc60)

## Versões
### v1.0.2
- Adicionada funcionalidade que utiliza um POST Method para salvar um Mural na database do servidor e retornar ao usuário um link para compartilhar sua lista;
- Complementando o item anterior, tornou-se possível acessar um Mural salvo em database através de uma URL; essa feature se utiliza de parâmetros da URL para enviar uma GET Request ao servidor e obter a lista de imagens relacionada à ID em questão;
- Melhoria na UX para facilitar o compartilhamento de um Mural através de um link;
- Nova funcionalidade informa ao usuário a quantidade de imagens presente em seu Mural através de um indicador na _navbar_ do app;
- Cookies desativados devido a um limite no tamanho que impedia o armazenamento de mais que 3~4 imagens;
- Todas requisições _http_ são redirecionadas para _https_.
### v1.0.1
- Melhoria no favicon.ico do site;
- Adição de uma grid com placeholders ao executar uma busca para indicar seu processamento;
- Adição de botão de 'remover' nas imagens do search que já estão na lista; adição de botão de 'abrir externo' nas imagens do search;
- Previne o usuário de adicionar um placeholder à lista ou abrir link em janela externa;
- Memoriza o último mural salvo através de cookies + msg aviso de cookies.
### v1.0.0-mvp
Primeira versão lançada com funcionalidades mínimas.

## Outros projetos
Confira [meu portfólio](https://hugobrancowb.github.io/) para mais informações e outros projetos realizados.