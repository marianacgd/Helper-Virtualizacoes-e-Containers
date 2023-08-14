# Helper-Virtualizacoes-e-Containers
Ajuda com Virtualizações e Container

# Virtualização

## O que é?

- Virtualização é uma tecnologia que permite a criação de ambientes virtuais isolados a partir de um único servidor físico.

- Consiste em executar múltiplas máquinas virtuais (VMs) ou ambientes virtuais em um único hardware físico.

- Cada VM é um sistema operacional completo e independente, com recursos como CPU, RAM e armazenamento próprios.

- Essa abordagem permite a consolidação de vários servidores virtuais em um único servidor físico.

- A virtualização possibilita a utilização mais eficiente dos recursos de hardware, reduzindo custos operacionais e de manutenção.

## Pra que serve?

- Maior eficiência: Melhora a utilização de recursos, permitindo que múltiplas VMs compartilhem o mesmo hardware físico.

- Isolamento: Cada VM é independente, garantindo que problemas em uma VM não afetem as outras, aumentando a segurança e a estabilidade.

- Flexibilidade: As VMs podem ser facilmente movidas entre servidores físicos, permitindo a migração de recursos para balanceamento de carga ou manutenção.

- Testes e Desenvolvimento: Ambientes virtuais oferecem um ambiente seguro para testar e desenvolver software sem afetar a infraestrutura real.

- Recuperação de Desastres: Através de snapshots e backups, é possível criar cópias de VMs para recuperação rápida em caso de falhas ou desastres.

## Como Funciona?

- Hypervisor: Software responsável por gerenciar a virtualização. Existem dois tipos principais de hypervisors: Type 1 (bare metal) e Type 2 (hosted).

- Type 1 Hypervisor: Executado diretamente no hardware físico, sem a necessidade de um sistema operacional hospedeiro. Exemplos incluem VMware vSphere/ESXi, Microsoft Hyper-V, e KVM.

- Type 2 Hypervisor: Executado em cima de um sistema operacional hospedeiro. Exemplos incluem VMware Workstation, Oracle VirtualBox e Microsoft Virtual PC.

- Máquinas Virtuais (VMs): Cada VM é um ambiente isolado e independente, com seu próprio sistema operacional, aplicativos e recursos dedicados.

- Recursos Alocados: O hypervisor divide os recursos físicos (CPU, RAM, armazenamento) em "partes" que são atribuídas a cada VM.

- Emulação de Hardware: O hypervisor emula hardware virtual para cada VM, permitindo que o sistema operacional dentro da VM acredite estar sendo executado em hardware físico real.

- Migração e Snapshot: A virtualização permite a migração de VMs entre servidores físicos em tempo real (Live Migration) e a criação de snapshots para backup e recuperação rápida.


# Container

## O que é?

- Containers são unidades de software que empacotam aplicações e suas dependências juntamente com bibliotecas e configurações necessárias para sua execução.

- Isolamento: Cada container é isolado do ambiente em que é executado, garantindo que as aplicações sejam independentes e não interfiram umas com as outras.

- Leveza: Containers compartilham o kernel do sistema operacional hospedeiro, tornando-os mais leves em comparação com máquinas virtuais completas.

- Portabilidade: Containers podem ser executados em qualquer ambiente que possua suporte para a tecnologia de containerização.

- Padronização: Com a padronização de containers, as aplicações podem ser desenvolvidas, testadas e implantadas de maneira consistente.

## Pra que serve?

- Agilidade: Os containers facilitam a implantação rápida e escalonável de aplicações, permitindo o desenvolvimento ágil e DevOps.

- Eficiência de Recursos: Como os containers compartilham o kernel do sistema operacional, é possível executar várias aplicações em um único host, maximizando o uso de recursos.

- Portabilidade: A portabilidade dos containers torna mais fácil mover aplicações entre ambientes locais, nuvem pública ou privada, e até mesmo entre diferentes sistemas operacionais.

- Versionamento e Rollback: É possível versionar os containers, permitindo o rollback para versões anteriores em caso de problemas.

- Escalabilidade: Containers podem ser dimensionados horizontalmente com facilidade, respondendo às demandas variáveis de tráfego e carga de trabalho.


# Virtualização vs. Container

## Diferenças

- Cada máquina virtual (VM) é um ambiente completo, incluindo sistema operacional, aplicativos e bibliotecas, replicando uma máquina física.

- Requer um hypervisor (Type 1 ou Type 2) para gerenciar as VMs e fornecer o isolamento entre elas.

- VMs têm maior sobrecarga, pois cada uma possui seu próprio sistema operacional e requer recursos significativos.

- Tempo de inicialização das VMs pode ser mais lento, pois é necessário inicializar o sistema operacional completo.

- Maior uso de recursos, como espaço em disco e memória RAM, devido à duplicação de sistemas operacionais.

- Todos os containers compartilham o mesmo kernel do sistema operacional hospedeiro, tornando-os mais leves e eficientes.

- Não requerem um hypervisor separado, pois são executados no mesmo kernel do sistema operacional.

- Containers são mais rápidos para iniciar, pois não há necessidade de inicializar um sistema operacional completo.

- Por compartilharem o kernel, há menor sobrecarga e uso eficiente de recursos.

- Containers são ideais para aplicações isoladas e independentes, onde a replicação de um sistema operacional completo não é necessária.

## Casos de uso

- A virtualização é mais adequada para ambientes onde é necessário executar diferentes sistemas operacionais lado a lado com isolamento completo.

- Containers são mais adequados para ambientes com aplicativos e serviços independentes, onde a eficiência de recursos e a implantação rápida são essenciais.


# Docker

Docker é uma plataforma de virtualização que permite empacotar e executar aplicativos em qualquer ambiente. 

Com o Docker, você pode empacotar todo o ambiente necessário para o seu aplicativo em um único contêiner, incluindo bibliotecas, dependências e configurações, e garantir que ele funcione da mesma forma em qualquer ambiente que execute o Docker.

Assim, Docker facilita a vida de desenvolvedores e operadores de sistemas criar, na hora de implantar e executar aplicativos em qualquer lugar, desde laptops até data centers em nuvem (DevOps).

## Arquitetura Docker

Client: quem estiver criando, subindo e executando containers.

Docker Host / Server: controla o que acontece com os containers; remoto ou local.

Docker Daemon: coordena interação entre cliente, servidor e registry.

Imagens: são os arquivos com todo conteúdo e estrutura das aplicações;

Registry: repositório para imagens docker, pode ser público ou privado. O Docker possui seu sistema próprio que se chama Docker Hub, é tipo um “github” para imagens docker.

Containers: são os ambientes de execução do Docker, criados a partir de imagens. Uma imagem é como um template de classe, e contêineres seriam instâncias dessas classes.

## Imagens Docker

- Imagens Docker são pacotes autocontidos que incluem tudo o que é necessário para executar um software, incluindo o código, bibliotecas, dependências, variáveis de ambiente e configurações.

- Elas são criadas a partir de um modelo chamado Dockerfile, que especifica as etapas necessárias para construir a imagem.

- As imagens são armazenadas em um registro, como Docker Hub, tornando-as facilmente acessíveis para compartilhamento e distribuição.

- Elas seguem o conceito de camadas, permitindo o reuso e a otimização do armazenamento.

- As imagens Docker facilitam a criação e a execução de aplicativos de forma consistente em diferentes ambientes.

Imagens Docker: Camadas(layers):

- Imagens Docker são compostas por camadas, que são partes individuais da imagem.

- Cada instrução no Dockerfile cria uma nova camada no processo de construção da imagem.

- As camadas são armazenadas em cache, o que possibilita a reutilização de camadas já existentes em imagens subsequentes.

- Alterações feitas em camadas superiores não afetam as camadas inferiores, garantindo isolamento e eficiência.

- O Docker usa um sistema de arquivos em camadas, onde cada camada contém apenas as diferenças em relação à camada anterior.

- A reutilização de camadas é uma das principais vantagens do Docker em relação à eficiência de armazenamento.

- Quando um Dockerfile é executado para criar uma nova imagem, as camadas existentes são reutilizadas sempre que possível.

- Se uma camada já existe em outra imagem ou em cache localmente, ela não precisa ser baixada ou recriada, economizando tempo e largura de banda.

- Essa reutilização também permite que várias imagens compartilhem as mesmas camadas de base, reduzindo significativamente o espaço de armazenamento necessário.

- A reutilização de camadas é especialmente benéfica ao lidar com atualizações frequentes, tornando o processo de construção mais rápido e eficiente.

ENV Vars:

- Variáveis de ambiente são valores dinâmicos que podem ser passados para um contêiner durante sua execução.

- Elas são usadas para configurar e personalizar o comportamento do aplicativo dentro do contêiner.

- As variáveis de ambiente podem incluir informações sensíveis, como senhas ou chaves de API, sem a necessidade de expô-las no código do aplicativo.

- Principais recursos e uso de variáveis de ambiente:

- Definidas no Dockerfile usando a instrução ENV.

- Passadas durante o tempo de execução usando a opção -e do comando docker run.

- Acessíveis dentro do contêiner pelo sistema operacional e pelo aplicativo em execução.

Volumes:

- Volumes são um mecanismo para persistir e compartilhar dados entre contêineres e o host.

- Permitem que os dados sobrevivam ao ciclo de vida do contêiner, mesmo se ele for removido.

- Volumes são usados para armazenar dados dinâmicos, como bancos de dados, uploads de usuários e arquivos de configuração.

- Principais recursos e uso de volumes:

- Podem ser montados em locais específicos dentro do contêiner usando a opção -v do comando docker run.

- Permitem compartilhar dados entre contêineres usando o mesmo volume em vários contêineres.

- Podem ser usados volumes anônimos ou volumes nomeados para melhor organização e gerenciamento.

Networking em Docker:

- O Networking permite que os contêineres compartilhem recursos, como serviços e dados, criando uma arquitetura distribuída.

- Existem diferentes modos de rede no Docker, como "bridge", "host" e "overlay", que se adequam a diferentes cenários.

- A rede "bridge" é a mais comum e cria uma rede interna onde os contêineres podem se comunicar usando seus nomes como hostnames.

Principais recursos de Networking em Docker:

- Exposição de Portas:

- Os contêineres podem expor portas para se comunicarem com o host ou com outros contêineres.

- Linking: permite que os contêineres se comuniquem diretamente através de um canal seguro.

- Docker Compose:simplifica o gerenciamento de redes, permitindo definir redes personalizadas e vincular serviços facilmente.

- Rede Overlay: é usada para conectar contêineres em hosts diferentes, criando um ambiente de cluster.

Gerenciamento Avançado:

- O Docker oferece opções avançadas de networking, como criar redes personalizadas, definir políticas de segurança e roteamento.

- Monitoramento de Rede:
 - Docker fornece ferramentas para monitorar o tráfego de rede entre contêineres e o host.




## ⚙️Ambiente Docker