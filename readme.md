# Especificações

- Imagens
    - Miniaturas
    
    É necessário adicionar as miniaturas no diretório ``` memefy-client/img ```. As miniaturas precisar ter as dimensões (165x165).
    
    - Base
    
    As imagens devem precisam estar no diretório ``` memefy-server/public/images/meme ``` do servidor de memes. Para elas serem reconhecidas, é necessário adicioná-las no arquivo ``` memes.yml ``` seguindo as regras lá definidas. As imagens precisam conter as dimensões (600x600).
    
    - Integração
    
    Para reconhecer as imagens, o cliente deve preencher um array contendo os aliases do servidor. Esse array pode ser encontrado em ``` memefy-client/index.html ``` em ```js $scope.properties.aliases ```.
    Por exemplo:
    - Servidor
    (memes.yml)
    ```yaml
        aliensguy:
          :name: Aliens Guy
          :width: 540
          :alias: aliens
          :top:  
          :bottom: meme creators
    ```
    
    - Cliente
    ($scope.properties.aliases)
    ```js
        /**
         * <nome_local_da_imagem> : <alias_no_servidor>
         */
        $scope.properties.aliases {
            "1" : "aliensguy"
        };
    ```
    
    Dessa forma, a url poderá ser criada para a imagem 1 ou "aliensguy"

- URL
    
    A url funciona com o seguinte formato: ``` http://<servidor>/<texto_topo>/<texto_base>/<alias_imagem> ```
    
    - Servidor
        
        O servidor atual é o memefy.herokuapp.com
    
    - Textos
        
        Caso não seja informado um dos textos, obrigatóriamente o texto sera posto na parte de baixo
    
    - Alias da imagem
    
        O alias da imagem pode funcionar de duas maneiras:             
        1. Fornecendo o alias cadastrado no ``` memes.yml ```
        2. Fornecendo a url completa de uma imagem externa* ao servidor
        
        
            * Fornecer um alias que redireciona ao servidor fornece um meme de erro.

# Instalando

Utilizando um servidor PaaS é bem simples. Basta instalar o git na máquina local e fazer um ```git clone <url do .git do repositório>``` e no caso do heroku, executar o comando ``` heroku create ``` e o app estará funcionando.




