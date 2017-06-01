---
title: "Colaboração de fornecedores com fornecedores externos"
description: "Este tópico descreve como os agentes de compras podem colaborar com os fornecedores externos na troca de informações sobre ordens de compra e estoque de consignação."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b141ed78306504949eae641377b5c5a2b0599572
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-collaboration-with-external-vendors"></a>Colaboração de fornecedores com fornecedores externos

[!include[banner](../includes/banner.md)]


Este tópico descreve como os agentes de compras podem colaborar com os fornecedores externos na troca de informações sobre ordens de compra e estoque de consignação.

O módulo **Colaboração do fornecedor** é destinado a fornecedores que não tenham integração EDI (Troca de dados eletrônica) com o Microsoft Dynamics 365 for Operations. Ele permite que os fornecedores trabalhem com ordens de compra, faturas e informações de estoque de consignação. Este tópico descreve como você pode colaborar com fornecedores externos que estiverem usando a interface de colaboração do fornecedor para trabalhar com OCs e estoque de consignação. Ele também descreve como habilitar um fornecedor específico para usar a colaboração do fornecedor e como definir as informações que todos os fornecedores verão ao responderem a uma OC. Para saber mais sobre o que os fornecedores externos podem fazer na interface de colaboração do fornecedor, consulte [Colaboração do fornecedor com clientes](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Para saber mais sobre como os fornecedores podem usar a colaboração do fornecedor nos processos de faturamento, consulte [Espaço de trabalho de faturamento de colaboração do fornecedor](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace). Para saber mais sobre como provisionar novos usuários de colaboração do fornecedor, consulte [Gerenciar usuários de colaboração do fornecedor](manage-vendor-collaboration-users.md).

## <a name="define-the-information-shown-to-vendors-when-they-respond-to-pos"></a>Definir as informações mostradas aos fornecedores quando eles respondem a OCs
Quando os fornecedores respondem à OC que você enviou, eles veem uma caixa de diálogo em que precisam confirmar se desejam aceitar, rejeitar ou aceitar a OC com alterações. As informações que precisam ser exibidas ao fornecedor nesse momento podem ser específicas da sua empresa, portanto você poderá especificar o texto que será mostrado em cada uma das três mensagens de confirmação. Por exemplo, o texto pode informar o fornecedor sobre as próximas etapas no processo ou sobre os termos e condições.  

Para definir o texto que é mostrado na resposta da OC:

1.  Abra a página **Informações para fornecedores em resposta a OCs**.
2.  Selecione um dos tipos de resposta a seguir:
3.  Clique em **Editar**.
4.  Insira as informações que você deseja que seus fornecedores vejam na caixa de diálogo **Mensagem de informação**.

Se for necessário adicionar mensagens em mais de um idioma, crie mensagens separadas com os códigos de idioma apropriados. A mensagem será mostrada ao fornecedor no idioma que ele usar.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Definir as opções de colaboração do fornecedor para um fornecedor específico
As configurações gerais para a colaboração do fornecedor no Dynamics 365 for Operations são definidas por um administrador. Por exemplo, ele determinará quais funções de segurança estarão disponíveis para todos os fornecedores com quem você colabora. Há também algumas configurações que podem variar para cada conta de fornecedor, e você deve definir o seguinte:

-   Habilite a colaboração do fornecedor.
-   Decida se você deseja que o fornecedor veja as informações de preço.

### <a name="enable-vendor-collaboration"></a>Habilitar a colaboração do fornecedor

Antes que as contas de usuário possam ser criadas para um fornecedor externo, você deve configurar a conta de fornecedor para permitir que ele use a colaboração do fornecedor. Para fazer isso, defina o campo **Ativação de colaboração** como ativo na guia **Geral**, na página **Fornecedores**. Há duas opções que podem ser escolhidas:

-   **Ativo (a OC é confirmada automaticamente)**– as ordens de compra são confirmadas automaticamente quando o fornecedor as aceita sem alterações.
-   **Ativo (a OC não é confirmada automaticamente)**– as ordens de compra precisam ser confirmadas manualmente por sua organização depois que o fornecedor aceitá-las.

### <a name="decide-whether-you-want-the-vendor-to-see-price-information"></a>Decida se você deseja que o fornecedor veja as informações de preço.

Se você quiser compartilhar as informações de preço, como preço unitário, descontos e encargos por meio da interface de colaboração, será preciso definir a opção **Valores/preços das ordens de compra** como **Sim** na conta de fornecedor. Esta opção está disponível na guia **Padrões da ordem de compra**.

## <a name="work-with-pos-when-using-vendor-collaboration"></a>Trabalhar com OCs ao usar a colaboração do fornecedor
### <a name="sending-a-po-to-the-vendor"></a>Enviando uma OC ao fornecedor

As ordens de compra são preparadas no Dynamics 365 for Operations. Quando a OC tiver um status de **Aprovada**, você a enviará ao fornecedor usando a ação **Enviar para confirmação **na página **Ordem de compra**. O status da OC mudará para **Em Revisão externa**. Depois que a OC for enviada, o fornecedor poderá vê-la na página **Ordens de compra para revisão** na interface de colaboração do fornecedor, onde ele poderá aceitar, rejeitar ou sugerir alterações à ordem. O fornecedor também pode adicionar comentários para comunicar informações como as alterações na OC. Para chamar a atenção do fornecedor para a nova OC, você também pode usar o sistema de gerenciamento de impressão para enviar a OC por email.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>Confirmação e aceitação da OC pelo fornecedor

Quando um fornecedor aceitar uma ordem de compra, a OC poderá ser confirmada automaticamente ou precisará ser confirmada manualmente. Isso vai depender se o campo **Ativação de fornecedor **estiver definido como **Ativo (a OC é confirmada automaticamente)** para o fornecedor ou como **Ativo (a OC não é confirmada automaticamente)**.  

A tabela a seguir mostra a troca comum de informações, dependendo de como o fornecedor responde quando você envia uma OC para confirmação.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Resposta do fornecedor</strong></td>
<td><strong>Resultado</strong></td>
</tr>
<tr class="even">
<td>O fornecedor <strong>aceita</strong> a ordem. O Dynamics 365 for Operations está configurado para confirmar automaticamente as OCs quando o fornecedor aceitar.</td>
<td>O status da ordem é atualizado para <strong>Confirmada</strong>. Se algo impede que a ordem seja atualizada, a resposta do fornecedor ainda é registrada como <strong>Aceita</strong>, mas o status da OC permanece <strong>Em Revisão externa</strong>.</td>
</tr>
<tr class="odd">
<td>O fornecedor <strong>aceita</strong> a ordem. O Dynamics 365 for Operations não está configurado para confirmar automaticamente as OCs quando o fornecedor aceitar.</td>
<td>A resposta do fornecedor é registrada como <strong>Aceita</strong>, mas o status da OC permanece <strong>Em Revisão externa</strong>.</td>
</tr>
<tr class="even">
<td>O fornecedor <strong>rejeita</strong> a ordem.</td>
<td>A resposta do fornecedor é registrada como <strong>Rejeitada</strong> e o status da OC permanece <strong>Em Revisão Externa</strong>. A rejeição é recebida junto com as anotações do fornecedor.</td>
</tr>
<tr class="odd">
<td>O fornecedor <strong>aceita a ordem com alterações</strong>. As alterações são sugeridas em nível de linha. É possível aceitar ou rejeitar linhas individuais. Outras alterações possíveis incluem:
<ul>
<li>Alterar datas ou quantidades.</li>
<li>Dividir linhas para datas de entrega ou quantidades diferentes.</li>
<li>Substituir um item.</li>
</ul>
As informações de preço e os encargos não podem ser alterados pelo fornecedor. Sugestões de alterações a esses itens podem ser feitas usando-se anotações.</td>
<td>A resposta do fornecedor é registrada como <strong>Aceito com alterações</strong>, <strong></strong> mas o status da OC permanece <strong>Em Revisão externa</strong>.</td>
</tr>
</tbody>
</table>

Você pode usar o espaço de trabalho de preparação de **Ordem de compra** **** para monitorar quais OCs o fornecedor respondeu. Este espaço de trabalho contém duas listas que contêm pedidos com um status de **Em Revisão Externa**:

-   Em revisão externa, ação necessária.
-   Em revisão externa, aguardando resposta do fornecedor.

### <a name="changing-a-po"></a>Alterando uma OC

Quando precisar alterar uma OC que já tenha tido resposta, você enviará uma nova versão da OC ao fornecedor. A nova OC terá um sufixo de versão para indicar que é uma versão modificada de uma OC anteriormente comunicada. A página **Histórico de confirmações do fornecedor de ordens de compra** permite que você e seus fornecedores acompanhem o histórico de cada ordem. A versão anteriormente confirmada da OC permanecerá na lista de OCs confirmadas até que a nova OC seja confirmada.

### <a name="cancelling-a-po"></a>Cancelando uma OC

Quando você cancela uma OC, o status é alterado para **Aprovada**. Você deve enviar a OC novamente ao fornecedor por meio do portal do fornecedor para que ele possa confirmar ou rejeitar o cancelamento. Depois que o cancelamento for confirmado, a OC aparecerá na lista de OCs confirmadas do fornecedor como **Cancelada**.

### <a name="adding-attachments-to-a-po"></a>Adicionando anexos a uma OC

Você pode adicionar anexos, como arquivos, imagens e anotações, à OC usando o sistema de gerenciamento de documentos. Os anexos adicionados com a restrição de tipo **Externo** aparecerão para o fornecedor quando você enviar a OC a ele.

## <a name="purchase-order-statuses-and-versions"></a>Status e versões da ordem de compra
Esta seção descreve os diferentes status que uma OC pode ter até o momento em que seja confirmada e em que momento as novas versões da OC são disponibilizadas ao fornecedor. Há diferenças nesses casos, dependendo se você usa o gerenciamento de alterações para ordens de compra. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versões e status se você não usar o gerenciamento de alterações

A tabela a seguir mostra um exemplo das alterações de status e versão pelas quais uma OC pode passar.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Ação**                                                               | **Status e versão**                                                                                                                                       |
| A versão inicial da OC é criada no Dynamics 365 for Operations. | O status é **Aprovada**.                                                                                                                                  |
| A OC é enviada ao fornecedor.                                            | Uma versão é registrada na interface de colaboração do fornecedor e o status é alterado para **Em Revisão externa**.                                          |
| O fornecedor envia uma resposta **Aceito com alterações**.                  | O status ainda é **Em Revisão externa**.                                                                                                                  |
| Você faz algumas alterações que são solicitadas pelo fornecedor.                  | O status é alterado para **Aprovada**.                                                                                                                        |
| Você envia a nova versão da OC ao fornecedor.                        | Uma nova versão é registrada na interface de colaboração do fornecedor e o status é alterado para **Em Revisão externa**.                                      |
| O fornecedor aceita a nova versão da OC.                            | O status ainda é **Em Revisão externa**a menos que a conta do fornecedor seja configurada para definir automaticamente a OC para um estado **Confirmado** ao aceitá-la. |

Os fornecedores não precisam confirmar a OC usando a interface de colaboração do fornecedor. Eles também podem enviar uma mensagem de email ou comunicar a aceitação de uma OC por meio de outro canais. É possível confirmar a ordem manualmente no Dynamics 365 for Operations. Se fizer isso, você receberá um aviso de que a ordem está sendo confirmada mesmo que não haja nenhuma resposta do fornecedor. A OC aparecerá no histórico de confirmação como uma ordem confirmada aberta que não tem nenhuma resposta. O fornecedor não terá mais a opção de confirmar ou rejeitar a OC.  

**Observação:** a versão da OC disponível para outros processos no Dynamics 365 for Operations sempre será a versão mais recente, mesmo se essa versão ainda não tiver sido registrada na interface de colaboração do fornecedor.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versões e status se você usar o gerenciamento de alterações

Se o gerenciamento de alterações estiver ativado para as OCs, a OC passará por um fluxo de trabalho de aprovação para atingir o status **Aprovada**. Esse processo não aparece para o fornecedor.  

A tabela a seguir mostra um exemplo das alterações de status e versão pelas quais uma OC poderá passar quando o gerenciamento de alterações estiver ativado: A versão será registrada quando a OC for aprovada, não quando a OC for enviada ao fornecedor ou confirmada.

|                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Ação**                                                                                                    | **Status e versão**                                                                                                                                                                                                                                                                                                                                                                      |
| A versão inicial da OC é criada no Dynamics 365 for Operations.                                      | O status é **Rascunho**.                                                                                                                                                                                                                                                                                                                                                                    |
| A OC é submetida ao processo de aprovação (Isso é um processo interno no qual o fornecedor não está envolvido). | O status é alterado de **Rascunho** para **Em Revisão** para **Aprovação** se a OC não for rejeitada durante o processo de aprovação. A OC aprovada é registrada como uma versão.                                                                                                                                                                                                                     |
| A OC é enviada ao fornecedor                                                                                  | A versão é registrada na interface de colaboração do fornecedor e o status é alterado para **Em Revisão externa**.                                                                                                                                                                                                                                                                       |
| Você faz algumas alterações que são solicitadas pelo fornecedor.                                                       | O status é alterado novamente para **Rascunho**.                                                                                                                                                                                                                                                                                                                                                    |
| A OC é submetida ao processo de aprovação novamente.                                                            | O status é alterado de **Rascunho** para **Em Revisão** para **Aprovação** se a OC não for rejeitada durante o processo de aprovação. Alternativamente, o sistema pode ser configurado para que as alterações de campos específicos não exijam uma nova aprovação. Nesse caso, o status é primeiro alterado para **Rascunho** e depois automaticamente atualizado para **Aprovada**. A OC aprovada é registrada como uma nova versão. |
| Você envia a nova versão da OC ao fornecedor.                                                             | A nova versão é registrada na interface de colaboração do fornecedor e o status é alterado para **Em Revisão externa**.                                                                                                                                                                                                                                                                   |
| O fornecedor aprova a nova versão da OC.                                                                | O status é alterado para **Confirmada** automaticamente ou quando você recebe a resposta do fornecedor e confirma a OC.                                                                                                                                                                                                                                                     |

## <a name="share-information-about-consignment-inventory"></a>Compartilhar informações sobre o estoque de consignação
Se você estiver usando o estoque de consignação, os fornecedores poderão usar a interface de colaboração do fornecedor para exibir informações nas seguintes páginas:

-   **Ordens de compra que consomem o estoque de consignação** – ordens de compra para o estoque de consignação são geradas quando a propriedade do estoque é alterada do fornecedor para a sua empresa. Um recebimento de produto é lançado ao mesmo tempo. Essas ordens de compra de consignação são exibidas somente na página**Ordens de compra que consomem o estoque em consignação**. Elas não estão incluídas na página **Todas as ordens de compra confirmadas**, no módulo **Colaboração do fornecedor**.
-   **Produtos recebidos de estoque de consignação** – esta página lista todas as transações em que a propriedade dos produtos é transferida do fornecedor para a sua empresa. Os fornecedores podem usar essas informações para faturar o cliente.
-   **Estoque de consignação disponível** – esta página mostra o estoque de consignação disponível de propriedade do fornecedor que foi recebido em seu depósito.





