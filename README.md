# Estudo de Arquitetura AWS com Amazon EC2

Estudo conceitual desenvolvido como parte de um desafio da **DIO**, após aulas introdutórias sobre computação em nuvem e serviços da AWS.

O objetivo foi representar uma arquitetura simples para publicação de uma aplicação, identificando a responsabilidade do Amazon EC2, Amazon EBS, Amazon S3 e Security Groups.

> **Escopo do projeto:** este repositório apresenta uma proposta de arquitetura para fins educacionais. Os recursos não foram provisionados em uma conta AWS e não representam uma infraestrutura em produção.

## Arquitetura proposta

![Diagrama conceitual de uma arquitetura AWS com usuário, internet, Security Group, EC2, EBS e S3](arquitetura-aws.drawio.png)

O diagrama representa o seguinte fluxo:

1. O usuário acessa uma aplicação pela internet.
2. O Security Group permite somente o tráfego autorizado para a instância.
3. A instância Amazon EC2 executa a aplicação.
4. Um volume Amazon EBS mantém o armazenamento em bloco associado à instância.
5. O Amazon S3 armazena objetos, como arquivos, imagens ou backups.

## Serviços estudados

### Amazon EC2

Serviço de computação que disponibiliza instâncias virtuais para executar aplicações. Em uma implementação real, seria necessário escolher região, zona de disponibilidade, imagem do sistema operacional, tipo de instância e forma de acesso.

### Amazon EBS

Armazenamento em bloco utilizado por instâncias EC2. Pode armazenar o sistema operacional, arquivos da aplicação e outros dados que precisam permanecer além do ciclo de execução do processo.

### Amazon S3

Serviço de armazenamento de objetos. Na arquitetura proposta, poderia receber arquivos estáticos e backups, evitando concentrar todos os dados no disco da instância.

### Security Group

Firewall virtual que controla o tráfego de entrada e saída dos recursos associados. As regras devem liberar apenas portas e origens estritamente necessárias.

## Decisões de segurança para uma implementação real

- Restringir o acesso administrativo a origens confiáveis.
- Expor somente as portas necessárias para a aplicação.
- Evitar acesso público irrestrito ao bucket S3.
- Utilizar permissões IAM com o princípio do menor privilégio.
- Não armazenar chaves, credenciais, IDs de recursos ou endereços IP no repositório.
- Manter sistema operacional e dependências atualizados.

## Custos e encerramento dos recursos

Em um laboratório real, EC2, EBS, S3, transferência de dados e outros componentes podem gerar cobranças. Após os testes, seria necessário:

- Encerrar instâncias que não fossem mais utilizadas.
- Excluir volumes EBS e snapshots desnecessários.
- Remover objetos e buckets criados apenas para o laboratório.
- Revisar o painel de faturamento e configurar alertas de custo.

## Aprendizados demonstrados

- Identificação dos componentes básicos de uma arquitetura na AWS.
- Diferença entre computação, armazenamento em bloco e armazenamento de objetos.
- Papel do Security Group na proteção do tráfego.
- Representação visual do fluxo entre usuário e serviços.
- Atenção a segurança, custos e ciclo de vida dos recursos.

## Limitações

- A arquitetura não foi provisionada na AWS.
- Não há aplicação implantada, métricas, logs ou testes de disponibilidade.
- Região, tipo de instância, sistema operacional e regras de rede não foram definidos.
- O diagrama não representa alta disponibilidade, balanceamento de carga ou escalabilidade automática.

Esses itens podem ser explorados futuramente em um laboratório prático controlado, com atenção aos limites de uso e possíveis custos da AWS.

## Autora

**Jéssica Trindade**

[GitHub](https://github.com/jessicatrindadeads) • [LinkedIn](https://www.linkedin.com/in/jessicatrindadeads/)
