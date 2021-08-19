---
title: Integrar as compras entre o Supply Chain Management e o Field Service
description: Este tópico descreve como a integração da gravação dupla oferece suporte a criação de ordens de compra e atualizações do Supply Chain Management e do Field Service.
author: RamaKrishnamoorthy
ms.date: 11/11/2020
ms.topic: article
audience: Application User
ms.reviewer: rhaertle
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 4a2420981553957b6b234fe56747bc6f3568acf6b8ad77366c33caeae63b4faf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716750"
---
# <a name="integrate-procurement-between-supply-chain-management-and-field-service"></a>Integrar as compras entre o Supply Chain Management e o Field Service

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

O Microsoft Dynamics 365 Supply Chain Management fornece uma funcionalidade robusta de compras. O Dynamics 365 Field Service fornece uma funcionalidade semelhante que oferece suporte aos processos de compras associados ao processo de serviço. As funcionalidades nesses dois aplicativos são integradas por meio de gravação dupla, e os casos de uso interfuncionais resultantes são habilitados por meio de mapeamentos de tabelas, lógica de solução, exibições e formulários.

Essa integração oferece suporte a criação de ordens de compra e, na maioria dos casos, atualizações dos dois aplicativos. No entanto, o Supply Chain Management controla preços, endereços e recebimento de produtos. Vários casos de uso interfuncionais poderosos são habilitados para organizações que usam o Field Service e o Supply Chain Management. Esses casos de uso permitem que as compras sejam iniciadas e rastreadas nos dois sistemas.

A ilustração a seguir mostra as tabelas nos dois sistemas e como elas são mapeadas entre si. As ordens de compra no Field Service fazem referência a uma linha de *conta*, enquanto as ordens de compra no Supply Chain Management fazem referência a uma linha de *fornecedor*. Para resolver a integração, a gravação dupla usa uma referência para vincular linhas de *fornecedor* a linhas de *conta*. Para obter mais informações, consulte [Fornecedor mestre integrado](vendor-mapping.md).

![Mapeamentos para compras.](media/scm-field-service-tables.png)

## <a name="prerequisites"></a>Pré-requisitos

Para integrar o Supply Chain Management ao Field Service, você deve instalar os seguintes componentes:

- Field Service versão 8.8.31.60 ou posterior, para uma integração abrangente das ordens de compra
- Supply Chain Management versão 10.0.14 ou posterior
- Gravação dupla, para executar a solução OneFSSCM

## <a name="installation-guidelines"></a>Diretrizes de instalação

### <a name="prerequisites"></a>Pré-requisitos

- **Gravação dupla** – para obter mais informações, consulte a [Home page da gravação dupla](dual-write-home-page.md#dual-write-setup).
- **Dynamics 365 Field Service** – para obter mais informações, consulte [Como instalar o Dynamics 365 Field Service](/dynamics365/field-service/install-field-service#step-1-install-dynamics-365-field-service).

Quando habilitados no Microsoft Dataverse, a gravação dupla e o Field Service introduzem várias camadas de solução que estendem o ambiente com novos metadados, formulários, exibições e lógica. Essas soluções podem ser habilitadas em qualquer ordem, embora a instalação seja feita normalmente nesta ordem:

1. **Field Service Common** – o Field Service Common é instalado quando o Field Service é instalado no ambiente.
2. **Field Service (Anchor)** – o Field Service (Anchor) é instalado quando o Field Service é instalado no ambiente. 
3. **Supply Chain Management Extended** – o Supply Chain Management Extended é instalado automaticamente quando a gravação dupla é habilitada em um ambiente. 
4. **Solução OneFSSCM** – o OneFSSCM é instalado automaticamente pela solução (Field Service ou Supply Chain Management) instalada por último.

    - Se o Field Service já estiver instalado no ambiente e você habilitar a gravação dupla, que instala o Supply Chain Management Extended, o OneFSSCM será instalado.
    - Se o Supply Chain Management Extended já estiver instalado no ambiente e você instalar o Field Service, o OneFSSCM será instalado.

## <a name="initial-synchronization"></a>Sincronização inicial

Para criar novas ordens de compra e trabalhar com ordens de compra existentes, você deve sincronizar os dados de referência entre o Supply Chain Management e o Dataverse. Use a funcionalidade de gravação inicial para detectar os relacionamentos entre as tabelas e localizar as tabelas que você deve habilitar para um determinado mapa.

Você deve sincronizar as seguintes tabelas:

- Modelos de produtos

    Ao executar a gravação inicial, você obtém uma lista completa das tabelas necessárias. Veja aqui alguns exemplos desses modelos:

    - Todos os produtos
    - Produtos liberados V2
    - Produtos distintos liberados pelo Dataverse

- Sites
- Depósitos
- Modelos de categorias de compras

    Veja aqui alguns exemplos desses modelos:

    - Categorias de compras
    - Pro
    - Hierarquia de categoria de produto
    - Atribuições de categoria de produtos

- Modelos de fornecedor, como Fornecedor V2
- Modelos de pessoa de contato, como Contatos do Dataverse V2
- Modelos de trabalhador, como Trabalhador

A sincronização das tabelas garante que todos os documentos (ordens de compra e recebimentos de produtos) no Supply Chain Management estejam disponíveis no Dataverse.

### <a name="account-and-vendor-tables"></a>Tabelas Contas e Fornecedores

As ordens de compra no Field Service dependem da tabela Contas para rastrear fornecedores. Portanto, as tabelas do Dataverse para ordens de compra usam contas para rastrear fornecedores. Para acomodar essa diferença fundamental, os quatro fluxos de trabalho a seguir devem ser ativados para manter as contas e os fornecedores em sincronia: 

- Criar Fornecedores na tabela Contas
- Criar Fornecedores na tabela Fornecedores
- Atualizar Fornecedores na tabela Contas
- Atualizar Fornecedores na tabela Fornecedores

Se o OneFSSCM estiver instalado, como o Field Service e o Supply Chain Management Extended estão instalados, esses fluxos de trabalho serão ativados automaticamente. Se o Field Service não estiver instalado, mas você quiser integrar as tabelas de ordens de compra ao Dataverse, será necessário ativar esses fluxos de trabalho. Em ambos os casos, a menos que você comece do zero, talvez seja necessário garantir que todos os fornecedores sejam criados como contas no Dataverse antes de criar ordens de compra. Caso contrário, erros podem ocorrer.

### <a name="initial-synchronization"></a>Sincronização inicial

Depois que todos os pré-requisitos forem atendidos, se você quiser que as ordens de compra e os recebimentos de produtos existentes estejam disponíveis nos dois sistemas, será necessário fazer uma sincronização inicial dos seguintes modelos:

- Cabeçalho da Ordem de Compra V2
- Linha da Ordem de Compra do CDS
- Exclusão temporária da Linha da Ordem de Compra do CDS
- Recebimento de Ordem de Compra
- Produto de Recebimento de Ordem de Compra

## <a name="mappings-with-logic"></a>Mapeamentos com lógica

A integração de compras estende o mapeamento de produtos com a lógica a seguir para garantir que a coluna **Tipo de Produto do Field Service** seja corretamente definida na tabela de produtos no Dataverse:

- Se **Tipo de Produto** estiver definido como *Produto* e **Grupo de modelos do item, Produto em estoque** estiver definido como *Verdadeiro*, **Tipo de Produto do Field Service** será definido como *Estoque*.
- Se **Tipo de Produto** estiver definido como *Produto* e **Grupo de modelos do item, Produto em estoque** estiver definido como *Falso*, **Tipo de Produto do Field Service** será definido como *Não Pertencente ao Estoque*.
- Se **Tipo de Produto** estiver definido como *Serviço*, **Tipo de Produto do Field Service** será definido como *Serviço*.

Além disso, o Dataverse inclui uma lógica que mapeia fornecedores com suas contas relacionadas. Essa lógica define a conta de fornecedor de fatura padrão. Na criação, a lógica de plug-in do servidor define a conta de fornecedor de fatura padrão do fornecedor relacionado à conta. O fornecedor tem uma referência à conta de fatura que é usada para definir esse valor.

## <a name="supported-scenarios"></a>Cenários com suporte

- As ordens de compra podem ser criadas e atualizadas pelos usuários do Dataverse. No entanto, o processo e os dados são controlados pelo Supply Chain Management. As restrições em atualizações de colunas da ordem de compra no Supply Chain Management se aplicam quando as atualizações são provenientes do Field Service. Por exemplo, não é possível atualizar uma ordem de compra se ela tiver sido finalizada. 
- Se a ordem de compra for controlada pelo gerenciamento de alterações no Supply Chain Management, um usuário do Field Service só poderá atualizá-la quando o status de aprovação do Supply Chain Management for *Rascunho*.
- Várias colunas são gerenciadas somente pelo Supply Chain Management e não podem ser atualizadas no Field Service. Para saber quais colunas não podem ser atualizadas, analise as tabelas de mapeamento no produto. Por uma questão de simplicidade, a maioria dessas colunas é definida como somente leitura nas páginas do Dataverse. 

    Por exemplo, as colunas de informações sobre preços são gerenciadas pelo Supply Chain Management. O Supply Chain Management tem contratos comerciais que o Field Service pode aproveitar. Colunas como **Preço unitário**, **Desconto** e **Valor líquido** são provenientes apenas do Supply Chain Management. Para garantir que o preço seja sincronizado com o Field Service, você deve usar o recurso **Sincronizar** nas páginas **Ordem de Compra** e **Produto da Ordem de Compra** no Dataverse quando os dados da ordem de compra tiverem sido inseridos. Para obter mais informações, consulte [Sincronizar sob demanda com os dados de compras do Dynamics 365 Supply Chain Management](#sync-procurement).

- A coluna **Totais** está disponível somente no Field Service, pois não há totais atualizados da ordem de compra no Supply Chain Management. Os totais no Supply Chain Management são calculados com base em vários parâmetros que não estão disponíveis no Field Service.
- As linhas da ordem de compra em que somente uma categoria de compras é especificada, ou em que o produto especificado é um item do tipo de produto *Serviço* ou Field Service, podem ser iniciadas somente no Supply Chain Management. Em seguida, elas são sincronizadas com o Dataverse e ficam visíveis no Field Service.
- Se apenas o Field Service estiver instalado, não o Supply Chain Management, a coluna **Depósito** será obrigatória na ordem de compra. No entanto, se o Supply Chain Management estiver instalado, esse requisito será relaxado, pois o Supply Chain Management permite linhas da ordem de compra em que nenhum depósito é especificado em determinadas situações.
- Os recebimentos de produtos (recebimentos de ordens de compra no Dataverse) são gerenciados pelo Supply Chain Management e não podem ser criados no Dataverse se o Supply Chain Management estiver instalado. Os recebimentos de produtos do Supply Chain Management são sincronizados do Supply Chain Management para o Dataverse.
- A entrega insuficiente é permitida no Supply Chain Management. A solução OneFSSCM adiciona lógica para que, quando a linha de recebimento de produtos (ou o produto de recebimento de ordens de compra no Dataverse) for criada ou atualizada, uma linha de diário de estoque seja criada no Dataverse para ajustar a quantidade restante que está na ordem para cenários de entrega insuficiente.

## <a name="unsupported-scenarios"></a>Cenários sem suporte

- O Field Service impede que linhas sejam adicionadas a uma ordem de compra cancelada no Supply Chain Management. Como solução alternativa, você pode alterar o status do sistema da ordem de compra no Field Service e, em seguida, adicionar a nova linha no Field Service ou no Supply Chain Management.
- Embora as linhas de compras afetem os níveis de estoque nos dois sistemas, essa integração não garante o alinhamento do estoque no Supply Chain Management e no Field Service. O Field Service e o Supply Chain Management têm outros processos que atualizam os níveis de estoque. Esses processos estão fora do escopo de compras.

## <a name="status-management"></a>Gerenciamento de status

Os status das ordens de compra no Field Service diferem dos status no Supply Chain Management.

### <a name="field-service-purchase-order-and-purchase-order-product-statuses"></a>Status de ordens de compra e produtos de ordens de compra no Field Service

| Cabeçalho – status do sistema | Cabeçalho – status de aprovação | Status do item |
|---|---|---|
| <ul><li>Preliminar</li><li>Envio feito</li><li>Cancelados(as)</li><li>Produto recebido</li><li>Faturado</li></ul> | <ul><li>Nulo</li><li>Aprovada</li><li>Rejeitada</li></ul> | <ul><li>Pendente</li><li>Recebidos</li><li>Cancelados(as)</li></ul> |

### <a name="supply-chain-management-purchase-order-and-purchase-order-line-statuses"></a>Status de ordens de compra e linhas de ordens de compra no Supply Chain Management

Os status de aprovação de linhas ficam ativos somente quando há um fluxo de trabalho de linha.

| Cabeçalho – status dos documentos | Cabeçalho – status de aprovação | Status da linha | Status de aprovação de linha |
|---|---|---|---|
| <ul><li>Ordem em Aberto (Ordem pendente)</li><li>Recebidos</li><li>Faturadas</li><li>Cancelados(as)</li></ul> | <ul><li>Preliminar</li><li>Em Revisão</li><li>Aprovada</li><li>Rejeitada</li><li>Em Revisão Externa</li><li>Confirmada</li><li>Finalizado</li></ul> | <ul><li>Ordem em Aberto (ordem pendente)</li><li>Recebidos</li><li>Faturadas</li><li>Cancelados(as)</li></ul> | <ul><li>Não Enviado</li><li>Em Revisão</li><li>Aprovada</li><li>Rejeitada</li></ul> |

As regras a seguir são aplicadas às colunas de status:

- O status no Supply Chain Management não pode ser atualizado no Field Service. No entanto, em alguns casos, o status no Field Service será atualizado quando o status da ordem de compra no Supply Chain Management for alterado.
- Se uma ordem de compra no Supply Chain Management estiver no gerenciamento de alterações e uma alteração estiver sendo processada, o status de aprovação será *Rascunho* ou *Em Revisão*. Nesse caso, o status de aprovação do Field Service será definido como *Nulo*.
- Se o status de aprovação da ordem de compra no Supply Chain Management estiver definido como *Aprovado*, *Em Revisão Externa*, *Confirmado* ou *Finalizado*, o status de aprovação da ordem de compra no Field Service será definido como *Aprovado*.
- Se o status de aprovação da ordem de compra no Supply Chain Management estiver definido como *Rejeitado*, o status de aprovação da ordem de compra no Field Service será definido como *Rejeitado*.
- Se o status do cabeçalho do documento no Supply Chain Management for alterado para *Ordem em aberto (Ordem pendente)* e o status da ordem de compra no Field Service for *Rascunho* ou *Cancelado*, o status da ordem de compra no Field Service será alterado para *Enviado*.
- Se o status do cabeçalho do documento no Supply Chain Management for alterado para *Cancelado* e nenhum produto de recebimento de ordens de compra no Field Service for associado à ordem de compra (por meio de produtos de ordens de compra), o status do sistema no Field Service será definido como *Cancelado*.
- Se o status da linha da ordem de compra no Supply Chain Management for *Cancelado*, o status do produto da ordem de compra no Field Service será definido como *Cancelado*. Além disso, se o status da linha da ordem de compra no Supply Chain Management for alterado de *Cancelado* para *Ordem Pendente*, o status do item de produto da ordem de compra no Field Service será definido como *Pendente*.

## <a name="sync-with-the-supply-chain-management-procurement-data-on-demand"></a><a id="sync-procurement"></a>Sincronizar sob demanda com os dados de compras do Supply Chain Management

O Supply Chain Management inclui dados de compras que tratam de contratos comerciais, descontos e outros cenários que dependem de processos secundários no Supply Chain Management. O mecanismo de compras usa regras complexas para determinar o melhor preço para uma determinada ordem de compra. Quando você usa a gravação dupla, os dados nem sempre são mantidos em sincronia entre os dois ambientes, especialmente em cenários em que a linha foi criada ou atualizada no Dataverse e pode acionar processos subsequentes no Supply Chain Management.

## <a name="sync-the-procurement-data-from-supply-chain-management"></a>Sincronizar os dados de compras do Supply Chain Management

1. No Dataverse, Acesse **Estoque \> Ordem de Compra**.
2. Selecione **Novo** para criar uma nova ordem de compra ou selecione a linha de uma ordem de compra existente.
3. Da ordem de compra ou da linha da ordem de compra.
4. No Painel de Ações, selecione **Sincronizar**.

Todas as colunas do Dataverse e do Field Service compartilhadas pelo Supply Chain Management são sincronizadas.

Veja as situações em que você pode usar a função **Sincronizar**:

- Se você fizer várias alterações sucessivas na mesma linha do Dataverse, execute a função **Sincronizar**.
- Se você não tiver certeza de que uma alteração pode ser a segunda alteração sucessiva do Dataverse, pode fazer sentido executar a função **Sincronizar**.
- Se você receber uma mensagem de erro sobre a atualização de um valor do Supply Chain Management, execute a função **Sincronizar** e repita a atualização no Dataverse.

## <a name="cancelling-the-posting-process"></a>Cancelar o processo de lançamento

Se o processo de lançamento de recebimento de produtos for cancelado durante o processamento, a gravação dupla poderá criar uma linha de recebimento de produtos no Dataverse, mas não criar uma linha de recebimento de produtos no Supply Chain Management. Essa situação ocorre porque a gravação dupla não oferece suporte a transações distribuídas.

## <a name="templates"></a>Modelos

Os modelos a seguir estão disponíveis para a integração de documentos relacionados a compras.

| Gerenciamento da Cadeia de Fornecedores | Field Service | descrição |
|---|---|---|
| [Cabeçalho da ordem de compra V2](mapping-reference.md#183) | msdyn\_Purchaseorders | Esta tabela contém as colunas que representam o cabeçalho da ordem de compra. |
| [Entidade da linha da ordem de compra](mapping-reference.md#181) | msdyn\_PurchaseOrderProducts | Esta tabela contém as linhas que representam as linhas em uma ordem de compra. O número do produto é usado para sincronização. Isso identifica o produto como uma unidade de manutenção de estoque (SKU), incluindo suas dimensões. Para obter mais informações sobre a integração de produtos ao Dataverse, consulte [Experiência unificada de produtos](product-mapping.md). |
| [Cabeçalho de recebimento de produtos](mapping-reference.md#185) | msdyn\_purchaseorderreceipts | Esta tabela contém os cabeçalhos de recebimento de produtos que são criados quando um recebimento de produtos é lançado no Supply Chain Management. |
| [Linha de recebimento de produtos](mapping-reference.md#184) | msdyn\_purchaseorderreceiptproducts | Esta tabela contém as linhas de recebimento de produtos que são criadas quando um recebimento de produtos é lançado no Supply Chain Management. |
| [Entidade excluída temporariamente da linha da ordem de compra](mapping-reference.md#182) | msdyn\_purchaseorderproducts | Esta tabela contém informações sobre linhas da ordem de compra que são excluídas temporariamente. Uma linha da ordem de compra no Supply Chain Management pode ser excluída temporariamente apenas quando a ordem de compra tiver sido confirmada ou aprovada, se o gerenciamento de alterações estiver ativado. A linha existe no banco de dados do Supply Chain Management e está marcada como **IsDeleted**. Como o Dataverse não tem um conceito de exclusão temporária, é importante que essas informações sejam sincronizadas com o Dataverse. Dessa forma, as linhas que são excluídas temporariamente no Supply Chain Management podem ser excluídas de forma automática do Dataverse. Nesse caso, a lógica de exclusão de uma linha no Dataverse está localizada no Supply Chain Management Extended. |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
