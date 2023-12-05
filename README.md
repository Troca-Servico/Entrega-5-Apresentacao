# Implementação

## Cadastro do Perfil

Realizamos ajustes para separar o cadastro de perfil do cadastro de serviços, permitindo que os usuários forneçam informações específicas para cada um dos casos. Isso proporciona maior flexibilidade aos usuários, permitindo-lhes cadastrar quantos serviços desejarem de forma independente.

## Cadastro de Serviços

* Ao cadastrar um serviço, agora solicitamos informações sobre as redes sociais do usuário que oferece o serviço.
* Na pesquisa de serviços (Opção 6), implementamos uma condição adicional para não exibir os serviços cadastrados pelo próprio usuário, apenas os serviços de terceiros.
* Modificamos a opção 9 (Avaliar Perfil) para evitar que o usuário avalie a si mesmo.
* Adicionamos a opção 10 (Visualizar Meus Serviços) para permitir que os usuários vejam os serviços que cadastraram.
* Implementamos uma verificação para determinar se um usuário existe no banco de dados, oferecendo maior segurança e controle sobre a manipulação de dados.

## Banco de dados 

Realizamos otimizações nas tabelas perfil e servicos, proporcionando um ambiente mais robusto e completo para armazenar informações relacionadas a perfis de usuários e prestação de serviço

### Tabela perfil
A tabela perfil é projetada para conter informações essenciais do cadastro de usuários
```
CREATE TABLE `perfil` (
	`id` INT(11) NOT NULL AUTO_INCREMENT,
	`avaliacoes` VARCHAR(500) NOT NULL DEFAULT '0' COLLATE 'utf8mb4_general_ci',
	`areas_interesse` VARCHAR(500) NOT NULL COLLATE 'utf8mb4_general_ci',
	`ft_perfil` VARCHAR(500) NOT NULL COLLATE 'utf8mb4_general_ci',
	`habilidades` VARCHAR(500) NOT NULL DEFAULT '' COLLATE 'utf8mb4_general_ci',
	`nome` VARCHAR(50) NOT NULL COLLATE 'utf8mb4_general_ci',
	`sexo` ENUM('M','F') NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
	`idade` INT(3) NOT NULL,
	`cpf` VARCHAR(11) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
	`email` VARCHAR(50) NOT NULL COLLATE 'utf8mb4_general_ci',
	PRIMARY KEY (`id`) USING BTREE
)
COLLATE='utf8mb4_general_ci'
ENGINE=InnoDB
AUTO_INCREMENT=3
;
```

### Tabela servicos
A tabela servicos é destinada a armazenar informações adicionais sobre os serviços prestados
```
CREATE TABLE `servicos` (
    `id` INT NOT NULL AUTO_INCREMENT,
    `area` VARCHAR(500) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `desc_serv` VARCHAR(500) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `cidade` VARCHAR(500) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `bairro` VARCHAR(500) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `tempo_ex` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `cpf` VARCHAR(11) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `whatsapp` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `instagram` VARCHAR(300) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `facebook` VARCHAR(300) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `linkedin` VARCHAR(300) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    PRIMARY KEY (`id`)
)
AUTO_INCREMENT=1
COLLATE='utf8mb4_general_ci'
ENGINE=InnoDB;

ALTER TABLE servicos
MODIFY COLUMN linkedin VARCHAR(300) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci';

```


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Link da apresentação:

https://www.canva.com/design/DAF18hoWK3Q/5om1Fv1bNb7ULcH9nZCU0g/view?utm_content=DAF18hoWK3Q&utm_campaign=designshare&utm_medium=link&utm_source=editor#19

