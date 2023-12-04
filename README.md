# Implementação

## Cadastro do Perfil

Realizamos ajustes para separar o cadastro de perfil do cadastro de serviços, permitindo que os usuários forneçam informações específicas para cada um dos casos. Isso proporciona maior flexibilidade aos usuários, permitindo-lhes cadastrar quantos serviços desejarem de forma independente.

## Cadastro de Serviços

* Ao cadastrar um serviço, agora solicitamos informações sobre as redes sociais do usuário que oferece o serviço.
* Na pesquisa de serviços (Opção 6), implementamos uma condição adicional para não exibir os serviços cadastrados pelo próprio usuário, apenas os serviços de terceiros.
* Modificamos a opção 9 (Avaliar Perfil) para evitar que o usuário avalie a si mesmo.
* Adicionamos a opção 10 (Visualizar Meus Serviços) para permitir que os usuários vejam os serviços que cadastraram.
* Implementamos uma verificação para determinar se um usuário existe no banco de dados, oferecendo maior segurança e controle sobre a manipulação de dados.