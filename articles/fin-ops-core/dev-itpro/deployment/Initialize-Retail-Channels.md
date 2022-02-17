---
title: Inicializar a Commerce Scale Unit (nuvem)
description: Este tópico explica como inicializar a Commerce Scale Unit (nuvem) no Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2018-4-30
ms.openlocfilehash: 84e70515accde161e7efa36755edec68d26be952
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092204"
---
# <a name="initialize-commerce-scale-unit-cloud"></a>Inicializar a Commerce Scale Unit (nuvem)

[!include[banner](../includes/banner.md)]

Este tópico explica como inicializar a Commerce Scale Unit (nuvem) no Microsoft Dynamics 365 Commerce.

Se você estiver usando uma área restrita ou ambiente de produção de nível 2 que tenha a versão do aplicativo 8.1.2. x ou posterior, você deve inicializar a Commerce Scale Unit (nuvem) antes de poder usar a funcionalidade de canal de varejo para operações de ponto de venda (PDV) ou de comércio eletrônico que usam o Retail Server na nuvem. A inicialização implantará uma Commerce Scale Unit (nuvem).

> [!IMPORTANT]
> Para clientes existentes que usam a funcionalidade de canal de varejo na nuvem, para garantir o suporte contínuo e ininterrupto para a sua empresa, precisamos atualizar seus canais de varejo para usar a Commerce Scale Unit. Os novos ambientes implantados sem Commerce Scale Unit não receberão mais qualidade e atualizações de serviço para componentes de canal de varejo hospedados na nuvem. Não há nenhuma ação necessária para clientes que usam exclusivamente a Commerce Scale Unit (hospedado no servidor). Entre em contato com o FastTrack solution architect se precisar de uma extensão.

## <a name="prerequisites"></a>Pré-requisitos

1. Implantar uma área restrita ou ambiente de produção de nível 2 que tenha a versão 8.1.2. x ou posterior.
2. Você pode fazer a autoimplantação de até duas Commerce Scale Units por ambiente. Se você precisar de mais de duas Commerce Scale Units por ambiente, no Microsoft Dynamics- Lifecycle Services (LCS), criar uma solicitação de suporte e inserir **Solicitação para a Commerce Scale Unit adicional** e indicar a ID do ambiente, o número de unidades de Commerce Scale Unit e as regiões de datacenter desejadas. A solicitação será concluída dentro de cinco dias úteis. Se você não precisar de mais de duas Commerce Scale Units, não será necessário criar uma solicitação de suporte. 
3. Você deve ter permissões do proprietário do projeto no Lifecycle Services antes de poder inicializar a Commerce Scale Unit.
4. Verifique se as chaves de configuração de licença de varejo estão habilitadas no seu ambiente. Para mais informações, consulte [Relatório de códigos de licença e chaves de configuração](../sysadmin/license-codes-configuration-keys-report.md). Você deve ter as seguintes chaves ativadas para usar a Commerce Scale Unit.

    - RetailBasic
    - RetaileCommerce-se você planeja usar o comércio eletrônico para o Dynamics 365 Commerce.
    - RetailGiftCard-se você planeja usar cartões de presente.
    - RetailInvent-se você planeja usar o estoque.
    - RetailModernPos-se você planeja usar o ponto de venda (PDV).
    - RetailReplenishment - se você planeja usar reabastecimento.
    - RetailScheduler
    - RetailStores - se você planeja usar o PDV.


## <a name="region-availability"></a>Disponibilidade da região
A Commerce Scale Unit está disponível para implantação nas seguintes regiões.

| Localização global | Região              | Disponibilidade        |
|-----------------|---------------------|---------------------|
| AMÉRICAS        | Leste dos EUA             | Geralmente disponível |
| AMÉRICAS        | Leste dos EUA 2           | Geralmente disponível |
| AMÉRICAS        | Norte Central dos EUA    | Geralmente disponível |
| AMÉRICAS        | Central Sul dos EUA    | Geralmente disponível |
| AMÉRICAS        | EUA Central          | Geralmente disponível |
| AMÉRICAS        | Oeste dos EUA             | Geralmente disponível |
| AMÉRICAS        | Oeste dos EUA 2           | Geralmente disponível |
| AMÉRICAS        | Canadá Central      | Capacidade limitada    |
| AMÉRICAS        | Leste do Canadá         | Capacidade limitada    |
| AMÉRICAS        | Centro-Oeste dos EUA     | Capacidade limitada    |
| APAC            | Leste da Austrália      | Geralmente disponível |
| APAC            | Sudeste da Ásia      | Geralmente disponível |
| APAC            | Leste do Japão          | Geralmente disponível |
| APAC            | Oeste do Japão          | Geralmente disponível |
| APAC            | Sudeste da Austrália | Capacidade limitada    |
| APAC            | Leste da Ásia           | Capacidade limitada    |
| APAC            | Sul da Índia         | Capacidade limitada    |
| APAC            | Índia Central       | Capacidade limitada    |
| EMEA            | Oeste da Europa         | Geralmente disponível |
| EMEA            | Norte da Europa        | Geralmente disponível |
| EMEA            | Sul do Reino Unido            | Capacidade limitada    |
| EMEA            | Oeste do Reino Unido             | Capacidade limitada    |

A capacidade de implantação em regiões com capacidade limitada é extremamente restrita. As solicitações de implantação são avaliadas de acordo com cada caso. Se você tiver uma necessidade comercial convincente para implantação em regiões com capacidade limitada, poderá arquivar uma solicitação de suporte a ser adicionada à lista de espera.

![Mapa mostrando a disponibilidade da região.](media/Commerce-Scale-Unit-Region-Availability.png "Mapa exibindo a disponibilidade da região")

## <a name="initialize-commerce-scale-unit-as-part-of-a-new-environment-deployment"></a>Inicializar a Commerce Scale Unit como parte de uma nova implantação de ambiente

Certifique-se de que a sede está disponível. Isso é necessário para registrar a unidade de escala nas matrizes durante o processo de inicialização. Não é recomendável inicializar uma unidade de escala quando as matrizes estão em manutenção, pois ela pode se tornar disponível durante o processo de manutenção.

1. Verifique se o ambiente da sede está disponível e não no modo de [Manutenção](../sysadmin/maintenance-mode.md).
2. Em LCS, na página de detalhes do ambiente, selecionar **Recursos do ambiente \> Comercial**.
3. Na página Implantação da configuração comercial, selecionar **Inicializar**.
4. Selecionar a versão da Commerce Scale Unit a ser inicializada.
5. Selecionar a versão a ser inicializada da Commerce Scale Unit.

## <a name="configure-channels-to-use-commerce-scale-unit"></a>Configurar canais para usar a Commerce Scale Unit

Após a implantação da Commerce Scale Unit, você deve garantir que os canais estão configurados para usar o banco de dados para ele. 

Para configurar os canais para usar o banco de dados da Commerce Scale Unit, siga estas etapas.

1. Na matriz do Commerce, acesse **Varejo e comércio \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce**.
1. No painel esquerdo, selecionar um banco de dados do canal.
1. Na guia rápida **Canal de varejo**, selecionar **Adicionar** e, então, selecionar seu canal de varejo na lista suspensa.
1. Selecionar **Adicionar** e selecionar seu canal on-line na lista suspensa. 

Ao concluir, acesse **Varejo e comércio \> TI de varejo e comércio \> Agenda de distribuição** e execute o trabalho 9999.

> [!NOTE] 
> O trabalho 9999 sincroniza todos os novos produtos e clientes com a Commerce Scale Unit. Esse processo pode levar um tempo. Se o canal precisar estar disponível apenas para a configuração do criador de site de comércio eletrônico, você poderá executar o trabalho 1070 em vez do trabalho 9999.

### <a name="database-refresh-and-commerce-scale-units"></a>Commerce Scale Units e atualização de banco de dados

Antes de começar, verifique se você está familiarizado com as [Etapas para concluir após uma atualização de banco de dados para ambientes que usam a funcionalidade Commerce](../database/database-refresh.md).

Os registros do banco de dados do canal da unidade de escala (no formulário banco de dados do canal) não podem ser movidos entre ambientes como parte da atualização do banco de dados. Isso ocorre porque os registros representam a configuração específica do ambiente.

Após a atualização do banco de dados, você pode regenerar o registro do banco de dados do canal da unidade de escala emitindo uma nova implantação da sua unidade de escala no LCS. Qualquer implantação ou operação de manutenção na unidade de escala tentará registrar a unidade de escala na matriz, caso o registro seja detectado como ausente.

Você pode emitir uma nova implantação da unidade de escala, sem alterar nenhum componente, selecionando, para implantar a mesma versão, sua unidade de escala já aplicada. Isso pode ser feito no LCS pelas seguintes etapas:

1. Em LCS, na página de detalhes do ambiente, selecionar **Recursos do ambiente \> Varejo**.
2. Na página de implantação da instalação, selecionar a unidade de escala que deseja reimplantar.
3. No menu de operações da unidade de escala, selecione **Atualizar**.
4. No controle deslizante, na lista suspensa para a **Versão selecionada**, escolha a opção **Especifique uma versão**.
5. Na caixa de texto, em **Especifique uma versão**, digite a versão mostrada para a unidade de escala, mostrada além da etiqueta da **Versão atual**.
6. Clicar no botão **Atualizar**.

Não é necessário selecionar **Extensões de atualização**, mesmo que você tenha aplicado anteriormente extensões, pois o último pacote de extensão aplicado à unidade de escala é separado automaticamente ao atualizar uma unidade de escala.

Se você tiver várias unidades de escala, será necessário executar a operação acima para cada unidade de escala. Você pode executar essas operações em paralelo, se desejado.

## <a name="deploy-additional-commerce-scale-units-optional"></a>Implantar Commerce Scale Units adicionais (opcional)

Depois de inicializar a Commerce Scale Unit, você pode fazer a implantação de uma unidade de segunda escala se a licença lhe autorizar isso. Para implantar mais de duas unidades de escala, você deve criar uma solicitação de suporte. Na solicitação de suporte, informe o número de Commerce Scale Unit necessárias, o nome do ambiente e as regiões desejadas. Para obter mais informações sobre essas licenças, consultar [Guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409). 

Para cada Commerce Scale Unit implantada, recomendamos que você crie um grupo de bancos de dados de canal separado seguindo essas etapas.

1. Na matriz do Commerce, acesse **Varejo e comércio > Retail Headquarters > Agendador do Retail > Grupo de banco de dados do canal**.
2. Criar um novo grupo de bancos de dados de canal.
3. Vá para o **Varejo e comércio > Retail Headquarters > Configuração do Agendador do Retail > Banco de dados do canal** e selecione o banco de dados do canal que corresponde à Commerce Scale Unit recém-criada.
4. Selecionar **Editar** e selecionar o novo grupo de banco de dados do canal.
5. Selecione **Salvar**.
6. Selecionar **Executar sincronização de dados** para o banco de dados do canal selecionado.

## <a name="additional-considerations-if-you-initialize-cloud-hosted-commerce-channel-components-in-an-existing-environment"></a>Considerações adicionais se você inicializar componentes de canal comerciais hospedados em nuvem em um ambiente existente

Se você já estiver usando componentes de canal comerciais hospedados em nuvem em um ambiente, a inicialização da Commerce Scale Unit ajudará a reduzir o tempo de inatividade quando esses componentes forem atualizados. É necessário planejamento adicional antes da inicialização da Commerce Scale Unit.

Quando você inicializa sua primeira Commerce Scale Unit em um ambiente que usa componentes de canal comerciais hospedados na nuvem, o processo de inicialização migrará os canais associados aos componentes de canal hospedados na nuvem para a primeira unidade de escala. Os canais associados às unidades de escala de armazenamento não são afetados.

O processo de migração é transparente para os canais. Depois que a inicialização da unidade de escala é iniciada, as seguintes operações são executadas automaticamente:

1. Uma nova Commerce Scale Unit será criada e associada ao ambiente.
2. A Commerce Scale Unit será registrada como um banco de dados de canal disponível na matriz.
3. Todos os canais mapeados para o **Banco de dados do canal padrão** na matriz serão atualizados para mapear a nova Commerce Scale Unit.
4. Uma sincronização de dados completa do Commerce Data Exchange (CDX) será executada para trazer os dados do canal para a nova unidade de escala.

**Planejamento e teste para a inicialização da Commerce Scale Unit** Como regra geral, ao inicializar a unidade de escala comercial, você deve planejar uma janela de tempo de inatividade de cinco horas para operações de armazenamento, bem como qualquer operação de canal de comércio eletrônico que use o Retail Server ou o ponto de venda da nuvem.

1. Executar uma atualização de banco de dados do ambiente de produção para um ambiente de UAT de área restrita. 
2. Inicializar a Commerce Scale Unit no ambiente de área restrita de UAT. 
3. Observe o tempo de inicialização para concluir a Commerce Scale Unit. Isso será comparável ao tempo que esta operação leva no ambiente de produção, durante o qual as operações de armazenamento e as operações de comércio eletrônico não estarão disponíveis.

Você deve executar as seguintes etapas adicionais antes de inicializar a Commerce Scale Unit.

- **Fechar todos os turnos do PDV** - Após a migração, os usuários do PDV não poderão fechar os turnos que estavam ativos durante o processo de migração.
- **Validar que todos os P-jobs foram concluídos com êxito** - é recomendável que P-jobs para sincronizar transações pendentes tenham sido concluídos antes que o CSU seja inicializado.
- **Sair de todos os dispositivos de PDV** Operações PDV não têm suporte durante a migração.
- **Cancelar e anular todas as transações suspensas no PDV** - As transações suspensas não são preservadas como parte da inicialização.

> [!IMPORTANT]
> Como parte da inicialização da Commerce Scale Unit, as transações suspensas anteriores serão perdidas e não poderão ser recuperadas. 

Veja o que ocorre durante o período de inicialização:

- Os canais comerciais hospedados na nuvem não funcionarão, a menos que você ative a funcionalidade PDV offline.
- Os dispositivos PDV com capacidade offline ativada terão funcionalidade reduzida.
- Qualquer cliente de comércio eletrônico que dependa do Retail Server será interrompido.
- Os canais que estão hospedados nas Commerce Scale Units (hospedados no servidor) não serão afetados.
- A funcionalidade do escritório principal não é afetada.

Veja o que ocorre após a inicialização ser concluída:

- O estado de ativação do dispositivo de todos os dispositivos PDV ativados é preservado, o que significa que os dispositivos não precisarão ser reativados.
- As instâncias de estação de hardware autônomo continuarão funcionando.
- Os relatórios do canal PDV serão redefinidos e não mostrarão os dados antes da inicialização.
- A operação mostrar diário também será redefinida e não mostrará os dados antes da inicialização.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
